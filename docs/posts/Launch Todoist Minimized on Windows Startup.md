---
title: Launch Todoist Minimized on Windows Startup
aliases: 
description: Todoist doesn't provide a way to launch Todoist on startup, minimized. Here's a script that does it.
authors:
  - Mathis Gauthey
categories:
  - guides
tags:
  - todoist
date:
  created: 2023-11-23T18:41:00+01:00
  updated: 2024-02-06T10:28:20+01:00
share: true
comments: true
---

# Launch Todoist Minimized on Windows Startup

Todoist doesn't provide a way to launch Todoist on startup, minimized. Here's a script that does it.

<!-- more -->

Requirement : [AutoHotkey](https://www.autohotkey.com/)

```ahk
Run, %localappdata%\Programs\todoist\Todoist.exe
WinWait, ahk_exe Todoist.exe
WinClose, ahk_exe Todoist.exe
```
