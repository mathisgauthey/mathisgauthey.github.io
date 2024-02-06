---
title: How to Automatically Back-up All Your Github Repo and Archive Them
aliases: 
description: Afraid of losing all your hard work on github ? Here a simple and fast way to backup all your projects in multiple zip files.
authors:
  - Mathis Gauthey
categories:
  - guides
tags:
  - script
  - bash
  - github
  - archive
date:
  created: 2023-11-14T15:29:00+01:00
  updated: 2024-02-06T11:19:45+01:00
share: true
comments: true
---

# How to Automatically Back-up All Your Github Repo and Archive Them

Afraid of losing all your hard work on github ? Here a simple and fast way to backup all your projects in multiple zip files.

<!-- more -->

## Goals

1. Clone all our repositories.
2. Archive them to their respective `folderName.zip`
3. Delete the repository folders

## Requirements

- Linux, git-bash on windows, well basically you need to be able to run bash script.
- [Github CLI](https://github.com/cli/cli#installation) → Access to the repo list and clone using https login.
- [parallel](https://www.gnu.org/software/parallel/) → Parallelize code to reduce execution time.
- [p7zip [Wiki ubuntu-fr]](https://doc.ubuntu-fr.org/p7zip) → Archive the cloned repository.

## The Script

You'll just need to input your account username in line `2` of the script.

You can find it here :`https://github.com/USER`

The script will clone and archive the repositories in the `current folder`.

```bash
# Cloning all the repositories from a profile
gh repo list USER --limit 1000 --json nameWithOwner --jq '.[].nameWithOwner' | \
   parallel -j16 gh repo clone

# Function to archive and remove subfolders
archive_and_remove() {
  local subfolder="$1"
  local subfolder_name="${subfolder%/}"

  # Archive the subfolder to its own ZIP file
  7z a -tzip "${subfolder_name}.zip" "$subfolder_name"

  # Remove the original subfolder
  rm -rf "$subfolder_name"
}

# Export the function to make it available to parallel
export -f archive_and_remove

# Use find to get a list of subfolders and pipe it to parallel
find . -maxdepth 1 -type d -exec basename {} \; | \
  parallel -j16 archive_and_remove
```
