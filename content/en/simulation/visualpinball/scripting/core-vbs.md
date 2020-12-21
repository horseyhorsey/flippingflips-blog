---
author: "Flips-Admin"
title: "📜Core VBS"
date: 2020-05-01T11:00:00+00:00
description: "The core.vbs file in the visual pinball scripts directory contains helper classes, amongst other things to be used in conjunction with controllers or basic scripts"
draft: false
image: images/vp/corevbs.jpg
hideToc: false
enableToc: true
enableTocContent: false
author: flips-admin
authorEmoji: 🌱
categories:
- download
- visual pinball
tags: 
- beginner
- kicker
- scripting
- switch
- trough
- vuk
---

The `Core.vbs` contains helper classes for `BallStacks`, `Motors` and much more.

This file is shipped with `Visual Pinball` and can be found in the `Scripts` folder.

Full documentation is available from VPForums tutorials. [vbsdoc.html](https://www.vpforums.org/Tutorials/vbsdoc.html) or use the `Scripts\Core.vbs` as this is updated.

---

## Initializing Core Vbs in a table

### Init Core.vbs Examples

---

#### Controller timers

---

Add timers to the table called `PinMameTimer` and `PulseTimer` if you want to update `Solenoids`, `Lamps`, `Switches`. You will find these timers in any `PinMame` table for reference.

---

#### Empty table (No Pinmame)

---

Insert the following into a tables script.

``` vb

LoadCoreVBS
Sub LoadCoreVBS
     On Error Resume Next
     ExecuteGlobal GetTextFile("core.vbs")
     If Err Then MsgBox "Can't open core.vbs"
     On Error Goto 0
End Sub

```

> If it's a completely empty script, then you will need to add the following at the top of the tables script

``` vb
Option Explicit
Randomize
```

Loading the table `F5` will load the `core.vbs`, if you have no errors then this is working.

---

#### Empty table (With Dummy Pinmame)

---

We can create a `VPinMAME.Controller` without loading any machine configuration allowing us to use the classes in the `Core.vbs`.

``` vb
LoadCoreVBS
Sub LoadCoreVBS
     On Error Resume Next
     ExecuteGlobal GetTextFile("core.vbs")
     Set Controller = CreateObject("VPinMAME.Controller")
     If Err Then MsgBox "Can't open core.vbs"
     On Error Goto 0
End Sub
```
---

## Constants

---

Constants used (must be defined) like

``` vb 
const UseSolenoids = 1 
```

   Name  | Description
---|---|
ExtraKeyHelp |Game specific keys in help window
SCoin        |Coin Sound
SFlipperOn   |Flipper activate sound
SFlipperOff  |Flipper deactivate sound
SSolenoidOn  |Solenoid activate sound
SSolenoidOff |Solenoid deactivate sound
UseColoredDMD|
UseDMD|
UseLamps     |Update lamps
UseModSol|
UseNVRAM| Is enabled
UseSolenoids |Update solenoids

---

## Callbacks
   Name  | Description
---|---|
SolCallback(68)|Solenoids (parsed at Runtime)
SolModCallback(68)|Solenoid modulated callbacks (parsed at Runtime) 
SolPrevState(68)|When modulating solenoids are in use, needed to keep positive value levels from changing boolean state
LampCallback |Sub to call after lamps are updated (or every update if UseLamps is false)
PDLedCallback  |Called after leds are updated
MotorCallback|Called once every update for mechanics or custom sol handler
GICallback     |Called for each changed GI String
GICallback2    |Called for each changed GI String
vpmCreateBall  | Called whenever a vpm class needs to create a ball
BSize|
BMass|
NVRAMCallback | NVRAM would deliver everything of the NVRAM all the time as 1D array

---

## Classes

---



---
### cvpmImpulseP
---

Impulse Plunger for fireing balls from `triggers` or `plungers`

---

#### cvpmImpulseP Members

---

   Name  | Description
---|---|
(Public)  .InitImpulseP | Initialise Impulse Plunger Object (Trigger, Plunger Power, Time to Full Plunge [0 = Auto])
(Public)  .CreateEvents | Create Hit/Unhit events
(Public)  .Strength     | Change plunger strength
(Public)  .Time         | Change plunger time (in seconds) to full plunger strength (0 = Auto Plunger)
(Public)  .Pullback     | Pull the plunger back
(Public)  .Fire	    | Fires / Releases the Plunger (Manual or Auto depending on Timing Value given)
(Public)  .AutoFire	    | Fires / Releases the Plunger at Maximum Strength +/- Random variation (i.e. Instant Auto)
(Public)  .Switch	    | Switch Number to activate when ball is sitting on plunger trigger (if any)
(Public)  .Random       | Sets the multiplier level of random variance to add (0 = No Variance / Default) 
(Public)  .InitEntrySnd | Plays Sound as Plunger is Pulled Back
(Public)  .InitExitSnd  | Plays Sound as Plunger is Fired (WithBall,WithoutBall)

---

#### cvpmImpulseP Snippet

Create trigger named `shooterLane` or replace `shooterLane` in script for your trigger.

##### Global
``` vb
Dim impulseP
```

##### New
``` vb
    Set impulseP = New cvpmImpulseP
    With impulseP
        .InitImpulseP shooterLane, 40, 0
        .Random 0.3
        .InitExitSnd "exit_sound", "exit_sound"
        .CreateEvents "impulseP"
    End With
```
---

##### Testing

Auto fire on `PlungerKey` up
``` vb 
If keycode = PlungerKey Then	
    impulseP.AutoFire
    PlaySound "plungerpull",0,1,AudioPan(Plunger),0.25,0,0,1,AudioFade(Plunger)
End If

```

#### cvpmImpulseP Example

 [link](/en/simulation/visualpinball/scripting/core-vbs-cvpmimpulsep/#cvpmimpulsep-example)

---
### cvpmSaucer
---

Manages saucer ball stack using a Visual Pinball kicker. You can create many types using this including `Scoops, VUKs`

---

#### cvpmSaucer Members

---

   Name  | Description
---|---|
(Public) .AddBall          | Add a ball to the saucer from a kicker.
(Public) .CreateEvents     | Auto-generate hit event for VP kicker(s) associated with this saucer
(Public) .HasBall          | True if the saucer is occupied.
(Public) .InitAltKick      | Set alternate direction and force (including Z force) - for saucers with two kickers
(Public) .InitExitVariance | Modify kick direction and force (+/-, min force = 1)
(Public) .InitKicker       | Setup main kicker, switch, exit direction and force (including Z force)
(Public) .InitSounds       | Sounds to play when a ball enters the saucer or the kicker fires
(Public) .solOut           | Fire the primary exit kicker.  Ejects ball if one is present.
(Public) .solOutAlt        | Fire the secondary exit kicker.  Ejects ball with alternate forces if present.

#### cvpmSaucer Snippet

This snippet uses a `kicker` named `Saucer001`. Create variables for `bsSaucer` and `swSaucer` to hold the switchNo.

##### Global
``` vb
Dim bsSaucer: Dim swSaucer: swSaucer = 25
```

##### Init
``` vb
Set bsSaucer = New cvpmSaucer
bsSaucer.CreateEvents "bsSaucer",  Saucer001 ' Create events on the switch
bsSaucer.InitKicker Saucer001, swSaucer, 180, 10, 0
```

##### Without CreateEvents

If you are not using a controller no events will fire. So you can handle this for an original game or testing general.

Update init method and comment the create events.

``` vb
'bsSaucer.CreateEvents "bsSaucer",  Saucer001 ' Create events on the switch
```

Create `Hit` event method for `Saucer001`

``` vb
' Add a ball to bsSaucer manually and update when the saucer001 is hit
Sub Saucer001_Hit()	
    bsSaucer.AddBall 1
    bsSaucer.SolOut(1)
End Sub
```

#### cvpmSaucer Example

[link](/en/simulation/visualpinball/scripting/core-vbs-cvpmsaucer/#cvpmsaucer-example)

---

### cvpmTrough

---

Manages a trough ball stack using Visual Pinball kickers.

---

#### cvpmTrough Members

---

   Name  | Description
---|---|
(Public) .AddBall         |Add a ball to the trough from a kicker.  If kicker is the exit kicker, stacks ball at exit.
(Public) .AddSw           |Assign a switch at a specific slot
(Public) .Balls           |Get current balls in trough, or set initial number of balls in trough
(Public) .BallsPending    |Get number of balls waiting in trough entry
(Public) .CreateEvents    |Auto-generate hit events for VP entry kicker(s) associated with this trough
(Public) .EntrySw         |Set switch number for trough entry (if any)|eg. Outhole
(Public) .InitExit        |Setup exit kicker, force and direction
(Public) .InitSwitches    |Set trough switches using an array, from exit slot back toward entrance.
(Public) .InitEntrySounds |Sounds to play when a ball enters the trough
(Public) .InitExitSounds  |Sounds to play when the exit kicker fires
(Public) .InitExitVariance|Modify exit kick direction and force (+/-, min force = 1)
(Public) .IsDebug         |    ' If you want to see what the trough is doing internally, add a `TextBox` to your table ' named `DebugBox` (recommend Courier New or FixedSys at a small font size)
(Public) .IsTrough        |Get or Set whether this trough is the default trough (first trough sets this by default)
(Public) .MaxBallsPerKick |Set maximum number of balls to kick out (default 1)
(Public) .MaxSlotsPerKick |Set maximum slots from which to get balls when kicking out (default 1)
(Public) .Reset           |Reset and update all trough switches
(Public) .Size            |Get or Set total number of balls trough can hold
(Public) .SolIn           |Solenoid handler for entry solenoid
(Public) .SolOut          |Solenoid handler for exit solenoid
(Friend) .Update          |Called from vpmTimer to update ball positions and switches

#### cvpmTrough Snippet

This uses the default tables `Drain` and `BallRelease` kickers.

##### Global
``` vb
Dim bsTrough, swTrough1, swTrough2, swTrough3, swTrough4
swTrough1 = 81: swTrough2 = 82: swTrough3=83: swTrough4=84
SolCallback(4) = "bsTrough.SolOut"  ' Set the call back to 4
```

##### Init
``` vb
Set bsTrough = New cvpmTrough
bsTrough.CreateEvents "bsTrough",  Drain ' set the object to the drain switch
bsTrough.Size = 4
bsTrough.Balls = 4
bsTrough.InitSwitches Array(swTrough1, swTrough2, swTrough3, swTrough4)
bsTrough.InitExit BallRelease, 90, 8		  
bsTrough.InitEntrySounds "Drain", "", ""
bsTrough.InitExitSounds "BallRelease", ""
bsTrough.IsDebug = True
bsTrough.Reset	
```

##### Without CreateEvents

If you are not using a controller no events will fire. So you can handle this for an original game or testing general.

We won't be using a callback but the above definition can be left in script.

Update init method after creation to kick a ball from the stack when table loads

``` vb
'bsTrough.CreateEvents "bsTrough",  Drain ' set the object to the drain switch
bsTrough.SolOut(1)
```

Handle when the ball drains

``` vb
' Add a ball to bsTrough manually and update.
Sub Drain_Hit()
    PlaySound "drain",0,1,AudioPan(Drain),0.25,0,0,1,AudioFade(Drain)    
    NewBall(1)
End Sub

Sub NewBall(Enabled) ' method to pulse the trough
    bsTrough.AddBall 1    
    Drain.DestroyBall
    bsTrough.SolOut(Enabled)    
End Sub
```
#### cvpmTrough Example

[link](/en/simulation/visualpinball/scripting/core-vbs-cvpmtrough/#cvpmtrough-example)

---

## TODO:

### cvpmBallStack (DEPRECATED)
### cvpmCaptiveBall
### cvpmDips
### cvpmDropTarget
### cvpmMagnet
### cvpmMech
### cvpmNudge
### cvpmTimer
### cvpmTurnTable
### cvpmVLock


