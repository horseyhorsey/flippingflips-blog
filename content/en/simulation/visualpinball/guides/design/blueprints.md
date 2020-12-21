---
author: "Flips-Admin"
title: "🧬 Playfield - Whitewoods from VP blueprints"
date: 2020-04-15T12:00:06+09:00
description: "How to use blueprints from Visual pinball edited with the GIMP to create a basic playfield whitewood"
draft: false
image: /images/guides/blueprint/vp_bp_loaded.png
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
- design
- graphics
- playfield
---

---

Using a blueprint from `Visual Pinball` gives us image dimensions to start with.

I've exported the `p1-beachwood.png` from the `File > New > Example Table` so it act as a `whitewood`

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 20%; max-height: 20%;">
        <img src="/images/guides/blueprint/p1-beachwood.png" alt="Example game wood texture"/>
    </div>
</div>
<br>

We'll use the blank template as a starter table [Link](/en/simulation/visualpinball/template/table/table-blank-stripped/#download)

---

## Guide Outline

[1. Create a blueprint](#create-the-blueprint)
[2. Editing blueprint](#editing-blueprint)
[3. Using the whitewood](#using-the-whitewood)

---

### Create the blueprint

Exports can be done via the `File Menu` by selecting `Export > Blueprint` and saving the image. 

Exported blueprint objects can be outlined or solid.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 20%; max-height: 20%;">
        <img src="/images/guides/blueprint/bp_all_layers.png" alt="Blueprint Outline - All Layers"/>
    </div>
    <div class="" style="max-width: 20%; max-height: 20%;">
        <img src="/images/guides/blueprint/bp_all_layers_solid.png" alt="Blueprint Solid - All Layers"/>
    </div>
</div>
<br>


We will need a bit better export, with less layers. 

Hide all layers with the `#` button and select our collidable layer `10`

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 20%; max-height: 20%;">
        <img src="/images/guides/blueprint/bp_hidden_layers.png" alt="Layers hidden"/>
    </div>
</div>
<br>

Export as a solid Blueprint

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 20%; max-height: 20%;">
        <img src="/images/guides/blueprint/bp_solid.png" alt="Blueprint solid final"/>
    </div>
</div>
<br>

---

### Editing blueprint

Import the image into an image editor of your choice. We'll use the [GIMP](https://www.gimp.org/downloads/) image editing software to do some basic edits.

Now we can draw, add text and images etc. in the space we have on the playfield.

`Open as Layers` on the `p1-beachwood` image and resize the `p1-beachwood` layer to fill the blueprint image. Next add some text and hide the blueprint layer.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 30%; max-height: 30%;">
        <img src="/images/guides/blueprint/gimp_layers.png" alt="Gimp layers"/>
    </div>
</div>
<br>

Export the image to use in Visual Pinball with `Export As` in `GIMP`
*You may want to save this as a `GIMP` `.xcf` to work on some more later.*

---

### Using the whitewood

Open the VP image editor from the menu or pushing `F3` and use the import button to select the exported image.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 30%; max-height: 30%;">
        <img src="/images/guides/blueprint/bp_import.png" alt="Imported Blueprint"/>
    </div>
</div>
<br>

Show the `Table Options` and select the new playfield from the dropdown. If the playfield image is hidden you can show from `View > Playfield / Backdrop`.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 30%; max-height: 30%;">
        <img src="/images/guides/blueprint/pf_loaded.png" alt="Loaded into playfield mesh"/>
    </div>
</div>
<br>

`F5` or better `F6` to run the the game and view.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 30%; max-height: 30%;">
        <img src="/images/guides/blueprint/vp_bp_loaded.png" alt="Running in Visual Pinball"/>
    </div>
</div>
<br>

---