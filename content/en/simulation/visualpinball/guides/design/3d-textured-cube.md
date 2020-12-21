---
author: "Flips-Admin"
title: "🏗️ 3D Part 3 - Texture the Blender cube and import to Visual Pinball"
date: 2020-05-15T11:00:00+00:00
description: "Map a texture to the default Blender cube and import into Visual Pinball"
draft: false
image: /images/guides/design/3d-texture-cube-5.jpg
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

> TODO

---

## Guide Outline

1. [Export UV map](#export-uv-map)
2. [Edit UV map](#basic-edit-uv-map)

---

### Export UV map

---

Open up `Blender` and select the default cube. Click the `UV Editing` tab and you should see an already mapped out cube.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 35%; max-height: 40%;">
        <img src="/images/guides/design/3d-texture-cube-1.jpg" alt="UV mapping of cube"/>
    </div>
</div>
<br>

> When we `Face` select the cube in `Edit` mode we can see each square that is mapped to the cube.

> The `bottom square` is the top of the `cube` and the `top square` is the bottom.

Select all the faces in the `UV` with `A`. Push `R` then `-90` and `Enter` to confirm to rotate the mapping.

Click the `UV > Export UV Layout` menu. Change the options in the `Export UV` options pane if you want. We'll change ours to `256x256`

We're going to use `Svg` here but you could use any image format from `Blender` at this stage. Save the file as `Cube.svg`.

---

### Basic Edit UV Map

---

We've opened the `svg` into `Inkscape` and filled out the squares with numbers.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 35%; max-height: 40%;">
        <img src="/images/guides/design/3d-texture-cube-2.jpg" alt="Numbers on UV map"/>
    </div>
    <div class="" style="max-width: 35%; max-height: 40%;">
        <img src="/images/guides/design/cube.png" alt="Exported Edited UV map"/>
    </div>
</div>
<br>

### Map Texture to Blender material

---

In `Object mode` select the cube then click the `Shading` tab.

Delete the `Principled BSDF` and add a new one. `Add > Shader > Diffuse BSDF`

Add an `Image Texture`. `Add > Texture > Image Texture`. 

Connect the `Image Texture` nodes `Color` to the `BaseColour` of the `Shader` then connect the `BSDF` to the surface of the `Material`

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 65%; max-height: 40%;">
        <img src="/images/guides/design/3d-texture-cube-3.jpg" alt="Numbers on UV map"/>
    </div>
</div>
<br>

* From the `Image Texture` drop down select the `cube.png` and we'll see it textured in view.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 65%; max-height: 40%;">
        <img src="/images/guides/design/3d-texture-cube-4.jpg" alt="Numbers on UV map"/>
    </div>
</div>
<br>

### Import to Visual Pinball

Using the export preset we created in [previous]() guide we export wavefront `.obj` to `cube.obj`.

* In Visual Pinball import the numbered `cube.png`
* Create a primitive in Visual Pinball and `Import Mesh` on the `cube.obj`
* Assign a material and select the `cube.png` from the image drop down.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 65%; max-height: 40%;">
        <img src="/images/guides/design/3d-texture-cube-5.jpg" alt="Textured model in Visual Pinball"/>
    </div>
</div>
<br>





