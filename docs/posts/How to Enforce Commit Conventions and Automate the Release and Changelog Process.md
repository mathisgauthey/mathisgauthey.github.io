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
  updated: 2024-04-17T23:41:14+02:00
share: true
comments: true
---

# How to Enforce Commit Conventions and Automate the Release and Changelog Process

In this post, I'll explain how to enforce conventional commits rules and automate the release and changelog process of a git repository.

<!-- more -->

## Introduction

### A Little Bit of Definitions First

- [Semantic Versioning](https://semver.org/) is a simple set of rules and requirements that dictate how version numbers are assigned and incremented.
- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) is a specification for adding human and machine readable meaning to commit messages. That's the one we'll use in every configuration here, it is close to the Angular specifications but has a few more types I reckon.

Common types according to [commitlint-config-conventional (based on the Angular convention)](https://github.com/conventional-changelog/commitlint/tree/master/@commitlint/config-conventional#type-enum) can be:

- `build`
- `chore`
- `ci`
- `docs`
- `feat`
- `fix`
- `perf`
- `refactor`
- `revert`
- `style`
- `test`

> [!info] Why use Conventional Commits instead of the Angular convention ?
> This is an extension of the Angular convention that contains a little bit more types for a more flexible management. It also aims to become a standard for all developers across every languages.

### Why Should We Use Such Conventions and Automated Tools ?

- Conventional commits and semantic release standards allow for a standard way to communicate changes made on a codebase, which helps developers communicate better. And god knows we're bad at this.
- Automated release process allows for easier changelog managements with easy rollbacks if required.
- In continuous integration and deployment, we aim to automate most of the things (testing, releasing, building and deploying) in order to be able to focus 100% on our programming and not on manual and repetitive tasks.

### Tools We'll Use

- [semantic-release](https://github.com/semantic-release/semantic-release) to automate the release process and changelog based on the Semantic Versioning rules.
- [VS Code extension](https://marketplace.visualstudio.com/items?itemName=vivaxy.vscode-conventional-commits) for conventional commits modal on committing changes.
- [commitlint](https://github.com/conventional-changelog/commitlint) to check and enforce that commit messages meet the conventional commit format and prevent other types of commits to go through.
- [conventional-changelog](https://github.com/conventional-changelog/conventional-changelog/tree/master) is also used for defining the Conventional Commits convention in semantic-release.
- [commitizen](https://github.com/commitizen/cz-cli) to add a CLI prompt when committing changes that will use conventional commits specifications. It is an alternative to an editor extension.

### Requirements

- [Install Nvm, Npm, Yarn - Setting up Node on Ubuntu](./Install%20Nvm,%20Npm,%20Yarn%20-%20Setting%20up%20Node%20on%20Ubuntu.md)
- A git repository

## Semantic Release

### Goals

1. Trigger `semantic-release` on new commits made on `main` branch.
2. Analyze commits based on [conventional commits style](https://www.freecodecamp.org/news/how-to-write-better-git-commit-messages/).
3. Generate releases notes automatically.
4. Put these release notes inside `docs/CHANGELOG.md`.
5. Create a release commit on main with the CHANGELOG.
6. Automatically tag based on conventional commit and semantic release conventions.

### Installation

Make sure you installed NVM like explained above, and go inside your git repository.

Install the packages locally using the following command :

```bash
npm install semantic-release -D
npm install @semantic-release/commit-analyzer -D
npm install @semantic-release/release-notes-generator -D
npm install @semantic-release/changelog -D
npm install @semantic-release/git -D
npm install @semantic-release/exec -D
npm install conventional-changelog-conventionalcommits -D
# npm install @semantic-release/github -D
```

> [!NOTE] Notes
> - It can also be installed globally, but it's not our goal as we just want to automate the release process of our current repository here.
> - The `-D` means the package will appear in your `devDependencies`.

It should create a `package.json` and `package.lock` file in your repository. Don't forget to add `node_modules/` to your `.gitignore` file **but keep the other two committed as they manage the packages and packages dependencies versions respectively.**

Then, create a configuration file named `.releaserc` at the root of your repository. More on that [here](https://github.com/semantic-release/semantic-release/blob/master/docs/usage/configuration.md#configuration), but just copy and paste that for now :

```yml
{
    "branches": [
        "main"
    ],
    "tagFormat": "${version}", # Because X.X.X is better than vX.X.X
    "debug": true, # Output debugging information
    "ci": true, # Allows for CI environment verifications
    "dryRun": false, # Skip some part like the publishing, helps previewing changes first
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
        [
            "@semantic-release/changelog",
            {
                "changelogFile": "docs/CHANGELOG.md"
            }
        ],
        [
            "@semantic-release/git",
            {
                "message": "chore(release): ${nextRelease.version} [skip ci]\n\n${nextRelease.notes}",
                "assets": [
                    "docs/CHANGELOG.md"
                ]
            }
        ]
    ]
}
```

> [!warning] Prevent infinite loops !
> Note that the `[skip ci]` is only important when working on Azuredevops. Indeed, if your continuous integration system involves a trigger on main that will make semantic-release generate a commit on main… You can definitely see where this is going. Make sure not to do that.

### Launch Locally to Test it Out

If you want to run the `semantic-release` locally, use `./node_modules/.bin/semantic-release --no-ci --dry-run`. If you're satisfied with the results, just get rid of the `--dry-run`, and it will create a release commit and tag **locally that you can then push if you like.**

## Enforce Commit Conventions in Your Team

### Introduction

Creating new rules and standards can be pretty hard, especially in a team that has been working differently for a very long time.

But a developer should know how to [write a good commit message](https://www.freecodecamp.org/news/how-to-write-better-git-commit-messages/), it is an essential part of his job as he won't always be the one to work on complex pieces of software, and needs to communicate for the present colleagues and the futures ones.

> [!success] In short, what is a good commit message ? Ask yourself these questions :
> - What are the changes I made
> - Why have I made these changes? Why was the change needed?
> - What effect have my changes made?
> - What are the changes in reference to? (Issue, bug report, etc.)

A good example that follows directly the flow from above might be :

```text
fix: fix foo to enable bar

This fixes the broken behavior of the component by doing xyz. 

BREAKING CHANGE
Before this fix foo wasn't enabled at all, behavior changes from <old> to <new>

Closes D2IQ-12345
```

### Use an Editor Extension

There's probably an extension that might allow for a streamlined conventional commit process in your editor, for example :

[Here's an extension that allows to use a commit modal when commiting changes on VS Code](https://marketplace.visualstudio.com/items?itemName=vivaxy.vscode-conventional-commits). Simply install and use it when committing changes.

### Use a CLI Tool

Alternative to an editor extension, here on the CLI directly, you can install it globally using :

```bash
npm install -g commitizen
```

Simply use `git cz` or just `cz` instead of `git commit` when committing. You can also use `git-cz`, which is an alias for `cz`. If you use npm 5.2+, you can also use `npx cz`.

### Force Conventional Commits Using Commitlint

If you want to enforce it and don't allow for random commit messages, you can enforce it with pre-commit hooks using commitlint :

At the root of your project, execute the following commands :

```bash
# Install commitlint cli and conventional config
npm install --save-dev @commitlint/{cli,config-conventional}

# Configure commitlint to use conventional config
echo "module.exports = {extends: ['@commitlint/config-conventional']}" > commitlint.config.js

# Install Husky v6
npm install husky --save-dev

# Activate hooks
npx husky install

# Add hook
npx husky add .husky/commit-msg  'npx --no -- commitlint --edit ${1}'
```
