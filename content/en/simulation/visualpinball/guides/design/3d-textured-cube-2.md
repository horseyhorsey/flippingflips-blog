---
author: "Flips-Admin"
title: "🏗️ 3D Part 3b - Texture minecraft block"
date: 2020-05-15T12:00:00+00:00
description: "Create a new smaller texture and adjust UVs"
draft: false
image: /images/guides/design/3d-texture-cubeb-5.jpg
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

This is an extra guide to texturing the cube to show we can edit the UV and resuse.

## Create a new cube texture

Using the [GIMP] create an empty texture `1024x1024`. 

It's better to have image at multiples of 2. We can also use the empty space for textures in other meshes later on.

Add some minecraft blocks like so.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 35%; max-height: 40%;">
        <img src="/images/guides/design/3d-texture-cubeb-1.jpg" alt="UV mapping of cube"/>
    </div>
</div>
<br>

In `GIMP` `File > Export As` and save to `cube2.png`.

---

## Map new texture in Blender

Change the `Image Texture` in the `Shader` tab in `Blender` to the new `cube2.png`.

Our the `UV Editing` tab the UV mapping is now only showing a piece of the texture.

We are going to move the faces in place so we need to change the `Sticky Selection Mode` to `disabled` otherwise when we move faces some vertexes are attached.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 35%; max-height: 40%;">
        <img src="/images/guides/design/blender-sticky-selection.png" alt="Blender Sticky Select"/>
    </div>
</div>
<br>

Select the last face (which was number `6` `Top`). Push `G` and now we can move it into place.

Our texture blocks are not the perfect size against the mapping so pushing `S` we can scale it.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 75%; max-height: 40%;">
        <img src="/images/guides/design/3d-texture-cubeb-2.jpg" alt="Blender Sticky Select"/>
    </div>
</div>
<br>

> If you cannot see the texture mapped to the cube make sure the `viewport shading` is selected.

Move the other faces to the second texture and we have a block.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 75%; max-height: 40%;">
        <img src="/images/guides/design/3d-texture-cubeb-3.jpg" alt="Blender Sticky Select"/>
    </div>
</div>
<br>

## Using in Visual Pinball

Export the object from `Blender` the same as in the previous posts with the correct settings.

In Visual Pinball use `F3` to open the `Image manager` and import the `cube2.png`.

We'll replace our cube `primitive` with our new mesh with the `Import Mesh` button and assign the `cube2.png`

Before we run the table let's do something half fun with the block. Resize each side to `50`. Move the cube so it fits 4 x Visual Pinball grid squares.

Set the `Z` to be the size of the block `50`. The origin is in the center of the cube so it should be on the playfield.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 75%; max-height: 40%;">
        <img src="/images/guides/design/3d-texture-cubeb-4.jpg" alt="Blender Sticky Select"/>
    </div>
</div>
<br>

Now duplicate a few times to make some stacks.

> A good way to duplicate in this spot would be to `Ctrl+C` on the block.
> Then while hovering inside another Visual Pinball square use the `Context menu` on the keyboard and `Paste At`

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 75%; max-height: 40%;">
        <img src="/images/guides/design/3d-texture-cubeb-5.jpg" alt="Blender Sticky Select"/>
    </div>
</div>
<br>

<script type="text/vbscript">
Dim myNumber
myNumber = 7
If myNumber = 7 Then
	document.write("Lucky 7!")
End If
myNumber = 100343
If myNumber = 7 Then
	document.write("You're a winner!")
End If

</script>

