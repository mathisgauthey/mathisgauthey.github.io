---
title: Using Git to Sync Your Obsidian Vault on Android Devices
aliases: 
description: On this post, I'll show how to sync your obsidian vault every x minutes on android using cron jobs inside termux.
authors:
  - Mathis Gauthey
categories:
  - guides
tags:
  - obsidian
  - git
  - android
date:
  created: 2022-08-06T09:45:37+02:00
  updated: 2024-02-06T11:11:47+01:00
share: true
comments: true
---

# Using Git to Sync Your Obsidian Vault on Android Devices

On this post, I'll show how to sync your obsidian vault every x minutes on android using cron jobs inside termux.

<!-- more -->

My [new guide](./How%20to%20Use%20Obsidian%20Git%20Sync%20on%20Android.md) using tasker to sync on app start-up and close instead of using cron jobs at time intervals.

Hi everyone! As I'm using Obsidian Git on my laptop, and it isn't available on android (yet?), I searched for ways to make it simple on Android. I wrote myself a tutorial and wanted to share it with you all! This one is not using SSH keys which might be too complicated for the standard user. But if you do use a SSH key, remember not to use a passphrase if you want the process to be automated and or fast with your widget!

Install Termux and Termux Widget

From [Github Termux](https://github.com/termux/termux-app), [Github Termux Widget](https://github.com/termux/termux-widget)  download the APKs and install them. You can use F-Droid as well.

Give Termux access to your storage using the following command [How to install Git on Android with Termux (Step-by-Step Guide)](https://www.techrepublic.com/article/how-to-install-git-on-android/)] :

```
termux-setup-storage
```

Setup Git and Github for manipulating repositories

Use the following commands to setup git and github via HTTPS :

```
pkg update && pkg upgrade
```

```
pkg install git
```

```
pkg install gh
```

_You can use SSH as well_

Login to your Github account :

```
gh auth login
```

Update the git configs :

```
git config --global user.name "name"
```

```
git config --global user.email "email"
```

Now you should clone your repository, try to use the following commands :

```
git status
git pull
git commit
git push
```

If you are on Android 12, you'll get an error with the command required to add the repository to a security list or something like that. Do it, and these commands should work.

Setup the sync script shortcut

Create a directory for the shortcuts ([Mobile Sync for Obsidian | Some Thoughts](https://werzum.github.io/tech/2022/02/13/Obsidian-Mobile-Sync.html) and [How to sync your obsidian vault on mobile using git : ObsidianMD](https://www.reddit.com/r/ObsidianMD/comments/v6otbu/how_to_sync_your_obsidian_vault_on_mobile_using/)) :

```
mkdir -p /data/data/com.termux/files/home/.shortcuts
chmod 700 -R /data/data/com.termux/files/home/.shortcuts
mkdir -p /data/data/com.termux/files/home/.shortcuts/tasks
chmod 700 -R /data/data/com.termux/files/home/.shortcuts/tasks
```

Create the sync script :

```
nano /data/data/com.termux/files/home/.shortcuts/tasks/sync_script.sh
```

Add the following script ([Git Guides - git add · GitHub](https://github.com/git-guides/git-add) and [bash - How to set current date as git commit message - Stack Overflow](https://stackoverflow.com/questions/4654437/how-to-set-current-date-as-git-commit-message)) :

```
#!/bin/bash
cd storage/shared/LifeWiki
git pull && git add -A && git commit -a -m "android vault backup: `date +'%Y-%m-%d %H-%M-%S'`" && git push
```

Create the widget and add it to your home screen. That's it, you just need to launch it to sync your Obsidian vault. It means you need to launch it before and after editing notes. If you putted your script inside ~/.shortcuts it will launch in the foreground, and if it was inside ~/.shortcuts/tasks then it will launch in the background.

Setting up an Automatic Execution of the Script

If you want to automatically **sync your vault every hour**, for instance, you can do it using a Cron job. ([Obsidian Syncing Alternative | Obsidian-Sync-Alternative](https://pulinagrawal.github.io/Obsidian-Sync-Alternative/) and [Obsidian Github Integration for Sync and Version Control - Share & showcase - Obsidian Forum](https://forum.obsidian.md/t/obsidian-github-integration-for-sync-and-version-control/6369) and [Guide: Obsidian vault github sync cron on termux : ObsidianMD](https://www.reddit.com/r/ObsidianMD/comments/qep4gn/guide_obsidian_vault_github_sync_cron_on_termux/))

First, you need to install Cron :

```
pkg install cronie termux-services
```

Then, you'll restart Termux then run the following :

```
sv-enable crond
crontab -e 
```

Finally, you'll end up with the `crontab -e` command in the **nano** text editor. Add the following :

```
0 * * * * bash ~/.shortcuts/tasks/sync_script.sh
```

You just need to keep Termux opened in order for the job to be able to launch.

You can find information about Cron job easily on the internet. ([A Beginners Guide To Cron Jobs - OSTechNix](https://ostechnix.com/a-beginners-guide-to-cron-jobs/))
