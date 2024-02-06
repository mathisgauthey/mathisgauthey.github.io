---
title: OLED Display AutoHotkey Script for Automatically Dimming the Taskbar
aliases: 
description: If you have an OLED PC that you use for work, don't want burn-in but don't want to hide the taskbar either, here's a solution.
authors:
  - Mathis Gauthey
categories:
  - guides
tags:
  - oled
  - ahk
  - script
date:
  created: 2023-11-21T08:46:00+01:00
  updated: 2024-02-06T10:33:56+01:00
share: true
comments: true
---

# OLED Display AutoHotkey Script for Automatically Dimming the Taskbar

If you have an OLED PC that you use for work, don't want burn-in but don't want to hide the taskbar either, here's a solution.

<!-- more -->

## Goal

1. Auto-dim the taskbar to prevent burn in.
2. Keep the dimming when an app is opened in full-screen on a second monitor.
3. Stop the dimming if an app is opened full-screen on the primary monitor.

## Sources

- Reddit source : [Screensaver and taskbar dimmer for protecting OLED displays during Windows desktop and gaming usage scenarios : r/OLED\_Gaming](https://www.reddit.com/r/OLED_Gaming/comments/sa6clj/screensaver_and_taskbar_dimmer_for_protecting/)
- StackOverflow reference with script : [How can I make icons in the Windows 10 taskbar/quicklaunch/tray darker to help prevent burn-in on my OLED display? - Super User](https://superuser.com/a/1691664/1708452)
- Detecting full screen app to stop dimming : [Detect Fullscreen application? - Ask for Help - AutoHotkey Community](https://www.autohotkey.com/board/topic/38882-detect-fullscreen-application/)
- Detecting the screen the current window is on : [Detecting the screen the current window is on - Ask for Help - AutoHotkey Community](https://www.autohotkey.com/board/topic/85457-detecting-the-screen-the-current-window-is-on/)

## Script

```ahk
SysGet, Monitor, Monitor                   ; Get monitor dimensions
SysGet, WorkArea, MonitorWorkArea          ; Get monitor work-area without taskbar
dimtop := % WorkAreaBottom + 1             ; taskbar is assumed to start below the work-area
Gui Color, 0,0                             ; Black color
Gui -Caption +ToolWindow +E0x20            ; No title bar, No taskbar button, Transparent for clicks
Gui Show, X0 Y%dimtop% W%MonitorRight% H63 ; Create a semi-transparent cover window
WinGet ID, ID, A                           ; Get its HWND/handle ID
Winset AlwaysOnTop,ON,ahk_id %ID%          ; Keep it always on the top
WinSet Transparent,99,ahk_id %ID%          ; Transparency 99/256
SetTimer, coverIt, 500                     ; Repeat setting it to be on top of the taskbar
return

GetCurrentMonitor()
{
  SysGet, numberOfMonitors, MonitorCount
  WinGetPos, winX, winY, winWidth, winHeight, A
  winMidX := winX + winWidth / 2
  winMidY := winY + winHeight / 2
  Loop %numberOfMonitors%
  {
    SysGet, monArea, Monitor, %A_Index%
    if (winMidX > monAreaLeft && winMidX < monAreaRight && winMidY < monAreaBottom && winMidY > monAreaTop)
      return A_Index
  }
  SysGet, primaryMonitor, MonitorPrimary
  return "No Monitor Found"
}

coverIt:
    WinGet style, Style, A                 ; Get active window style and dimensions
    WinGetPos ,,,winW,winH, A
    ; 0x800000 is WS_BORDER.
    ; 0x20000000 is WS_MINIMIZE.
    ; check no border and not minimized
    isfull := ((style & 0x20800000) = 0 and winH >= A_ScreenHeight and winW >= A_ScreenWidth)
    isPrimaryMonitor := (GetCurrentMonitor() = 1)
    if (isfull and isPrimaryMonitor) {
        WinHide, ahk_id %ID%
    } else {
        WinShow, ahk_id %ID%
        Winset AlwaysOnTop,ON,ahk_id %ID%      ; Ensure it is still on the top
    }
    return
```
