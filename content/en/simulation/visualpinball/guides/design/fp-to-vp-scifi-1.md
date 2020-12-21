---
author: "Flips-Admin"
title: "🏗️ FP to VP SciFi Classic Part 1 - Converting FP layers to VP"
date: 2020-05-20T17:00:00+00:00
description: "How to convert tables from Future Pinball to Visual Pinball quick time."
draft: false
image: /images/guides/design/fpconvert/scifi-vp-playable-whitewood.jpg
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

For this guide we're going to convert the game that was shipped with Future Pinball on their website.

[Sci-Fi Classic ](https://futurepinball.com/download.html)

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fpconvert/scifi-classic.jpg" alt="SciFi Classic Future Pinball"/>
    </div>
</div>
<br>

```
Credits
----------
Table Design and Graphics by: Matt Ellis
Coding by: Christopher Leathley
Music by: Scott Haag
```

This game, as many others are unplayable for us in Future Pinball. The physics are that bad and if you want a simulation you will be frustated if you're used to playing any real world machine. We don't use the `physics hacks` some have created, as we find that these are no better.

Having been into the Future Pinball editor again recently writing these, the editor is pretty smart in comparison to Visual Pinball and some amazing work was done to this. In fact, we'll start using this A LOT more, especially for `guides` and `wires`.

---

## Import to Blender

---

Import the `SciFi` `.fpt` table into blender and save for quick reopening again if need to come back.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fpconvert/scifi-loaded_blend.jpg" alt="SciFi Classic in Blender"/>
    </div>
</div>
<br>

---

### Exporting `linked` layers

---

The quickest way to convert this is to export similar layers as one. eg. Selected all plastics exported as `plastics.obj`

All of these layers won't be `collidable` in `VP`. Fake walls assigned to physics mats and any ball interaction like `targets` and `bumpers` all done in VP.

---

#### Wanted object layers

---

We've quickly gone over the table and decided on what we would need as layers from this game.

* Apron
* Plastics
* Rubbers (ignore sling rubbers)
* Rubber Posts
* Metal Bolts
* Metal Brackets (Kickers)
* Metal Pegs
* Screws
* Screw Caps
* Star Posts
* Wooden guides
* Wire guides
* Wire Wall guides

---

#### Exporting object layers

---

Use the scaled `VP` export preset created in earlier guides.

> Note: `Wires \ Rubbers` need to be converted to mesh with an added UV before VP.

---

#### Selecting / Exporting Tips

---

* We found best to take each `layer` from top down and delete the whole blender selections as you go. eg. starting from selecting all the `screws` to `screw caps`
* When you delete for example and you notice you missed a piece of `plastic` then we can undo the delete, add to the selection and repeat.
* If you're using your own table then naming your objects in `FP`. Example: `Screw1`, `Screw2`, then you would be able to filter and select these saving time.
* In the scene tree at the bottom of the list is different icons, these will give you selection of the object origin.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fpconvert/scifi-blend-selectedplastics.jpg" alt="Selected all plastics ready for exporting"/>
    </div>
</div>
<br>

---

## Visual Pinball Import

---

We've started with our `blank stripped template` again and resized the playfield `dimensions` to a rough `954.5 x 1910`.

* Create a `Primitive` and name it `SciPlastics`
* Set all `Scales` to `1`. 
* Position `X, Y` to `0`
* Import the `SciPlastics.obj`
* Set material to `PlasticWithImage` or similar otherwise kickers will be viewed in front.

We can repeat this process now copying the `primitive` and only having to change the name, importing a new mesh, setting material and image.

---

### Make Table Flippable

---

We add in `fake` everything and set physics materials depending on the type.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fpconvert/scifi-vp-collidable-layers.jpg" alt="Visual Pinball collidable layers"/>
    </div>
</div>
<br>

We added:

* Imported `Apron, Playfield, Plastic` images after converting to `.png`
* GI with no cutouts and mapped to `GI` collection
* Gates (used same rotation as Future Pinball)
* Targets (drop and stand ups)
* Kicker (not enabled for now, it will get stuck without script to kick it)

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fpconvert/scifi-vp-editor.jpg" alt="Sci Fi all layers in Visual Pinball"/>
    </div>
</div>
<br>

---

### Testing

---

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fpconvert/scifi-vp-playable-whitewood.jpg" alt="Sci Fi Classic Visual Pinball screenshot"/>
    </div>
</div>
<br>

We can knock the ball around fine in this table, texures are missing etc but with not much time at all we have this flipping.

### Download

SciFi VP Example [Download](/dl/examples/fflips_scifi.7z)