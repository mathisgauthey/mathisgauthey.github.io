---
title: How to Fix Windows Spotlight Not Working (ADMTheme issue)
aliases: 
description: How to fix Windows Spotlight reverting back to picture.
authors:
  - Mathis Gauthey
categories:
  - guides
tags:
  - windows
  - theme
  - windows-spotlight
  - wallpaper
date:
  created: 2024-01-12T12:02:00+01:00
  updated: 2024-02-06T11:39:34+01:00
share: true
comments: true
---

# How to Fix Windows Spotlight Not Working (ADMTheme issue)

In this post, I'll explain how to fix windows spotlight if it keeps reverting back to picture mode.

<!-- more -->

## Introduction

Recently, I came across an issue. I love to use `Windows Spotlight` for my Background and Lockscreen. But on my MSI laptop, the background settings would always revert back to `Picture` with a default wallpaper.

I tried, and you should try as well, the following fixes :

- [Reset and register Windows Spotlight](https://www.elevenforum.com/t/reset-and-re-register-windows-spotlight-in-windows-11.5248/#post-285757)
- Go into `Control Panel > Hardware and Sound > Power Options > Edit Plan Settings`
   	- `Change advanced power settings`
   	- `Desktop Background settings > Slide Show` ⇒ `Paused` for both.

And finally I figured what was wrong. A theme was auto-applied on start-up. How ?

- Search `msconfig` on Windows :
   	- `System Configuration > Services`
- Search start-up applications on the `Windows Task Manager`

Found nothing unusual. But the auto-applie theme was called `ADMTheme`. It was related to [AutoDarkMode apparently](https://www.reddit.com/r/Windows11/comments/10hry9s/comment/j5awaqx/?utm_source=share&utm_medium=web2x&context=3), a Windows tool to automatically switch your Windows color scheme.

## Fix

The fix is quite simple.

1. Uninstall AutoDarkMode
2. Go into `C:\Users\%USERPROFILE%\AppData\Roaming\AutoDarkMode` and delete this folder.
3. Reboot
4. Open a CMD as admin and type in the following command : `winget install --id=Armin2208.WindowsAutoNightMode  -e`
5. Reboot

Now you can open AutoDarkMode, configure it to change with `From sunset to sunrize (location services)`, and configure your windows background and lockscreen.

Your theme will be kept as `ADMTheme`, but it'll keep your changes.

The issue was probably caused by an old update of AutoDarkMode I reckon. Anyway, it's now fixed.
