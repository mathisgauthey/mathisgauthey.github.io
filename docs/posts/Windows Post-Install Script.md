---
title: Windows Post-Install Script
aliases: 
description: A small winget install script that I use on my computers.
authors:
  - Mathis Gauthey
categories:
  - guides
tags:
  - batch
date:
  created: 2023-01-16T13:31:14+01:00
  updated: 2024-02-06T09:01:35+01:00
share: true
comments: true
---

# Windows Post-Install Script

A small winget install script that I use on my computers.

<!-- more -->

## Sources

Source : [Browse the winget repository - winstall](https://winstall.app/)

## Scripts

### Main Tools

```
winget install --id=Microsoft.VisualStudioCode -e
winget install --id=Microsoft.PowerShell -e
winget install --id=Git.Git -e
winget install --id=TortoiseGit.TortoiseGit -e

winget install --id=Appest.TickTick  -e
winget install --id=Obsidian.Obsidian -e
::winget install --id=JohannesMillan.superProductivity  -e

winget install --id=Mozilla.Firefox  -e
winget install --id=Google.GoogleDrive -e
winget install --id=Google.ChromeRemoteDesktop -e
winget install --id=Cryptomator.Cryptomator -e

winget install --id=Armin2208.WindowsAutoNightMode -e
winget install --id=ShareX.ShareX -e
::winget install --id=TGRMNSoftware.BulkRenameUtility -e
winget install --id=WinMerge.WinMerge -e
winget install --id=Microsoft.PowerToys -e
winget install --id=7zip.7zip -e
winget install --id=AutoHotkey.AutoHotkey  -e
winget install --id=JAMSoftware.TreeSize.Free -e
winget install --id=DeepL.DeepL -e

winget install --id=SumatraPDF.SumatraPDF -e
winget install --id=TheDocumentFoundation.LibreOffice  -e

winget install --id=Stremio.Stremio -e
::winget install --id=WindscribeLimited.Windscribe -e
winget install --id=Spotify.Spotify -e
winget install --id=VideoLAN.VLC -e
winget install --id=OBSProject.OBSStudio -e
winget install --id=Discord.Discord -e
```

- Install [Bulk Rename Utility](https://www.bulkrenameutility.co.uk/Download.php) manually as command is not working atm.
- Install [Windscribe](https://windscribe.com/download) manually as command not working atm.

### Terminal (now Included in windows)

```
winget install --id=Microsoft.WindowsTerminal -e
```

### Torrents

```
winget install --id=qBittorrent.qBittorrent -e
```

### Component Temperature

```
winget install --id=CPUID.HWMonitor -e
```

### Music

```
winget install --id=Musescore.Musescore.3  -e
```

### Encryption

```
winget install --id=IDRIX.VeraCrypt -e
```

### Python Dev

```
winget install --id=Anaconda.Anaconda3  -e
```

### Linux ISO Boot Key

```
winget install --id=Balena.Etcher  -e
```

### File Server

- Filezilla
