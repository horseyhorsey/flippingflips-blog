---
author: "Flips-Admin"
title: "📜 Script - Cycle 💡 Lights Rainbow"
date: 2020-04-29T12:00:06+09:00
description: "Scripting snippet example with table for rainbow cycled lamps. This script is crude but it will introduce you to VP Timers, VP Collections, VP Lights, variables, methods, loops, switch statements..."
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

This script is crude but it will introduce you to VP Timers, VP Collections, VP Lights, variables, methods, loops, switch statements in `Visual Basic Script`

## Table prerequisites

* 1 Create or use an existing `VPX` table
* 2 Create a few `Lights` on the table
* 3 Create a new collection called `LampCollection`. (Select lights before creating and you can create from selection, `F8` and skip `step 4`.)
* 4 Map these lights to the collection by selecting `right click > add to collection > LampCollection`
* 5 Create timer object named `leds` that is disabled. Set the interval for how long the cycle lasts

## Script

``` vb

Dim led_num:led_num=1 ' Set step 1
leds.Enabled = 1 ' Enable the timer

'**********************
'Cycle Rainbow : 12 color steps over LampCollection
'**********************
Sub leds_Timer()
  Dim lamp
  if led_num=12 then led_num=1
    For each lamp in LampCollection
    Select Case led_num
      Case 1
      lamp.color=RGB(255,0,0) ' RED
      lamp.colorFull=RGB(255,0,0)
      Case 2
      lamp.color=RGB(255,127,0)
      lamp.colorFull=RGB(255,127,0)
      Case 3
      lamp.color=RGB(255,255,0)
      lamp.colorFull=RGB(255,255,0)
      Case 4
      lamp.color=RGB(127,255,0)
      lamp.colorFull=RGB(127,255,0)
      Case 5
      lamp.color=RGB(0,255,0)
      lamp.colorFull=RGB(0,255,0)
      Case 6
      lamp.color=RGB(0,255,127)
      lamp.colorFull=RGB(0,255,127)
      Case 7
      lamp.color=RGB(0,255,255)
      lamp.colorFull=RGB(0,255,255)
      Case 8
      lamp.color=RGB(0,127,255)
      lamp.colorFull=RGB(0,127,255)
      Case 9
      lamp.color=RGB(0,0,255)
      lamp.colorFull=RGB(0,0,255)
      Case 10
      lamp.color=RGB(127,0,255)
      lamp.colorFull=RGB(127,0,255)
      Case 11
      lamp.color=RGB(255,0,255)
      lamp.colorFull=RGB(255,0,255)
      Case 12
      lamp.color=RGB(255,0,127)
      lamp.colorFull=RGB(255,0,127)
      Case else
      lamp.color=RGB(255,255,255)
      lamp.colorFull=RGB(255,255,255)
    End Select
    Next

  led_num = led_num +1 ' increment step
End Sub

```

## Example download

[Download](/dl/examples/fflips_rainbow-lights.7z) - fflips_rainbow-lights.7z