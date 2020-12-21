---
author: "Flips-Admin"
title: "🏗️ Primitive - Inner cabinet Walls and Translite"
date: 2020-04-09T12:00:06+09:00
description: "How to add some inner walls and translite for visual pinball"
draft: false
image: /images/guides/design/walls-translite-vp.png
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
- cosmetic
- design
- graphics
- primitive
- translite
- wall
---

---

As a template already has an updated `Primitive` for walls, we'll use the blank template as a starter table [Link](/en/simulation/visualpinball/template/table/table-blank-stripped/#download)

---

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 20%; max-height: 20%;">
        <img src="/images/guides/design/walls-translite-vp.png" alt="Example game wood texture"/>
    </div>
</div>
<br>

## Guide Outline

[1. Find the primitive](#primitive)
[2. Editing texture](#texture)

---

## Primitive

---

Find the `WallsTranslite` primitive (multiple options):

- Use the `Select` option next to `Maginify`  (Quickest with less objects in table)
- Or Use `Ctrl+Shift+E` to open `Select Element` and find in list to select
- Or Just show `Layer 11` and select it from playfield.

---

### Copying the primitive

---

Not needed for this guide but if you want to use this in another table.

- `Ctrl+C` to copy with it selected
- `Ctrl+V` to paste in an existing open table.
- Adjust dimensions on the primitive on the `X,Y` to fit your table if is a different size.

---

## Texture

---

In the `Image Manager` (`F3`) there is a `WallsTranslite` image assigned to the primitive. 

The texture is `2048 x 2048` and displays `Left, Right, Back, Translite` and this can be exported from the `Image Manager`.

### Gimp edit tips

- Use fuzzy select with 150 threshold to select the panels
- Fill the selections a color `Edit > Fill with color`

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 20%; max-height: 20%;">
        <img src="/images/guides/design/walls-translite.png" alt="In the Gimp fuzzy selecting"/>
    </div>
</div>

- Edit the image as you see fit

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 20%; max-height: 20%;">
        <img src="/images/guides/design/walls-translite-edited.png" alt="In the Gimp fuzzy selecting"/>
    </div>
</div>
<br>


### Import texture

- Use the `Reimport From` in the `Image Manager` (`F3`) to load in edited `WallsTranslite` image.
- Next time you make edits to the image you can use the `Reimport` button to save time.

Run the game with `F5` to view the result or run `F6` when loaded use `Flippers` to adjust view.

---