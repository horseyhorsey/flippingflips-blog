---
author: "Flips-Admin"
title: "🏬 Decals Part 1. Transparent images from Inkscape"
date: 2020-04-18T12:00:06+09:00
description: "How to create and use decals with sketched out shots on a visual pinball blueprint using Inkscape to generate transparent .png ready for visual pinball."
draft: false
image: /images/guides/design/bp_shots_vp.png
hideToc: false
enableToc: true
enableTocContent: false
author: flips-admin
authorEmoji: 🌱
categories:
- guides
- visual pinball
tags: 
- beginner
- blueprint
- cosmetic
- decal
- design
- inkscape
---

---

> A decal is one way of using images. We'll create a `very` rough layout by hand in [Inkscape](https://inkscape.org/release/inkscape-1.0/)

---

## Shot layout

---

### Create a shot layout in Scalable Vector Graphics

- Open a blueprint that was exported from `Visual Pinball` into `Inkscape` (not import)
- Keep the file dimensions when it asks
- Create bezier lines on a seperate layer for shot angles
- When happy hide the `Blueprint` layer
- Export the image as `Page`, checking the dimensions are in `px` and were the same dimesions as the blueprint.

### Example layout

[bp_shot_layout.svg](/images/guides/design/bp_shot_layout.svg)
Save as to open with `Inkscape` or something that can open `SVG` 

[bp_shot_layout.png](/images/guides/design/bp_shot_layout.png)
Shot layer exported `.png` 

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 20%; max-height: 20%;">
        <img src="/images/guides/design/ink_export_snap.png" alt="Inscape ready to export"/>
    </div>
</div>
<br>

---

## Decal

---

### Create decal

---

- Create a `decal` in `visual pinball`. Set its dimensions to `952x2162`
- Assign to a layer away from the bottom `Layer 11`
- Lock the layer so it cannot be moved accidentley
- Set the `X` and `Y` positions to `0`
- Offset the decal to cover the playfield `X:476 Y:1081` (half the lengths)

### Assign image to decal
- Assign a material to the `decal` otherwise it will look faded
- Import the image `.png` and select it from the decal
- Run the table with `F5` or `F6` to see the results

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 45%; max-height: 30%;">
        <img src="/images/guides/design/bp_shots_vp.png" alt="Inscape ready to export"/>
    </div>
</div>
<br>

---
