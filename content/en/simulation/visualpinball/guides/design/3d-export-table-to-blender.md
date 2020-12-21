---
author: "Flips-Admin"
title: "🏗️ 3D Part 1- Export VP table to Blender"
date: 2020-05-14T12:00:06+09:00
description: "How to use Blender for Visual Pinball"
draft: false
image: /images/guides/design/vp-blender-imported.jpg
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
- design
- graphics
- primitive
---

> Visual pinball 10+ is able to export the whole table as a wavefront .obj

---

## Guide Outline

1. [Export Table](#export-table)
2. [Load Table in Blender3D](#import-to-blender)

### Export Table

1. Export a table from Visual Pinball. `File > Export > Mesh`
2. If layers are hidden then these are not included in the exported mesh.

### Import To Blender

> If you don't have `Blender` installed it can be downloaded from [here](https://www.blender.org/download/)

1. In `Blender` create a new scene. `New > General`
2. Remove the default cube by selecting and deleting with the `Delete` key
3. Import the table `*.obj`. `File > Import > Wavefront Obj`
4. Before loading the model change the `Import OBJ` options so the table is the correct translation to work with.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 55%; max-height: 40%;">
        <img src="/images/guides/design/blender-import-options.jpg" alt="Blender options need changing otherwise its flipped"/>
    </div>
</div>

Forward: -Y Forward
Up:______-Z Up

5. Save these values as an `Operator Preset` named `vp-import` to use when importing VP again.
6. Double click the table object to load in the `Blender` file explorer.
7. Push `Num_7` to activate the top down view when model is loaded
8. Using the `Middle mouse button` `+` `Shift` to move or pan the view without holding `Shift`.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 45%; max-height: 30%;">
        <img src="/images/guides/design/vp-blender-imported.jpg" alt="Top down view of playfield in 3D"/>
    </div>
</div>




