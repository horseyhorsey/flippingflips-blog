---
author: "Flips-Admin"
title: "🏗️ FP to VP SciFi Classic Part 2 - Playfield mesh and holes"
date: 2020-05-20T19:00:00+00:00
description: "Creating Visual Pinball playfield mesh with holes"
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

---

For this guide we'll show one way of cutting holes into your playfield.

## Blender

### Selecting objects to cut from

---

With the table open in `Blender`:

- `Z` to view wire frame to make it easier to see what we need to select
- `Num7` to get into `Top` `Ortho`
- Select all the `ornholes` you need.
- `Ctrl-J` to join the holes
- We've renamed the join to `!OrnHoles` for easy access in the tree

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fpconvert/scifi-orn-holes-blend.jpg" alt="Selecting all holes in blender"/>
    </div>
</div>
<br>

---

### Using modifier to cut

---

- `Z` to come out of `wireframe` and select the `playfield` mesh on its own.
- In the modifiers tab, add a new `Boolean` modifier.
- Select `Difference`
- Select the `!OrnHoles`
- We can apply the modifier when happy

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fpconvert/scifi-orn-holes-modified.jpg" alt="Blender boolean modifier"/>
    </div>
</div>
<br>

### Export layers

We want to also include our `Ornament Holes` as well as the `Playfield` mesh, but not joined as this isn't supported.

- Select the joined `!OrnHoles` and export this for a layer in Visual Pinball.
- Export the `Playfield` Mesh

---

## Import to Visual Pinball

### Playfield mesh

- Create a new `primitive`, this must be named `playfield_mesh`.
- Make sure to use a material like `PlayfieldWithImage`.
> Note the material should be set on the `Table > Playfield` options and not on this primitive.

### Ornaments

Insert layer as before with previous, nothing special.

> We created `3D` like insert by cutting holes from the lamps in Blender and offsetting the light lower than the playfield in Visual Pinball.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fpconvert/scifi-vp-lighting.jpg" alt="Gamewith holes and lighting"/>
    </div>
</div>
<br>