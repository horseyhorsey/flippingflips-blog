---
author: "Flips-Admin"
title: "🏗️ 3D Part 4a - Future Pinball to Blender - Create to match Visual Pinball Dimensions"
date: 2020-05-18T16:00:00+00:00
description: "How to import Future Pinball tables to Blender, match dimensions and export some rails for a test"
draft: false
image: /images/guides/design/fp/fp-blender-scaled-to-vp-inplace.jpg
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
---

---

## Why match dimensions?

---

The reason we want to match the dimensions etc here is because we would like anything positioned in FP to match our VP table.

Most objects should be a straight import to Blender and export to VP in correct position and size.

---

## VP Blueprint

---

We start with our template again but the dimensions are the same as the default table.

|Width 	|Height
|---|---
952 	|2162
20.250” 	|46.0”
514.35mm|1168.4mm

With our `Visual Pinball` template open, hide all the layers with `#` button then select `1,2,10` as visible.

This is enough to create our blue print from

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/create-bp-for-fp.jpg" alt="getting bluprint ready for future pinball"/>
    </div>
</div>
<br>

Create a `Blueprint` that isn't `Solid` and save as `bmp`

> You could save `.png.` then convert to `.jpg` as the bitmaps are large.

---

## New Future Pinball Table

---

Create a new table in `Future Pinball` and set the dimensions to `514x1168` to match the VP dimensions.

> Future pinball rounds the values, so we choose nearest eg: 514

> If the dimensions aren't editable in the Future Pinball editor make sure to run as `Administrator`.

Use the menu `Table > Texture Manager > Import` to load our `Blueprint` then we can select it as a playfield and check `Display Pf in Editor`.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/bp-in-fp.jpg" alt="getting blueprint ready for future pinball"/>
    </div>
</div>
<br>

Move FP objects roughly into position and we have same as Visual Pinball.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/vp-fp-matched.jpg" alt="Future Pinball table adjusted to fit VP blueprint"/>
    </div>
</div>
<br>

> You may not see the playfield like we did when table is running until you `Preferences > Editor Options > Uncheck Load Image in Editor` then restart `Future Pinball`.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/vp-fp-matched-pf.jpg" alt="Future Pinball with Visual Pinball blueprint"/>
    </div>
</div>
<br>

---

### Download 

---

[FuturePinball Template](/dl/fp/fflips-blank-vpsize.7z)

---

## Blender

---

### Create mesh from VP

---

We have exported the Visual Pinball table as `obj` with just `Layer 10` visible as this is enough for the boundries to match.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/export-vp-obj.jpg" alt="Exporting Layer 10 from Visual Pinball"/>
    </div>
</div>
<br>

---

### Import Future Pinball Table

---

Using `Blender 2.7` import the `Future Pinball` table using the `add-on` from the `File > Import` menu.

Push `Num7` to activate top down view in `Ortho` `Num5`. Select all objects with `a`.

We can scale it up to match `Visual pinball` by pushing `S` to scale then `1.85` and `Enter` to confirm.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/fp-blender-scaled-to-vp.jpg" alt="Scaling Future Pinball to Visual Pinball in Blender"/>
    </div>
</div>
<br>

Still in `Top view` we can push `G` to move it. We move into place matching the `0,0` with the corner of the playfield.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/fp-blender-scaled-to-vp-inplace.jpg" alt="Visual pinball with future pinball in Blender"/>
    </div>
</div>
<br>

---

### Import the VP obj as layer

---

We can do this just to quickly check it fits. We import the object from the `Layer 10` we did previously on this page and making sure to select the preset we saved to import `Visual Pinball` objects.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/fp-vp-matched-blender.jpg" alt="Close match in VP and FP"/>
    </div>
</div>
<br>

We should be good to go now and when imported to Visual Pinball there should be minor tweaking in Visual Pinball if any for 3D positioning.

---

### Exporting the apron rails

---

We've undone the step of importing the VP object and just have our FP layers. We'll have a pop at doing the rails above the apron.

We'll join them so we can export as one mesh, material with a UV map.

---

#### Rails - Join, Convert to mesh add UV

---

> Visual pinball will not take the `.obj` without a UV mapped.

Select the rails on top of the apron then do the following to `join` and create a `UV Map`:

- `Ctrl+J` to join the objects. 
- `Alt+C > Convert to mesh`
- `Tab` to edit mode, `A` select all
- `Mesh > UV Unwrap > Unwrap`

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/blend-selected-fp-apron-rails.jpg" alt="Apron rails selection"/>
    </div>
</div>
<br>

---

## Import to Visual Pinball

---

We've created a new primitive and placed on the table at random and named `apron_rails_prim`.

Import the mesh with default options.

- Set the `XSize, YSize, ZSize` from `100` to `1`. 
- Set the `X,Y` position to `0`

When run the game the rails should be "roughly" there.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/apron-rails-from-fp.jpg" alt="Future Pinball rails in Visual Pinball"/>
    </div>
</div>
<br>

> Static objects (like the rails) are good this way but when you're wanting to rotate primitives you would want a better center point / origin from blender

---