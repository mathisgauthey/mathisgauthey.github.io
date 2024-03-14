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
  updated: 2024-03-14T23:05:29+01:00
share: true
comments: true
---

# Launch Todoist Minimized on Windows Startup

Todoist doesn't provide a way to launch Todoist on startup, minimized. Here's a script that does it.

<!-- more -->

1. Download and install [AHK](https://www.autohotkey.com/download/ahk-install.exe](https://www.autohotkey.com/download/ahk-install.exe).
2. Copy and paste the script below in a new `todoist.ahk` file.
3. Save this `todoist.ahk` file inside your startup folder. You can access it by using `CTRL+R` and typing `shell:startup`.
4. (Optional) Test the script by double-clicking the file. Todoist should open and instantly minimize to the taskbar.
5. That's it. Todoist will start and then minimize itself next time you boot up ;)

```ahk
Run, %localappdata%\Programs\todoist\Todoist.exe
WinWait, ahk_exe Todoist.exe
WinClose, ahk_exe Todoist.exe
```

Thanks [belima](https://github.com/belima) for the instructions that were missing ✌️
