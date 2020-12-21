---
author: "Flips-Admin"
title: "🏗️ FP to VP SciFi Classic Part 3 - Script converting"
date: 2020-05-21T13:00:00+00:00
description: "Add the script to the game"
draft: false
image: /images/guides/design/fpconvert/scifi-vp-lighting.jpg
hideToc: false
enableToc: true
enableTocContent: false
author: flips-admin
authorEmoji: 🌱
categories:
- guides
- visual pinball
tags: 
- 3D
- beginner
- blender
- design
- future pinball
- graphics
- primitive
- ramp
- wire
---

---

## SciFi Classic


### Issues

* Add `Trigger` named `DummyTrigger`
* Add vars for `BulbOn, BulbOff, BulbBlink`
* Replace `FlashForMs` with `Light.Duration startState, duration, endState`
* Lights need naming
* `UserData` should be replaced with `UserValue`
*  No `Set` methods for timers
* `Expired` should be replaced with `_Timer` on methods
* `PlayMusic` doesn't have channels in VP
* `EffectMusic` doesn't exist
* `Dropped` to `IsDropped`

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fpconvert/scifi-orn-holes-blend.jpg" alt="Selecting all holes in blender"/>
    </div>
</div>
<br>