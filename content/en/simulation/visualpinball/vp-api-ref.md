---
author: "Flips-Admin"
title: "📝 Visual Pinball Api"
date: 2020-04-11T08:00:06+09:00
description: "Visual Pinball Api references for scripting in visual basic script."
image: images/vp/visual-pinball-logo.png
draft: false
hideToc: false
enableToc: true
enableTocContent: false
author: flips-admin
authorEmoji: 🌱
categories:
- visual pinball
- vpx-api
tags: 
- audio
- backglass
- ball
- decal
- flasher
- flipper
- gate
- Kicker
- light
- physics
- plunger
- primitive
- ramp- reel
- rubber
- scripting
- spinner
- switch
- table
- target
- textbox
- timer
- trigger
- wall
---

The API references have been created from the `CommandReference.txt` from `VPX 6.0` build of `Visual Pinball`.

They can be used in `Visual Pinballs` script to interact with table objects.

---

Variables starting with a (*) can't be changed by the script (most can be read though) or don't have an effect.

## Global

### Global Keys
   Name |
---|
*LeftFlipperKey
*RightFlipperKey
*LeftTiltKey
*RightTiltKey
*CenterTiltKey
*PlungerKey
*StartGameKey
*AddCreditKey
*AddCreditKey2
*LeftMagnaSave
*RightMagnaSave
*LockbarKey

### Global Methods
   Name  | Description
---|---|
GetBalls(Ball) | returns all Balls on the table 
GetElements(Editable) |returns all Elements on the table
GetElementByName(string) |returns a certain Element, based on the name
FireKnocker(int Count)
LoadValue(string,string,VARIANT) |load a value for tablename,valuename,value
MaterialColor(string,OLE_COLOR) |change base color of a material
Nudge(float Angle, float Force)
NudgeGetCalibration/NudgeSetCalibration(int XMax, int YMax, int XGain, int YGain, int DeadZone, int TiltSensitivty)
NudgeSensorStatus(VARIANT *XNudge, VARIANT *YNudge)
NudgeTiltStatus(VARIANT *XPlumb, VARIANT *YPlumb, VARIANT *TiltPercent)
SaveValue(string,string,VARIANT) |save a value for tablename,valuename,value
QuitPlayer(int CloseType)
UpdateMaterial(string, float wrapLighting, float roughness, float glossyImageLerp, float thickness, float edge, float edgeAlpha, float opacity, OLE_COLOR base, OLE_COLOR glossy, OLE_COLOR clearcoat, VARIANT_BOOL isMetal, VARIANT_BOOL opacityActive, float elasticity, float elasticityFalloff, float friction, float scatterAngle) |updates all parameters of a material (same input ranges as used in the material editor)
UserDirectory(string)
Version | returns VP_VERSION_MAJOR * 1000 + VP_VERSION_MINOR * 100 + VP_VERSION_REVISION
VPBuildVersion | same, deprecated
VersionMajor | major VP version number
VersionMinor | minor VP version number
VersionRevision | VP version revision

### Global Properties
   Name | Type | Description | Default
---|---|---|---
*GameTime| int | Gets the current internal game time in milliseconds
*GetCustomParam|int| - 1..9, i.e. GetCustomParam(1) to get "param1" and GetCustomParam(2) to get "param2" from the command line "VPinballX.exe -c1 param1 -c2 param2"
DMDWidth|int| - set width of DMD
DMDHeight|int| - set height of DMD
DMDPixels|VARIANT| - set array of (byte-)values (0..100), size needs to match the previously set width and height
DMDColoredPixels|VARIANT| - set array of (long-)values (0..255,0..255,0..255), size needs to match the previously set width and height
*NightDay|int| - 0..100 value set in the UI (by the user) that defines if its night or day, so that the script can tweak table elements based on that value
*ShowDT|bool| - Desktop mode enabled (true) or Rotated Fullscreen mode enabled (false)
*ShowFSS|bool| - Extended Backglass mode enabled (true) or not (false)
*SystemTime| int | Gets the current internal game time in milliseconds
*WindowWidth|int| - get width of rendering window/fullscreen
*WindowHeight|int| - get height of rendering window/fullscreen
YieldTime|int| time in milliseconds to sleep during each frame - can help side threads like vpinmame. | 0

### Global Audio
   Name  | Description
---|---|
EndMusic()
MusicVolume(float volume) |0..1
PlayMusic(string, float volume) | volume 0..1
PlaySound(string, int loopcount, float volume, float pan, float randompitch, int pitch, bool useexisting, bool restart, float front_rear_fade)
StopSound(string)

PlaySound Options:
- also allows to increase/decrease the frequency of an already playing samples, and in general to apply all the settings to an already playing sample, and to choose if to restart this playing sample from the beginning or not
- loopcound chooses the amount of loops
- volume is in 0..1
- pan ranges from -1.0 (left) over 0.0 (both) to 1.0 (right)
- randompitch ranges from 0.0 (no randomization) to 1.0 (vary between half speed to double speed)
- pitch can be positive or negative and directly adds onto the standard sample frequency
- useexisting is 0 or 1 (if no existing/playing copy of the sound is found, then a new one is created)
- restart is 0 or 1 (only useful if useexisting is 1)
- front_rear_fade is similar to pan but fades between the front and rear speakers
- so f.e. PlaySound "FlipperUp",0,0.5,-1.0,1.0,1,1,0.0 would play the sound not looped (0), at half the volume (0.5), only on left speaker (-1.0), with varying pitch (1.0), it would reuse the same channel if it is already playing (1), restarts the sample (1), and plays it on the front speakers only (0.0)

## Table

   Name | Type | Description | Default
---|---|---|---
*Name|string | table name
*FileName|string | file name (without path and extension)
*GlobalDifficulty|float | Mainly chooses/weights between SlopeMax and SlopeMin, but also affects precision of flippers/scattering (0..100)
*Image|string | playfield image
PlungerNormalize|int | Mech-Plunger component adjustment or weak spring, aging. |100
PlungerFilter|bool | |false
*Accelerometer|bool 
*AccelNormalMount|bool
*AccelerometerAngle|float
*JoltAmount|int
*TiltAmount|int
*JoltTriggerTime|int
*TiltTriggerTime|int
*DeadZone|int
NudgeTime|float

### Table Callback
   Name | Description
---|---|
OnBallBallCollision(ball1, ball2, velocity)

### Table Audio
   Name | Type | Description | Default
---|---|---|---
*TableSoundVolume|int | Scales the global sound volume (in percent) | 100
*TableMusicVolume|int | Scales the global music volume (in percent) | 100

### Table Backglass
   Name | Type | Description | Default
---|---|---|---
*BackglassMode|int | Which Backglass mode is active (0=Desktop,1=Fullscreen,2=FullSingleScreen)|0
*BackDropColor|OLE_COLOR|
BackdropImage|string|

### Table Ball
   Name | Type | Description | Default
---|---|---|---
BallImage|string| 
BallFrontDecal|string| image of the ball front decal
*BallDecalMode|bool| switch between using the ball decal as ball logo or ball 'scratches'
*BallReflection | |enable ball reflection on table. depending on the global video setting 'Reflect Ball on Playfield' this is on or off. Or it is defined specific for this table.
BallPlayfieldReflectionScale|float| scale/dampen the contribution of the playfield to the ball reflections
*BallTrail | enable ball trail/motion blur on table. depending on the global video setting 'Ball Trail/Motion Blur' this is on or off. Or it is defined specific for this table.
*TrailStrength|int| defines the strength of the ball trail (0-100)

### Table Collections
   Name | Type | Description | Default
---|---|---|---
Count|int| return count of items in the collection

### Table Dimensions
   Name | Type | Description | Default
---|---|---|---
*Width|float| Playfield width. | 1000
*Height|float| Playfield height. | 2000
*GlassHeight|float| Height of Glass above Playfield
*TableHeight|float| Table height

### Table Graphics
   Name | Type | Description | Default
---|---|---|---
*EnableAntialiasing|bool| enables AA for this table if you have set 'Enable AntiAliasing' in the video options. |false
*EnableFXAA|bool| enables FXAA for this table if you have set 'Enable FXAA' in the video options. |false
*RenderEMReels|bool| | |true
*RenderDecals|bool| | |true
*TableAdaptiveVSync|int| sets adaptive vsync option for this table (-1=use global setting, 0=off, 1=automatic, any other number is refresh rate in Hz)
DefaultBulbIntensityScale|float| scale/dampen the contribution of the bulbs lights on the ball. This is a default setting for all balls created on the the table. If you need ball specific intensity scaling you can change the intensity by using the BulbIntensityScale value on the ball
*DetailLevel|int| defines the ramp accuracy for this table and overrides the global setting from the video options (range 0-10).


### Table Playfield
   Name | Type | Description | Default
---|---|---|---
*PlayfieldColor|OLE_COLOR|
PlayfieldReflectionStrength|int| | defines the reflection strength of the (dynamic) table elements on the playfield (0-100)

### Table Physics

   Name | Type | Description | Default
---|---|---|---
*SlopeMax|float| Angle of Playfield within Cabinet (used for Physics only)
*SlopeMin|float| Angle of Playfield within Cabinet (used for Physics only)
Gravity|float| | |0.86543
Friction|float| for the Playfield|0.0025
Elasticity|float| for the Playfield|0.2
ElasticityFalloff|float| for the Playfield|0
Scatter|float| scatter angle for the Playfield|0
DefaultScatter|float| overrides all elements that have scatter angle set to < 0 | 0
*OverridePhysics|int| overrides the table physics settings with pre defined settings defined under Preferences -> Physics Options You can define up to 8 different physics settings for the table and the flippers. Save them to one of the 8 slots and by assigning the slot number to this OverridePhysics it overrides these settings. | 0 (means use table settings)
PhysicsLoopTime|int| the meaning of this has changed starting with 9.2.1: it specifies the maximum number of iterations spent in the physics update. by setting it f.e. to 1, the rendered frame updates will -always- match the physics updates,everything above 1 allows for multiple physics updates per frame (2, 3 or 4 can be good values for this, as it slows down the physics temporarily if the FPS drop below 50, 33 or 25 in these cases). |-1 (which means infinite updates allowed)

### Table POV
   Name | Type | Description | Default
---|---|---|---
*Scalex|float| X Scale of Table
*Scaley|float| Y Scale of Table
*Scalez|float| Z Scale of Table
*Xlatex|float| X Offset of Table
*Xlatey|float| Y Offset of Table
*Xlatez|float| Z Offset of Table
*Inclination|float| Angle of Table (used for Display only) | 43
*Rotation|float| Rotation of Table (used mainly for FS/Cab tables: 270)
*Layback|float| Skew of Table (used mainly for FS/Cab tables). | 0
*FieldOfView|float| Perspective of Table. | 45

### Table Lighting

   Name | Type | Description | Default
---|---|---|---
*LightAmbient|OLE_COLOR| changes the ambient light contribution for each material, please always try to keep this at full Black
*Light0Emission|OLE_COLOR| changes the light contribution for each material (currently light0 emission is copied to light1, too)
LightEmissionScale|float|
EnvironmentEmissionScale|float|
AOScale|float| scaling factor when blending the ambient occlusion
SSRScale|float|  scaling factor when blending the screen space reflections
BloomStrength|float|  scaling factor when blurring the clipped framebuffer contribution (leave at 1 for kinda natural glow)
*LightHeight|float|  height of lights
*LightRange|float| range of lights
ColorGradeImage|string| the 256x16 LUT texture used for the color grading post process

### Table Stereo 3D
   Name | Type |  Description | Default
---|---|---|---
*MaxSeparation|float| Maximum separation/scale effect for Stereo 3D (ranges from 0..1)
*ZPD|float|  Reads the depth where the Stereo 3D should happen (ranges from 0..1)
*Offset|float|  Reads the constant offset for the Stereo 3D effect (ranges from 0..1)

## Objects

### Ball

---

#### Ball Methods
None

#### Ball Read Only

#### Ball Read/Write
   Name | Type | Description | Default
---|---|---|---
AngMomX|float|
AngMomY|float|
AngMomZ|float|
AngVelX|float|
AngVelY|float|
AngVelZ|float|
BulbIntensityScale|float| allows to dampen/scale the intensity of (bulb-)light reflections on each ball (e.g. to simulate shadowing in the ball lane, etc)
Color|OLE_COLOR| sets color of ball
DecalMode|bool| switch between using the ball decal as ball logo or ball 'scratches'
FrontDecal|string| image of the ball front decal
ForceReflection|bool| if enabled the ball will be reflection on the playfield even it's on a ramp or an upper playfield. (default=0)
ID|int| gets a unique ID for each ball created or allows to set an artificial one to distinguish different balls on the table
Image|string|
Mass|float|
PlayfieldReflectionScale|float| allows to dampen/scale the contribution of the playfield reflections on each ball (see BallPlayfieldReflectionScale() for the Table)
Radius|float|
ReflectionEnabled|bool| if playfield reflects objects this can be used to enable/disable the reflection for a specific ball
UserValue|any| can store any user defined value for re-use later-on
VelX|float|
VelY|float|
VelZ|float|
Visible|bool| changes if the ball is visible on the playfield or not (e.g. only physics simulated)
X|float|
Y|float|
Z|float|

### Bumper

---

#### Bumper Read Only

   Name | Type | Description | Default
---|---|---|---
*Name|string|
*X|float | X position
*Y|float | Y position
*BaseMaterial|string|
*BaseVisible|bool | | | true
*CapMaterial|string|
*CapVisible|bool | || true
*HeightScale |float ||| 90.0
*Orientation|float 
*Radius|float |||45.0
*ReflectionEnabled|bool || |true
*Scatter|float
*SkirtMaterial|string|
*Surface|string|

#### Bumper Read/Write
   Name | Type | Description | Default
---|---|---|---
Collidable |bool
EnableSkirtAnimation|bool | en/disables the skirt animation of a bumper, for example if something external is triggering the bumper (i.e. no ball contact with the skirt) |true
Force|float|
HasHitEvent|bool|
RingDropOffset|float| An offset to influence the ring animation. The default move down limit is calculated by (HeightScale*0.5) * Table_Scalez. The final move down limit is calculated by RingDropOffset + (HeightScale*0.5)* Table_Scalez. For example: If the ring is moving too far down you have to try to set the RingDropOffset to -10.
RingSpeed|float|
TimerEnabled|bool|
TimerInterval|int| set interval for triggering the timer (1 equals 1000 timer calls per second, 1000 equals 1 timer call per second, -1 makes it dependent on the FPS that a user can reach)
Threshold|float
UserValue|any | can store any user defined value for re-use later-on)

### Decal

---

#### Decal Read Only

   Name | Type | Description | Default
---|---|---|---
*X|float
*Y|float
*FontColor|OLE_COLOR
*Font|IFontDisp
*HasVerticalText|bool
*Height|float
*Image|string | texture name
*Rotation |float
*SizingType|SizingType | 0=AutoSize, 1=AutoWidth, 2=ManualSize
*Surface|string
*Type|DecalType| 0=Text, 1=Image
*Text|string
*Width|float

### EM Reel

---

#### EM Reel Methods

   Name | Description
---|---
AddValue(int value)
ResetToZero()
SetValue(int value)
SpinReel(int ReelNumber, int PulseCount)

#### EM Reel Read Only

   Name | Type | Description | Default
---|---|---|---
*Name|string
*BackColor|OLE_COLOR
*Image|string| picture name
*UserImageGrid|bool

#### EM Reel Read/Write
   Name | Type | Description | Default
---|---|---|---
IsTransparent|bool
Width|float
Height|float
ImagesPerGridRow|int
X|float
Y|float
Range|float
Reels|float
Spacing|float
Sound|string
Steps|float
TimerEnabled|bool|
TimerInterval|int| - set interval for triggering the timer (1 equals 1000 timer calls per second, 1000 equals 1 timer call per second, -1 makes it dependent on the FPS that a user can reach)
UpdateInterval|int|
UserValue|any | can store any user defined value for re-use later-on
Visible|bool

### Flasher

---

#### Flasher Methods
None

#### Flasher Read Only

   Name | Type | Description | Default
---|---|---|---
*Name|string
*DisplayTexture|bool|

#### Flasher Read/Write
   Name | Type | Description | Default
---|---|---|---
AddBlend|bool| use additive alpha blending instead of classical alpha blending
Amount|int | defines the filter amount how much of ImageB is filtered over ImageA in percent (0..100, can be set to >100 though)
Color || defines the color of the element in the editor. If you don't want to colorize the image set the color to blank white (RGB 255,255,255)
DMD|bool| enable DMD image via script connection
Filter|string| use one of the following filters to blend ImageA > ImageB: 'None', 'Additive', 'Multiply', 'Overlay', 'Screen' (filter names are case sensitive!) this feature only works if you defined both images
ImageA|string| texture name for image A
ImageB|string| texture name for image B
IntensityScale|float| - sets the flashers brightness/emission scale, so that one can fade in/out all affected flashers with the same scaling factor
Mode | int | 0=ImageModeWorld, 1=ImageModeWrap
ModulateVsAdd|float| blends between modulating and additive when bulb is enabled (0..1)
Opacity|int |lets you define the blend amount 0..100% (you can use values >100% though to for example enhance the strength of flashers in additive alpha blending mode)
ImageAlignment
TimerEnabled|bool|
TimerInterval|int | set interval for triggering the timer (1 equals 1000 timer calls per second, 1000 equals 1 timer call per second, -1 makes it dependent on the FPS that a user can reach)
UserValue|any |can store any user defined value for re-use later-on
Visible|bool| shows/hides the flasher

---

### Flipper

#### Flipper Methods
   Name | Description
---|---
RotateToEnd() | Rotates back to end angle
RotateToStart() | Rotates back to start angle

#### Flipper Read Only

   Name | Type | Description | Default
---|---|---|---
*BaseRadius| float |
*Color|OLE_COLOR
*CurrentAngle| float | only readable
*Enabled|bool
*EndAngle| float |
*EndRadius| float |
*FlipperRadiusMin| float |
*Height| float |
*Length| float |
*RubberColor|OLE_COLOR
*RubberHeight| float |
*RubberThickness| float |
*RubberWidth| float |
*StartAngle| float |
*Surface|string
*X|float
*Y|float
*Visible|bool

#### Flipper Read/Write
   Name | Type | Description | Default
---|---|---|---
Elasticity| float |
ElasticityFalloff| float |
EOSTorque| float | This value/factor affects the way how long a flipper arm stays in the up/raised position even when you released the flipper button. On real pinballs it will take some time until the flipper solenoid loses it's power until the flipper drops down or is forced to move by a hitting ball. The default value is 0.75. For fine tuning you can change that but not higher than 1 or lower than 0.5 or the result will be totally unrealistic.
EOSTorqueAngle| float | This configures the range where the EOS Torque will be applied
Friction| float | 0..1
Mass| float |
OverridePhysics(int) || overrides the flipper physics settings with pre defined settings defined under Preferences -> Physics Options. You can define up to 8 different physics settings for the table and the flippers. Save them to one of the 8 slots and by assigning the slot number to this OverridePhysics it overrides these settings. default=0 (means use table settings)
RampUp| float | Coil ramp up speed. Set to 0 for fastest flipper response.
Return| float |
Strength| float |
Scatter| float |
TimerEnabled|bool|
TimerInterval|int | set interval for triggering the timer (1 equals 1000 timer calls per second, 1000 equals 1 timer call per second, -1 makes it dependent on the FPS that a user can reach)
UserValue|any | can store any user defined value for re-use later-on

---

### Gate

#### Gate Methods

   Name | Description
---|---
Move(int dir, float speed, float angle) | dir(0/1)

#### Gate Read Only
   Name | Type | Description | Default
---|---|---|---
*CloseAngle| float |
*Height| float |
*Length| float |
*Material| string|
*Name| string|
*OpenAngle| float 
*Rotation| float |
*Surface| string||
*X| float |
*Y| float |
*Visible|bool

#### Gate Read/Write
   Name | Type | Description | Default
---|---|---|---
Collidable|bool
CurrentAngle| float | - only readable, it returns the current open angle
Damping| float | - 0..1
Elasticity| float |
Friction| float | 0..1
GravityFactor| float | - usually between 1..3
Open|bool
ShowBracket|bool
TimerEnabled|bool|
TimerInterval|int)| set interval for triggering the timer (1 equals 1000 timer calls per second, 1000 equals 1 timer call per second, -1 makes it dependent on the FPS that a user can reach)
UserValue|any | can store any user defined value for re-use later-on

---

### Kicker

#### Kicker Methods

   Name | Description
---|---
BallCntOver(int)
CreateBall()
CreateSizedBall(float radius)
CreateSizedBallWithMass(float radius, float mass)
DestroyBall(int ballId)
Kick(float angle, float speed, float inclination)
KickXYZ(float angle, float speed, float inclination, float x, float y, float z)
KickZ(float angle, float speed, float inclination, float heightz)

#### Kicker Read Only

   Name | Type | Description | Default
---|---|---|---
*Name| string|
*Color(OLE_COLOR)
*DrawStyle | KickerType | 0=Hidden, 1=Hole, 2=Cup, 3=Invisible
*HitHeight| float|
*Legacy| bool| if checked the kicker will behave as an old VP9 kicker that means no distraction of the ball if it doesn't hit straight the kicker center
*Orientation| float|
*Radius| float|
*Surface| string|
*X| float |
*Y| float |

#### Kicker Read/Write
   Name | Type | Description | Default
---|---|---|---
Enabled| bool|
Fall Through| bool| if checked the ball will fall through the surface assigned to the kicker, only if the surface is higher than the playfield
HitAccuracy| float| defines the accuracy how fast the ball gets caught when rolling over the kicker center (0.0-1.0)
LastCapturedBall  ||returns an instance to the last captured ball or the current captured ball. If no ball was captured before or was destroyed before an error message will be displayed.
Scatter| float|
TimerEnabled| bool|
TimerInterval |int | set interval for triggering the timer (1 equals 1000 timer calls per second, 1000 equals 1 timer call per second, -1 makes it dependent on the FPS that a user can reach)
UserValue|any | can store any user defined value for re-use later-on

---

### Light

#### Light Methods

   Name | Description
---|---
Duration(int startState, int durationTime, int endState) | Starts a light in startState and leaves it into that state for the amount of milliseconds defined by durationTime until the light switches to the endState e.g.: light1.Duration 2, 1000, 1 (light starts to blink for 1000ms and then switches to ON)

#### Light Read Only

   Name | Type | Description | Default
---|---|---|---
*Image| string|
*Name| string|
*Shape | Shape | 0=Circle, 1=Custom
*Surface| string|
*X| float |
*Y| float |

#### Light Read/Write
   Name | Type | Description | Default
---|---|---|---
BlinkPattern| string| off/on pattern for the light to use while the interval is going: 1 is ON, 0 is OFF, for example 111000111000101010101
BlinkInterval|int|
BulbModulateVsAdd| float| blends between modulating and additive when bulb is enabled (0..1)
BulbHaloHeight| float| sets the halo height of a bulb light
Color| OLE_COLOR| 'normal' color
ColorFull| OLE_COLOR| full brightness color
Bulb| bool|
DepthBias| float|
FadeSpeedUp| float| speed to fade into on state
FadeSpeedDown| float| speed to fade into off state
Falloff| float|
FalloffPower| float|
FPS that a user can reach)
ImageMode| bool| if true, passthrough Image (as if it would be fully emissive), otherwise light image with global lighting using the attached Surface material
Intensity| float| sets the lights brightness/emission
IntensityScale| float| sets the lights brightness/emission scale, so that one can fade in/out all affected lights with the same scaling factor
ShowBulbMesh| bool|
ShowReflectionOnBall| bool| in bulb mode, en/disable the reflection of the bulb on balls
State|LightState | 0=Off, 1=On, 2=Blinking
StaticBulbMesh| bool| 
ScaleBulbMesh| float|
TransmissionScale| float| sets the light scale for transmission, f.e. through playfield plastics or transparent ramps that are placed above the bulb light
TimerEnabled| bool|
TimerInterval |int | set interval for triggering the timer (1 equals 1000 timer calls per second, 1000 equals 1 timer call per second, -1 makes it dependent on the 
UserValue|any | can store any user defined value for re-use later-on
Visible| bool|

---

### Plunger

#### Plunger Methods

   Name | Description
---|---
CreateBall(IBall **ball) | create a new ball located at the tip of the plunger
Fire() | fire the plunger from the current position (for an auto-plunger, immediately pulls back all the way and fires with full strength)
MotionDevice() | returns a non-zero integer with the type of special input device attached, or 0 if none is attached (1=Pinball Wizard, 2=Ultracade, 3=SideWinder, 4=VirtuaPin plunger kit, 5=Generic/other)
Position() | returns a float (0 to 25) with the current position of the (mechanical or digital) plunger
Pullback() | start retracting the plunger at the speed given by PullSpeed; continues automatically until Fire() is called

#### Plunger Read Only

   Name | Type | Description | Default
---|---|---|---
*AnimFrames| int|  Flat style only: the number of animation frames in the Image; the image must be arranged with all of the frames lined up horizontally, all the same size, with the fully forward image in the leftmost cell
*AutoPlunger| bool|  if set, this is a solenoid launcher rather than a traditional plunger
*Color| OLE_COLOR|  surface color for 3D rendering; used only if no texture is specified via Image
*Image| string|  image used as texture for the 3D styles or as animation cell(s) for the flat style
*MechPlunger| bool|  true if this simulation plunger can be controlled by a mechanical plunger input device attached to the system; if set, the ParkPosition is used as the rest position
*Name| string|  name of the object for scripting references
*PullSpeed| float|  speed of retraction when Pullback() is called (for pulling via keyboard interface)
*RingDiam| float|  Custom type only: the diameter of the e-ring in the on-screen rendering, as a fraction of the Width setting
*RingGap| float|  Custom type only: the distance between the tip and the e-ring in the on-screen rendering
*RingThickness| float|  Custom type only: the thickness of the e-ring in the on-screen rendering
*RodDiam| float|  Custom type only: the drawing diameter of the rod as a fraction of the Width setting
*SpringDiam| float|  Custom type only: the diameter of the spring coil in the on-screen rendering, as a fraction of the Width setting
*SpringEndLoops| float|  Custom type only: the number of stationary (non-stretching) "end loops" the spring makes in the on-screen rendering (fractional values are allowed)
*SpringGauge| float|  Custom type only: the thickness of the spring wire in the on-screen rendering
*SpringLoops| float|  Custom type only: the number of loops the spring makes around the rod within the displayed extent (fractional values are allowed, as partial loops are perfectly sensible)
*Shape| string|  Custom type only: a list of Distance/Diameter pairs separated by semicolons specifying the shape of the tip, as a series of circles centered on the plunger axis
*Surface| string|  object for aligning vertical position of plunger; sits atop playfield if this is left blank
*Type| int|  the visual style of the plunger drawn on-screen
*Visible| bool|  true if plunger is visible on-screen
*Width| float|  on-screen width of the plunger on each side of the center-line (this acts like a radius, so the actual drawing width is twice this value)
*X| float|  x position of center-line of plunger
*Y| float|  y position of back end of plunger
*ZAdjust| float|  moves the on-screen rendering vertically up (positive values) or down (negative values) from the default position determined by the Surface alignment

#### Plunger Read/Write
   Name | Type | Description | Default
---|---|---|---
FireSpeed| float|  speed of firing when Fire() is called or mechanical plunger is released; controls both animation speed and ball launch strength
MechStrength| float|  controls strength of coupling to mechanical plunger position; using about the same value as FireSpeed usually works best
MomentumXfer| float|  adjustment factor for launch strength; multiplied into final ball speed calculation on each launch, so 1.0 has no effect, and 2.0 doubles the strength
ParkPosition| float|  distance back from fully forward position of resting position (as a fraction of the total length); used only if MechPlunger is enabled
Stroke| float|  total travel distance; also controls the on-screen length (which is slightly longer than the travel distance, to accommodate the non-moving parts)
ScatterVelocity| float|  amount of randomness added to ball velocity on firing
TimerEnabled| bool|  enable the plunger's script timer
TimerInterval| int|  interval for firing the plunger's script timer
UserValue|any | can store any user defined value for re-use later-on

---

### Primitive

#### Primitive Methods

** The following only applies to mesh primitives with an animation sequence

   Name | Description
---|---
PlayAnim(float startFrame, float speed) | start playing the sequence from 'startFrame' til the end with frame rate 'speed'
PlayAnimEndless(float speed)            | start playing the sequence in a loop with frame rate 'speed'
StopAnim()                              | stop the animation
ContinueAnim(float speed)               | continue a stopped animation with frame rate 'speed'
ShowFrame(float frameNr)                | show the mesh at frame 'frameNr', where 'frameNr' can also be a fractional frame number like 1.23. VP will interpolate between subframes.

#### Primitive Read Only

   Name | Type | Description | Default
---|---|---|---
*EnableStaticRendering|bool| if set the primitive is only rendered once (like walls) any dynamic changes later won't have an effect. This is useful for objects like posts or static toys, because this won't have an impact of the perfomance
*IsToy|bool| disables collision handling and all physics preprocessing completely. It overwrites the Collidable-flag and can't be used from within the script. This option is useful if you have real toys or static primitives which are never hitable at all and are just there for the 'looks'. | true
*Name|string|
*ReflectionEnabled|bool| |true
*Scatter|float|

#### Primitive Read/Write
   Name | Type | Description | Default
---|---|---|---
BackfacesEnabled|bool| default=false, if enabled will also show/render the backfacing triangles (if a transparent material is used)
BlendDisableLighting|float| 0..1, same as DisableLighting, but can blend between the two extremes
BlendDisableLightingFromBelow|float| 0..1, similar to DisableLighting, but will block light coming from below (e.g. from light elements)
Collidable|bool| enables/disables collision detection, this can be used from within the script.
DisableLighting|bool|
DrawTexturesInside|bool| textures the inside of the old standard primitive
Elasticity|float|
ElasticityFalloff|float|
Friction|float| |0..1 
HasHitEvent|bool| enables the support for a hit event in the script (it's the same as for walls)
HitThreshold|float| holds the current hit threshold if a ball has hit the primitive
Image|string| texture name
NormalMap|string| normal map name
RotAndTra0 or RotX|float| rotates the primitive around it's X axis
RotAndTra1 or RotY|float| rotates the primitive around it's Y axis
RotAndTra2 or RotZ|float| rotates the primitive around it's Z axis
RotAndTra3 or TransX|float| translates the primitive along it's X axis
RotAndTra4 or TransY|float| translates the primitive along it's Y axis
RotAndTra5 or TransZ|float| translates the primitive along it's Z axis
RotAndTra6 or ObjRotX|float| rotates the X axis of the primitive's local coordinate system. This is used to orientate the object first, after that RotXYZ will rotate the object around this rotated coordinate system
RotAndTra7 or ObjRotY|float| rotates the Y axis of the primitive's local coordinate system. This is used to orientate the object first, after that RotXYZ will rotate the object around this rotated coordinate system
RotAndTra8 or ObjRotZ|float| rotates the Z axis of the primitive's local coordinate system. This is used to orientate the object first, after that RotXYZ will rotate the object around this rotated coordinate system
SideColor|OLE_COLOR| sideColor of the old standard primitive (only valid if no image was set)
Sides|float| amount of sides for the old standard primitive
Size_X|float| X size
Size_Y|float| Y size
Size_Z|float| Z size
Threshold|float| hit threshold for firing the hit event
TopVisible|bool| toggle visibility
TopColor|OLE_COLOR| topColor of the old standard primitive (only valid if no image was set)
UserValue|any| can store any user defined value for re-use later-on
X|float| X position
Y|float| Y position
Z|float| Z position

---

### Ramp

#### Ramp Methods
None

#### Ramp Read Only
   Name | Type | Description | Default
---|---|---|---
*Name|string
*ReflectionEnabled|bool||true
*Scatter| float |
*Type|RampType| 0=Flat, 1=4Wire, 2=2Wire, 3=3WireLeft, 4=3WireRight, 5=Wire

#### Ramp Read/Write
   Name | Type | Description | Default
---|---|---|---
Collidable|bool
Elasticity| float |
Friction| float | | 0..1
HasHitEvent|bool| enables the support for a hit event in the script (it's the same as for walls)
HasWallImage|bool| apply image to walls
HeightBottom| float |
HeightTop| float |
Image| string| texture name
ImageAlignment|RampImageAlignment | 0=ImageModeWorld, 1=ImageModeWrap
LeftWallHeight| float |
RightWallHeight| float |
Threshold| float | hit threshold for firing the hit event
UserValue|any |can store any user defined value for re-use later-on
Visible|bool
VisibleLeftWallHeight| float |
VisibleRightWallHeight| float |
WidthBottom| float |
WidthTop| float |

---

### Rubber

#### Rubber Methods
None

#### Read Only

   Name | Type | Description | Default
---|---|---|---
*Name|string|
*Collidable|bool|
*EnableShowInEditor|bool| if set one cannot adjust the control points of the rubber but the rotation angles are applied to the rubber mesh in the editor.
*EnableStaticRendering|bool| if set the rubber is only rendered once (like walls) any dynamic changes later won't have an effect. This is useful for static rubbers like rubbers on posts. 
*HasHitEvent|bool|
*HitHeight|float|defines the collision height of a rubber (default is 25.0 midpoint of a standard ball with size 50)
*Material|string|
*ReflectionEnabled|bool| |true
*Scatter|float|
*Thickness|int|

#### Rubber Read/Write
   Name | Type | Description | Default
---|---|---|---
Elasticity|float|
ElasticityFalloff|float|
Friction|float| | 0..1
Image|string| texture name
RotX|float| angle to rotate the whole rubber around the X axis 
RotY|float| angle to rotate the whole rubber around the Y axis 
RotZ|float| angle to rotate the whole rubber around the Z axis 
TimerEnabled|bool|
TimerInterval|int| set interval for triggering the timer (1 equals 1000 timer calls per second, 1000 equals 1 timer call per second, -1 makes it dependent on the FPS that a user can reach)
UserValue|any | can store any user defined value for re-use later-on
Visible|bool|

---

### Spinner

#### Spinner Methods
None

#### Spinner Read Only
   Name | Type | Description | Default
---|---|---|---
*AngleMax| float|
*AngleMin| float|
*CurrentAngle| float| only readable
*Height| float|
*Length| float|
*Material| string|
*Name| string|
*ReflectionEnabled| bool| | true
*Rotation| float|
*Surface| float|
*ShowBracket| bool|
*Visible| bool|
*X| float|
*Y| float|

#### Spinner Read/Write
   Name | Type | Description | Default
---|---|---|---
Damping| float| | 0..1
Elasticity| float|
Image| string|
TimerEnabled| bool|
TimerInterval| int| set interval for triggering the timer (1 equals 1000 timer calls per second, 1000 equals 1 timer call per second, -1 makes it dependent on the FPS that a user can reach)
UserValue|any| can store any user defined value for re-use later-on

---

### Target

#### Target Methods
None

#### Target Read Only
   Name | Type | Description | Default
---|---|---|---
*Name|string|
*Collidable|bool|
*HasHitEvent|bool|if set a hit event is fired when the ball hits the drop/hit target without animation. An additional dropped/raised event is fired for drop targets after the mesh animation is over.
*Material|string
*Orientation|float|angle to rotate the whole target around the Z axis 
*ReflectionEnabled|bool||true
*ScaleX|float
*ScaleY|float
*ScaleZ|float
*Scatter|float|
*X|float
*Y|float
*Z|float

#### Target Read/Write
   Name | Type | Description | Default
---|---|---|---
BlendDisableLighting|float| same as DisableLighting, but can blend between the two extremes |  0..1
BlendDisableLightingFromBelow|float| similar to DisableLighting, but will block light coming from below (e.g. from light elements) |  0..1
DisableLighting|bool|
DropSpeed|float| the speed how fast the drop or hit target will move 
Elasticity|float|
ElasticityFalloff|float|
Friction|float| | 0..1
Image|string| texture name
IsDropped|bool|  can only be used for drop targets if the drop target is raised or dropped
HitThreshold|float| holds the current hit threshold if a ball has hit the target
RaiseDelay|int|  defines a delay in milliseconds after the dropped target will start to raise to it's normal position
TimerEnabled|bool| each target has a build-in timer which can be enabled by setting this to 1
TimerInterval|int| set interval for triggering the timer (1 equals 1000 timer calls per second, 1000 equals 1 timer call per second, -1 makes it dependent on the FPS that a user can reach)
UserValue|any|   can store any user defined value for re-use later-on
Threshold|float|  hit threshold for firing the hit event
Visible|bool|

---

### Textbox

#### Textbox Methods
None

#### Textbox Read/Write

   Name | Type | Description | Default
---|---|---|---
Alignment
Height|float
IsTransparent | bool/int
BackColor | OLE_COLOR
DMD |bool |enable DMD image via script connection
Font
FontColor | OLE_COLOR
IntensityScale |float | scales the color of the textbox
Name |string |
Text |string
TimerEnabled | bool/int
TimerInterval |int | set interval for triggering the timer (1 equals 1000 timer calls per second, 1000 equals 1 timer call per second, -1 makes it dependent on the FPS that a user can reach)
UserValue | any | can store any user defined value for re-use later-on
Visible |bool|
Width|float
X|float
Y|float

---

### Timer

#### Timer Methods
None

#### Timer Read Only

   Name | Type | Description | Default
---|---|---|---
*Name|string|

#### Timer Read/Write
   Name | Type | Description | Default
---|---|---|---
Enabled|bool
Interval|int| set interval for triggering the timer (1 equals 1000 timer calls per second, 1000 equals 1 timer call per second, -1 makes it dependent on the FPS that a user can reach)
UserValue|any| can store any user defined value for re-use later-on

---

### Trigger

#### Trigger Methods
   Name | Description
---|---|
BallCntOver(int value)
DestroyBall(int ballId)

#### Trigger Read Only
   Name | Type | Description | Default
---|---|---|---
*Enabled| bool|
*Name| string|
*Radius| float|
*TriggerShape(Shape) - 0=None, 1=Wire, 2=Star
*Visible| bool|
*X| float|
*Y| float|

#### Trigger Read/Write
   Name | Type | Description | Default
---|---|---|---
AnimSpeed| float|
HitHeight| float|
Rotation| float|
Surface| string|
TimerEnabled| bool|
TimerInterval| int|set interval for triggering the timer (1 equals 1000 timer calls per second, 1000 equals 1 timer call per second, -1 makes it dependent on the FPS that a user can reach)
UserValue| any|can store any user defined value for re-use later-on
WireThickness| float|This option is only used for wire shape triggers. The thickness is a factor to scale the wire 0=normal thickness(default). To make it thicker use values like 0.5, 1, 1.5, 2...

---

### Wall

#### Wall Methods
   Name | Description
---|---|
PlaySlingshotHit() | if the wall has slingshots defined, a call to this function will play the hit animation without triggering the actual hit event.

#### Wall Read Only

   Name | Type | Description | Default
---|---|---|---
*Name|string
*HasHitEvent|bool|
*Image|string | texture name
*SideColor|OLE_COLOR|
*HeightBottom|float|
*HeightTop|float|
*FaceColor|OLE_COLOR|
*CanDrop|bool|
*DisplayTexture|bool|
*SideImage|string
*Visible|bool|
*SideVisible|bool|
*SlingshotColor|OLE_COLOR|
*SlingshotAnimation|bool|
*FlipbookAnimation|bool|
*Scatter|float|
*ReflectionEnabled|bool| |true

#### Wall Read/Write
   Name | Type | Description | Default
---|---|---|---
Collideable|bool|
BlendDisableLighting|float| 0..1, same as DisableLighting, but can blend between the two extremes
BlendDisableLightingFromBelow|float| 0..1, similar to DisableLighting, but will block light coming from below (e.g. from light elements)
Disabled|bool|
DisableLighting|bool|
Elasticity|float|
Friction|float| 0..1
IsBottomSolid|bool|
IsDropped|bool|
SlingshotThreshold|float|
Threshold|float|
TimerEnabled|bool|
TimerInterval|int| set interval for triggering the timer (1 equals 1000 timer calls per second, 1000 equals 1 timer call per second, -1 makes it dependent on the FPS that a user can reach)
UserValue|any|can store any user defined value for re-use later-on