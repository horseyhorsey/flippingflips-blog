---
author: "Flips-Admin"
title: "📜 Core.vbs - cvpmTrough"
date: 2020-05-04T14:00:06+09:00
lastMod: 2020-05-05T14:00:06+09:00
description: "How to create a Trough with Visual Pinball using cvpmTrough"
draft: false
image: /images/vp/corevbs/trough-ball-in-play.png
hideToc: false
enableToc: true
enableTocContent: false
author: flips-admin
authorEmoji: 🌱
categories:
- download
- visual pinball
tags: 
- beginner
- kicker
- scripting
- switch
- trough
---

## cvpmTrough Example

---

Class and member Reference [link](/en/simulation/visualpinball/scripting/core-vbs/#cvpmtrough)

---

### About

---

- Uses [Dummy controller](/en/simulation/visualpinball/scripting/core-vbs/#empty-table-with-dummy-pinmame)
- Removes `Drain_Hit` events (is replaced by the `cvpmtrough`)
- `Textbox` renamed to `DebugBox` to show active/inactive `Trough` switches.

<br>
<div id="banner" style="overflow: hidden; display: flex; justify-content:space-around;">
    <div class="" style="max-width: 75%; max-height: 20%;">
        <img src="/images/vp/corevbs/trough-ball-in-play.png" alt="CvpmTrough Visual Pinball"/>
    </div>
</div>
<br>

> Ball is exited from the trough via the kicker named `BallRelease` when the `Drain` is hit

---

### Download
---

[fflips_corevbs_trough.7z](/dl/examples/corevbs/fflips_corevbs_trough.7z)


