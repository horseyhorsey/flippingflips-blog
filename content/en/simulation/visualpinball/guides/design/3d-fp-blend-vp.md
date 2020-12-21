---
author: "Flips-Admin"
title: "🏗️ 3D Part 4 - Future Pinball to Blender"
date: 2020-05-18T13:00:00+00:00
description: "How to import Future Pinball tables to Blender"
draft: false
image: /images/guides/design/fp/imported-vuk-demo-2.8.jpg
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

## Blender setup

---

A script for Blender to import Future Pinball was made for the community of [GoPinball](http://www.gopinball.com/forum/index.php?sid=4c481a0bbf404c8807ddadb4f80506d1) and all others. It based on an implementation of `LvR` from [PinSimDB](http://www.pinsimdb.org/).

It will allow us to convert and import Future pinball into Blender.

---

### Issues

---

Unfortunatley this plugin doesn't work on `Blender 2.8`. We did try to update it but needed more than we wanted to get into.

---

### Blender 2.79b

---

We have 2.8 installed, so we have picked the `blender-2.79b-windows64.zip` from the list. 

> You won't be able to run multiple versions installed but a portable version works if this would be a second install.

Blender 2.79 [Downloads](https://download.blender.org/release/Blender2.79/).

---

### FP- AddOn

---

Everything about the Add-On is here. [FuturePinball_FPX](https://archive.blender.org/wiki/index.php/Extensions:2.6/Py/Scripts/Import-Export/FuturePinball_FPx/#Installation)

When we last checked the download wasn't working. It could've been removed because it's incompatible with 2.8, so use the following mirror provided.

#### Download
 [Mirror](/dl/fp/Addon-Fpx-File-io_scene_fpx.zip)

---

### Installing Add-On

---

Run `Blender 2.7` and select the menus `File > UserPreferences > Add-Ons > Install Add-On from File`.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/add-on-userprefs.jpg" alt="Install FP blender add-on"/>
    </div>
</div>
<br>

You can check to enable the plugin.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/add-on-install.jpg" alt="Future Pinball add-on installed"/>
    </div>
</div>
<br>

We also need to activate the `ms3d` add-on for Milkshape3D otherwise importing is greyed out in the File menu.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/add-on-install.jpg" alt="Milkshape 3D add-on installed"/>
    </div>
</div>
<br>

`Save` the user preferences for next load.

---

## Importing Future Pinball

---

### About Future Pinball

---

Future Pinball is a real time Pinball Development System created by `Christopher Leathley` in 2008. It allows you to design and play your very own pinball simulation in True real time 3D. It uses Advanced Physics to provide the best possible Simulation of a true to life pinball machine.

---

#### Download

---

Download @ [Future Pinball.com](https://futurepinball.com/download.html)

---

### Find a FP table source

---

Open `Future Pinball` and use the Table launcher `F4` and load the `Ramp-VUK-Demo`.

Save this table to the desktop or use path the table is loaded from.

---

### Import table

---

In `Blender` delete the default cube and `File > Import > Future Pinball Table` on the `.fpt`

This took just under a minute to load but you should see the table has been imported.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/imported-vuk-demo.jpg" alt="Future Pinball table in Blender"/>
    </div>
</div>
<br>

> Saving to `.blend` after loading will save time if you need to open an unchanged table.

This screenshot is after saving the `Blender` file then using `Blender 2.8` to load it.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 50%; max-height: 40%;">
        <img src="/images/guides/design/fp/imported-vuk-demo-2.8.jpg" alt="Future Pinball table in Blender"/>
    </div>
</div>
<br>

> Future Pinball tables `Forward` and `Up` positions are the same to blender when loaded.


---