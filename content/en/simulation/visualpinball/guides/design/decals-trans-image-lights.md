---
author: "Flips-Admin"
title: "🏬 Decals Part 2. 💡 Lamps"
date: 2020-04-20T12:00:06+09:00
description: "How to create lamp decals with Inkscape from Visual Pinball blueprints"
draft: false
image: /images/guides/blueprint/inkscape-decal-in-vp.png
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
- decal
- design
- graphics
- lamp
- light
- playfield
---

## Guide Outline

> In this guide we'll use the table template as a base table to work from but you can use any.

Download Template: [Starter Blank Template](/en/simulation/visualpinball/template/table/table-blank-stripped/#download)

---

### VP Blueprint

---

- Create a light on the table and assign to `Layer 3`. Set the light to `blinking`.
- Export the `Blueprint` with just the lights layer `3`, solid or filled.
- See [Blueprints](/en/simulation/visualpinball/guides/design/blueprints/#create-the-blueprint) on exporting blueprints from Visual Pinball

---

### Inkscape 

---

- Open the `Blueprint` with [Inkscape](https://inkscape.org/release/inkscape-1.0/) using `default import resolution`.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 20%; max-height: 20%;">
        <img src="/images/guides/blueprint/inkscape-open-blueprint.png" alt="Open in Inkscape"/>
    </div>
</div>

- In `Document Properties` we have the image dimensions assigned and page fitted to blueprint.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 20%; max-height: 20%;">
        <img src="/images/guides/blueprint/inkscape-blueprint-props.png" alt="Document properties set to blueprint image size"/>
    </div>
</div>

- Create two layers and assign the blueprint to the bottom.
- Create simple text over the light add a stroke if you please.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 20%; max-height: 20%;">
        <img src="/images/guides/blueprint/inkscape-decal-text.png" alt="Text in place of a light"/>
    </div>
</div>

- Hide the background layer and in `Export Area` select `Page` to export the whole page.
- `Export As` to select a path to export, then click `Export` to save the `.png`

---

### VP Decals

---

- Import the decals image into Visual Pinball in the Image Manager `F3`
- Create a decal the size of the table. See [Create Decal](/en/simulation/visualpinball/guides/design/decal-trans-image/#create-decal)
- Assign the new image to the decal from the dropdown
- Select a material that has opacity checked in it's properties
- Run the table to see the blinking ball save
- Push `Q` once to access the debug menu and select lights
<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 20%; max-height: 20%;">
        <img src="/images/guides/blueprint/inkscape-decal-in-vp.png" alt="Decal text on vp light"/>
    </div>
</div>

- Tweak to get some values you like from this `Lights` menu.
- Change materials on the decal layer to test

---

### Download

Table with decals applied
[fflips_decals_lights.7z](/dl/examples/fflips_decals_lights.7z)

---

