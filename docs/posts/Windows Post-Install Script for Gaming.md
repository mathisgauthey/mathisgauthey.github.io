---
title: Windows Post-Install Script for Gaming
aliases: 
description: A small winget install script that I use on my gaming computers.
authors:
  - Mathis Gauthey
categories:
  - guides
tags:
  - batch
date:
  created: 2023-01-16T13:31:35+01:00
  updated: 2024-02-06T11:08:20+01:00
share: true
comments: true
---

# Windows Post-Install Script for Gaming

A small winget install script that I use on my gaming computers.

<!-- more -->

## Sources

Source : [Browse the winget repository - winstall](https://winstall.app/)

## Scrips

### Core Game Launchers

```
winget install --id=Valve.Steam -e
winget install --id=EpicGames.EpicGamesLauncher -e
```

### Other Stuff

```
winget install --id=GOG.Galaxy -e
winget install --id=ElectronicArts.EADesktop -e
winget install --id=Ubisoft.Connect -e
```

### Nvidia Specific

```
winget install --id=TechPowerUp.NVCleanstall  -e
```

Only check :

- Check `Disable Installer Telemetry & Advertising`
- Check `Perform a Clean Installation`

### Mouses

#### Logitech Specific

```
winget install --id=Logitech.GHUB  -e
```

#### Razer Specific

```
winget install --id=RazerInc.RazerInstaller -e 
```

### MSI GL75 Specifics

```
winget install --id=SteelSeries.GG  -e
```

- [How to Fix a Slow Upload Speed with a Killer E2400 Gigabit Ethernet Controller](./How%20to%20Fix%20a%20Slow%20Upload%20Speed%20with%20a%20Killer%20E2400%20Gigabit%20Ethernet%20Controller.md)
