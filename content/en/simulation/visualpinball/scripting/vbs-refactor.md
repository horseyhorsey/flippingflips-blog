---
author: "Flips-Admin"
title: "📜 Script - Refactoring the template script"
date: 2020-05-15T07:30:00+00:00
description: "There is code in the visual pinball script which is shipped in the default/blank tables. We can move this code into new script files."
draft: false
image: images/vp/snippets.jpg
hideToc: false
enableToc: true
enableTocContent: false
author: flips-admin
authorEmoji: 🌱
categories:
- download
- templates
- visual pinball
tags: 
- beginner
- scripting
---

> This isn't needed and may seem unnecessary to some users but we like to see a blank slate in the tables script and with such common code that is used in most tables we can move this out and use it again.

Using blank template as a starter table [Link](/en/simulation/visualpinball/template/table/table-blank-stripped/#download)


---

## New Script Files

---

Create text files in the `Scripts` folder with the `.vbs` extension.

* `ball_and_sound.vbs`
* `manual_ball_ctrl.vbs`

> If on windows you may need to enable visible file extensions

---

### Manual Ball Control

---

`rothbauerw's Manual Ball Control`

We'll take this first as it's in between the sound scripts.

On line `246` is starts and ends on line `289`. Take this out and copy to the `manual_ball_ctrl.vbs` and save it.


<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 75%; max-height: 20%;">
        <img src="/images/guides/script/ball-ctrl-refactor.jpg" alt="Cutting script from Visual Pinball script to Notepad++"/>
    </div>
</div>
<br>

> We could remove the `EnableBallControl` from the script on `Line 26` and from the top of our table script and just use the `ControlBallInPlay = 1` when we want to use it.

---

### Ball and sound

---

Take all from `Positional Sound Playback Functions` down and add to the `ball_and_sound.vbs` file.

<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 75%; max-height: 20%;">
        <img src="/images/guides/script/ball-sound-refactor.jpg" alt="Cutting sound scripts from Visual Pinball script to Notepad++"/>
    </div>
</div>
<br>

---

## Using the scripts

---

If we compile the table script with `Script > Compile` we should get a `compilation successful`.

If we run on the other hand it will fail because the first thing it misses is the sound functions.

Add the following to load our script functions so we can find the sound functions once more.

``` vb
ExecuteGlobal GetTextFile("ball_and_sound.vbs")
ExecuteGlobal GetTextFile("manual_ball_ctrl.vbs")
```

> No error check here because we know :100:% they're there.

---

## Example download

[fflips_new-blank-stripped_scripts.7z](/dl/template/fflips_new-blank-stripped_scripts.7z)