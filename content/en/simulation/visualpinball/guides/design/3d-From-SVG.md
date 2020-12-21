---
author: "Flips-Admin"
title: "🏗️ 3D Part 5 - Blender SVG - 3D Text"
date: 2020-05-19T16:00:00+00:00
description: "Make meshes from SVG and import to Visual Pinball"
draft: false
image: /images/guides/design/3d-text-inkscape-blender6.jpg
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
- graphics
- inkscape
- primitive
- svg
---

Blender can import `svg`, so we could use this for lots of things like 3D text, making plastics layer from blueprints.

We wanted some 3D text in a game that would stick out like the Hollywood sign. Seeing as this process has an extra step from objects with paths it was worth documenting.

---

## Inkscape Text

---

We've opened `Inkscape` and created some text for our game. 

> The text can be any `font size` as you'll be able to resize the mesh in `Blender`

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/3d-text-inkscape.jpg" alt="Text created in inkscape"/>
    </div>
</div>
<br>

For text we need to use `Path > Object to Path` or `Shift+Ctrl+C`.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/3d-text-inkscape-path.jpg" alt="Inkscape convert text to path"/>
    </div>
</div>
<br>

Save as `SVG` somewhere we can load into `Blender`

---

## Blender SVG

---

We've created a new blender scene and `deleted` the `default cube` as what seems to be standard issue.

Activate Top Orthographic `Num5` `Num7` and `File > Import > Scalable Vector Graphics` and select our text `svg`.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/3d-text-inkscape-blender1.jpg" alt="Loaded SVG into Blender"/>
    </div>
</div>
<br>

Our imported text is all on separate paths. We don't want to adjust individual letters so we can join them by selecting all the letter and `Ctrl+J` to join.

After this we want to center the origin. `Right click > Set origin > Geometry To Origin`

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/3d-text-inkscape-blender2.jpg" alt="Loaded SVG into Blender"/>
    </div>
</div>
<br>

---

## Create mesh and edit

---

You can scale it now at this point but we can't change the `thickness`.

We need to convert this to a mesh first, this is done in `Blender 2.8` in `object mode` from the menu `Object > Convert > Mesh From Curve`.

> Prior versions `Alt+C` to get the menu and convert.

---

## Extruding

---

- Use `Num1` to go into `Front` view.
- `Tab` to edit mode and select all `A`
- Use `E` to extrude and move the mesh up

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/3d-text-inkscape-blender3.jpg" alt="Extruded text"/>
    </div>
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/3d-text-inkscape-blender4.jpg" alt="Extruded text"/>
    </div>
</div>
<br>

---

## UVs

---

Before this is usable in VP we'll need to create a UV map. 

- `Tab` to edit mode, select all `A`
- `UV > Smart UV Project`

You can see in the image below the letters have been unwrapped.

These letters can be flipped if needed in the `UV Selection Mode` `Island` by right click clicking and using the mirror options.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/3d-text-inkscape-blender5.jpg" alt="Flipping mapped faces"/>
    </div>
</div>
<br>

## Export to Visual Pinball

Before exporting we used `Num3` to access the `Right View` then `R` and `x` `90` to rotate it so it's facing the front.

Using the VP blender export options from the first guide we save our model, then import the mesh from a `Primitive` in Visual Pinball`.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 75%; max-height: 40%;">
        <img src="/images/guides/design/3d-text-inkscape-blender6.jpg" alt="The 3D svg inside Visual Pinball"/>
    </div>
</div>
<br>

> Quick test with a `RubberWhite` material.

---