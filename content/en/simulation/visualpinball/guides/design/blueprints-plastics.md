---
author: "Flips-Admin"
title: "🧬 Plastics - Creating plastic layer from blueprints"
date: 2020-05-15T08:40:00+00:00
description: "How to use the Visual Pinball blueprints to create a plastics layer"
draft: false
image: /images/guides/blueprint/plastic-layer-pre-bp.jpg
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
- plastic
- wall
---

---

> We'll use the blank template as a starter table [Link](/en/simulation/visualpinball/template/table/table-blank-stripped/#download)

---

## Adding Visual Pinball plastics

---

Hide all layers except `Layer 5`, copy the `Left Slingshot` plastic and `Paste as` somewhere in the table.

Unlock the new plastic we copied and create some random plastics by duplicating and adjusting the `wall` points.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 20%;">
        <img src="/images/guides/blueprint/plastic-layer-pre-bp.jpg" alt="Vp Plastics layer"/>
    </div>
</div>
<br>

Export a solid blueprint.

> More about blueprint here. [Blueprints - Whitewood](/en/simulation/visualpinball/guides/design/blueprints/#create-the-blueprint)

---

## Remove playfield background

---

Open the image with `GIMP`. In the layers right click the `blueprint` and `Add Alpha Channel`

Use the `Fuzzy` select tool and select the white background and `Delete`. `Ctrl+Shift+A` to select `None`

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 20%;">
        <img src="/images/guides/blueprint/plastic-layer-alpha.jpg" alt="Plastics in the GIMP with background removed"/>
    </div>
</div>
<br>

---

## Add textures to plastics

---

Use the `Fuzzy` select tool and select any of the black plastic pieces. We'll select all the pieces.

Select a pattern.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 20%;">
        <img src="/images/guides/blueprint/plastic-layer-pattern.jpg" alt="GIMP pattern select"/>
    </div>
</div>
<br>

Use `Ctrl+;` to fill or use the `Edit > Fill Pattern`

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 20%;">
        <img src="/images/guides/blueprint/plastic-layer-pattern-fill.jpg" alt="GIMP pattern select"/>
    </div>
</div>
<br>

---

## Use in Visual Pinball

---

Use `Export As` from the `File` menu and import into Visual Pinball with `F3 (Image Manager)`

Select all the plastics in the layer and change the `Top Image` to our `plastics.png`.

Set the material of the walls to `Plastic` and we've also set `Collidable` and using a physics material `a_physics_Plastic`

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 20%;">
        <img src="/images/guides/blueprint/plastic-layer-imported.jpg" alt="GIMP pattern select"/>
    </div>
</div>
<br>

Run the game and check the result.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 20%;">
        <img src="/images/guides/blueprint/plastic-layers-vp.jpg" alt="GIMP pattern select"/>
    </div>
</div>
<br>

---