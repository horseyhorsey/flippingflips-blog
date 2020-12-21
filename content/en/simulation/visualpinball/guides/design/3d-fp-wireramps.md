---
author: "Flips-Admin"
title: "🏗️ 3D Part 4b - Future Pinball wire ramps to VP"
date: 2020-05-18T17:00:00+00:00
description: "How to import Future Pinball wire ramps to Blender, convert to mesh and into Visual Pinball"
draft: false
image: /images/guides/design/fp/fp-wire-ramps-vp-player.jpg
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

## Create ramps in Future Pinball

---

We've created two ramps in `FP`. One ramp is just a connection `Vertical Up Kicker`

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/fp-wire-ramps-create.jpg" alt="Future Pinball creating wire ramps"/>
    </div>
</div>
<br>

---

### Wire ramp table

---

Future Pinball table [Download](/dl/fp/fflips-blank-vuk-vpsize.7z)

---

## Blender Edit Wire Ramp

---

- Import the `FP` table into `Blender 2.7`

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/fp-wire-ramps-blendloaded.jpg" alt="Future Pinball table loaded into Blender with wire ramps"/>
    </div>
</div>
<br>

- Select every part of the ramp with `Shift + Right Click`. Selecting all rings, guides.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/fp-wire-ramps-blend-selected.jpg" alt="Selected wire ramp parts"/>
    </div>
</div>
<br>


- `Alt + C` and convert to mesh.
- `Ctrl + J` to join the wire ramp as one
- `Tab` to edit mode and `A` to select all
- `Mesh > UV Unwrap` to create a UV map for VP

---

## Export to VP

---

Select the VP export presets we saved and change the scale to `1.85`.

Save as new export preset `vp-export-scaled-selection`.

---

## Use in VP

* Create a `primitive`
* Prim scales set to `1`.
* `x,y,z` to `0`
* Import mesh

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/fp-wire-ramps-vp-editor.jpg" alt="Wire ramp in Visual Pinball loaded into editor"/>
    </div>
</div>
<br>

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/fp-wire-ramps-vp-player.jpg" alt="Wire ramp in Visual Pinball loaded"/>
    </div>
</div>
<br>

### Collision

Make the `primitive` a `toy only` so it cannot be collided with. We would replace the collide layers with an invisible `VP Ramp`

---
