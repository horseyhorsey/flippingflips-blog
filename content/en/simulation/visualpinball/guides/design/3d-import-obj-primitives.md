---
author: "Flips-Admin"
title: "🏗️ 3D Part 2 - Import models created in Blender"
date: 2020-05-15T10:00:00+00:00
description: "How to use Blender for Visual Pinball"
draft: false
image: /images/guides/design/3d-add-cone-5.jpg
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
- primitive
---

> Visual pinball 10+ is able to import wavefront .obj models.

---

Following on from the previous guide have an imported table in `Blender` ready.

## Guide Outline

1. [Create blender object](#create-blender-object)
2. [Visual Pinball Primitive](#visual-pinball-primitive)

---

### Create blender object

---

* Add a `Cone` mesh. Give it a radius of `2m` and set the `Z` to `1m` to fit on the playfield.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 35%; max-height: 40%;">
        <img src="/images/guides/design/3d-add-cone-1.jpg" alt="Add a Cone mesh"/>
    </div>
        <div class="" style="max-width: 35%; max-height: 40%;">
        <img src="/images/guides/design/3d-add-cone-2.jpg" alt="Adjust the defaults"/>
    </div>
</div>
<br>


* With cone selected export the obj as it is
* Change the options and save as preset `vp-export-selection-only`

Name|Value
---|---|
SelectionOnly | Checked
Forward| -Y Forward
Up | -Z Up

* Save the `.obj` file to open with `Visual Pinball`

---

### Visual Pinball Primitive

---

* Create a primitive in Visual Pinball, and set the `X`, `Y` position to `0`
* With the primitive selected we can name this to `Cone`.
> Easy to lose track if not naming from `Primitive`
* Click `Import Mesh` button and load the object with default values.
* Nothing changed after loading so set the editor value to `1` so it's visible

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 55%; max-height: 40%;">
        <img src="/images/guides/design/3d-add-cone-3.jpg" alt="Adding a primitive Cone mesh"/>
    </div>
</div>
<br>

* Set the position of the object center of the table by halving the dimensions of the table.
* X = `476`, Y = `1081`
* Take note of the `X,Y,Z Size` is 100. 100 times the size of our original model.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 55%; max-height: 40%;">
        <img src="/images/guides/design/3d-add-cone-4.jpg" alt="View of Cone in Visual Pinball table"/>
    </div>
</div>
<br>

We have a bit of a monstrosity but we can see it translates great in the table and all we need to do is duplicate it.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 55%; max-height: 40%;">
        <img src="/images/guides/design/3d-add-cone-5.jpg" alt="Duplicate cones in Visual Pinball table"/>
    </div>
</div>
<br>

> Bride of Pinbot 3D (2020)





