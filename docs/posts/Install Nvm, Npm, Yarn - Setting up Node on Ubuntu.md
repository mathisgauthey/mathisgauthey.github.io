---
title: Install Nvm, Npm, Yarn - Setting up Node on Ubuntu
aliases: 
description: Here's how to install and setup Node on Ubuntu.
authors:
  - Mathis Gauthey
categories:
  - guides
tags:
  - script
  - node
  - nvm
  - npm
  - yarn
date:
  created: 2024-01-18T08:49:00+01:00
  updated: 2024-02-06T11:26:28+01:00
share: true
comments: true
---

# Install Nvm, Npm, Yarn - Setting up Node on Ubuntu

Here's how to install and setup Node on Ubuntu.

<!-- more -->

Sources :

- [GitHub - nvm-sh/nvm: Node Version Manager - POSIX-compliant bash script to manage multiple active node.js versions](https://github.com/nvm-sh/nvm#install--update-script)
- [Installation | Yarn](https://classic.yarnpkg.com/lang/en/docs/install/#windows-stable)

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
# wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
command -v nvm # After relaunching terminal
nvm install --lts
node --version
npm install --global yarn
yarn --version
```
