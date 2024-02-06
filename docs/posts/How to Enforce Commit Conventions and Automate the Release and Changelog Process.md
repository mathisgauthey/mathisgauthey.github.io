---
title: How to Enforce Commit Conventions and Automate the Release and Changelog Process
aliases: 
description: In this post, I'll explain how to enforce conventional commits rules and automate the release and changelog process of a git repository.
authors:
  - Mathis Gauthey
categories:
  - guides
tags:
  - git
  - github-workflows
  - commit
  - convention
  - release
  - semantic-versioning
date:
  created: 2024-01-18T08:25:00+01:00
  updated: 2024-02-06T10:09:39+01:00
share: true
comments: true
---

# How to Enforce Commit Conventions and Automate the Release and Changelog Process

In this post, I'll explain how to enforce conventional commits rules and automate the release and changelog process of a git repository.

<!-- more -->

## What is What ?

- [Semantic Versioning](https://semver.org/) is a simple set of rules and requirements that dictate how version numbers are assigned and incremented.
- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) is a specification for adding human and machine readable meaning to commit messages. That's the one we'll use in every configuration here, it is close to the Angular specifications but has a few more types I reckon.

Common types according to [commitlint-config-conventional (based on the Angular convention)](https://github.com/conventional-changelog/commitlint/tree/master/@commitlint/config-conventional#type-enum) can be:

- build
- chore
- ci
- docs
- feat
- fix
- perf
- refactor
- revert
- style
- test

## Tools We'll Use

- [semantic-release](https://github.com/semantic-release/semantic-release) to automate the release process and changelog based on the Semantic Versioning rules.
- [commitizen](https://github.com/commitizen/cz-cli) to add a prompt when commiting changes that will use conventional commits specifications.
- [commitlint](https://github.com/conventional-changelog/commitlint) to check and enforce that commit messages meet the conventional commit format
- [conventional-changelog](https://github.com/conventional-changelog/conventional-changelog/tree/master) is also used for presets.
- [VS Code extension](https://marketplace.visualstudio.com/items?itemName=vivaxy.vscode-conventional-commits) for conventional commits modal.

## Requirements

- [Install Nvm, Npm, Yarn - Setting up Node on Ubuntu](./Install%20Nvm,%20Npm,%20Yarn%20-%20Setting%20up%20Node%20on%20Ubuntu.md)
- A git repository

## Configuration

### Semantic Release

Go inside your git repository. Install the package locally using the following command :

```bash
npm install --save-dev semantic-release
npm install @semantic-release/commit-analyzer -D
npm install @semantic-release/release-notes-generator -D
npm install @semantic-release/github -D
npm install conventional-changelog-conventionalcommits -D
```

Note : It can also be installed globally, but it's not our goal as we just want to automate the release process of our repository here.

It should create a `package.json` and `package.lock` file in your repository. Don't forget to add `node_modules/` to your `.gitignore` file.

Then, create a configuration file named `.releaserc` at the root of your repository. More on that [here](https://github.com/semantic-release/semantic-release/blob/master/docs/usage/configuration.md#configuration), but just copy and paste that for now :

```text
{
  "branches": [
    "main"
  ],
  "debug": true,
  "ci": true,
  "dryRun": false,
  "plugins": [
    [
      "@semantic-release/commit-analyzer",
      {
        "preset": "conventionalcommits"
      }
    ],
    [
      "@semantic-release/release-notes-generator",
      {
        "preset": "conventionalcommits"
      }
    ],
    "@semantic-release/github"
  ]
}
```

### Commitizen

Install globally using :

```bash
npm install -g commitizen
```

Simply use `git cz` or just `cz` instead of `git commit` when committing. You can also use `git-cz`, which is an alias for `cz`. If you use npm 5.2+, you can also use `npx cz`.

### Commitlint

At the root of your project, execute the following commands :

```bash
# Install commitlint cli and conventional config
npm install --save-dev @commitlint/{config-conventional,cli}

# Configure commitlint to use conventional config
echo "module.exports = {extends: ['@commitlint/config-conventional']}" > commitlint.config.js

# Install Husky v6
npm install husky --save-dev

# Activate hooks
npx husky install

# Add hook
npx husky add .husky/commit-msg  'npx --no -- commitlint --edit ${1}'
```

### VS Code Extension

It [exists](https://marketplace.visualstudio.com/items?itemName=vivaxy.vscode-conventional-commits). Simply install and use.
