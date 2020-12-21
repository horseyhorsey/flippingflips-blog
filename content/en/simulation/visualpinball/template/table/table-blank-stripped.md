---
author: "Flips-Admin"
title: "🏓 Table - Blank Stripped"
date: 2020-04-04T12:00:06+09:00
description: "Visual Pinball Table template with a reduced file size created from blank table"
draft: false
image: images/vp/visual-pinball-template.png
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
---

## About

This table template was created from a `BlankTable` in `VPX 10.6.0` and was meant to be as lightweight as possible. For testing, copy pasting into other tables.

<div>
<img src="/images/vp/template/new-blank-stripped.jpg" alt="..." title="Desktop" width="300" />

</div>

## Features \\ Guide

{{< expand "Dimensions" >}}

* Default no change

   Width    |    Height 
----------------|-------------
952|2162
20.250"   |   46.0"

{{< /expand >}}

{{< expand "Objects" >}}
* Removed all template primitives apart from posts
* Removed `RubberEMWheel`
* Removed Flipper Shadows
* Added `Trough` exit screwed panel
* Added larger / modern `WallsTranslite` primitive and template texture `WallsTranslite.png`. (Removed sidewalls)
{{< /expand >}}

{{< expand "Physics" >}}
- Lowered `Flipper` strength
* Metal, Wood, Rubber collidables use `a_physics` materials based on physics values given.
- Change `Plunger` pull speed lower to `80`
{{< /expand >}}

{{< expand "Layers" >}}
* 1  = Flippers, other
* 2  = Switches, bumpers etc
* 3  = Lights, GI
* 5  = Plastics
* 10 = All collidable objects
* 11 = Cabinet, walls
{{< /expand >}}

{{< expand "Notes" >}}
* Removed all default sound and images to reduce file size to `3mb`, zips to `500kb`
* Rubber posts are two layers. Hidden collidable 0-55 height with visible rubbers.
* Metal guides are two layers. Hidden collidable straight edges with visible curved walls.
{{< /expand >}}

<img src="/images/vp/template/new-blank-stripped-fs.jpg" alt=".." title="FullScreen" width="300" />

## Download

[Download](/dl/template/fflips_new-blank-stripped.7z) - fflips_new-blank-stripped.7z 