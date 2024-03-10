---
title: How to Install Warp Terminal on WSL
aliases: 
description: How to install Warp terminal on WSL
authors:
  - Mathis Gauthey
categories:
  - guides
tags:
  - warp
  - terminal
  - WSL
date:
  created: 2024-03-06T09:21:47+01:00
  updated: 2024-03-10T23:04:00+01:00
share: true
comments: true
---

# How to Install Warp Terminal on WSL

Warp terminal is a popular choice for a powerful terminal enhanced by AI on Mac. It is also available on Linux now, instead of waiting for a Windows version, one could use WSL right now to use it !

<!-- more -->

## TLDR Copy Pasta

```bash
sudo apt update && sudo apt upgrade
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo apt -y install ./google-chrome-stable_current_amd64.deb
curl https://releases.warp.dev/stable/v0.2024.02.27.08.01.stable_00/warp-terminal_0.2024.02.27.08.01.stable.00_amd64.deb
sudo dpkg -i warp-terminal_0.2024.02.27.08.01.stable.00_amd64.deb
sudo apt --fix-broken install
export BROWSER=google-chrome
export WARP_ENABLE_WAYLAND=1
export MESA_D3D12_DEFAULT_ADAPTER_NAME=NVIDIA
WARP_ENABLE_WAYLAND=1 MESA_D3D12_DEFAULT_ADAPTER_NAME=NVIDIA warp-terminal
```

## Explanations

First, perform a classic update and upgrade of your registries :

```bash
sudo apt update && sudo apt upgrade
```

Then install Google Chrome, it'll be required to log in to your Warp terminal account :

```bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo apt -y install ./google-chrome-stable_current_amd64.deb
```

Download the Warp deb file and install it along with the dependencies :

```bash
curl https://releases.warp.dev/stable/v0.2024.02.27.08.01.stable_00/warp-terminal_0.2024.02.27.08.01.stable.00_amd64.deb
sudo dpkg -i warp-terminal_0.2024.02.27.08.01.stable.00_amd64.deb
sudo apt --fix-broken install
```

Then, configure the launch arguments to get a beautiful window back on Windows :

```bash
export BROWSER=google-chrome
export WARP_ENABLE_WAYLAND=1
export MESA_D3D12_DEFAULT_ADAPTER_NAME=NVIDIA
```

You can now launch it and login :

```bash
WARP_ENABLE_WAYLAND=1 MESA_D3D12_DEFAULT_ADAPTER_NAME=NVIDIA warp-terminal
```

It'll open a google-chrome window.

1. The Warp terminal window will ask you to log in.
2. You'll be redirected to Chrome.
3. Input your email adress.
4. Copy and paste the link from your mail to the Google Chrome window.
5. It'll ask you to `Take you to Warp`, but it won't work. Instead, use the copy auth token.
6. Paste the auth token to your Warp terminal windows.
7. You're now logged in !

![2024-03-09_18-18-30_warp_install.png](../images/2024-03-09_18-18-30_warp_install.png)

Tada, you can launch warp from window and use it on your WSL ! It's amazing, so enjoy it !
