---
title: My Complete Obsidian Workflow to Manage My Life
aliases: 
description: In this post, I'll go into the details on how I organize my whole life using Obsidian.
authors:
  - Mathis Gauthey
categories:
  - guides
tags:
  - obsidian
  - tasks
  - journaling
  - workout-log
  - media-tracking
  - read-it-later
  - bookmark-management
  - note-taking
  - note-sharing
date:
  created: 2023-07-29T17:53:34+02:00
  updated: 2024-02-06T11:01:10+01:00
share: true
comments: true
---

# My Complete Obsidian Workflow to Manage My Life

In this post, I'll go into the details on how I organize my whole life using Obsidian.

<!-- more -->

I'll solve many problems I've seen people struggle with online, and showcase my setup and how you can use it as a starting point.

## Introduction

![2023-08-05_19-43-11_obsidian_workflow_workspace_example.png](../images/2023-08-05_19-43-11_obsidian_workflow_workspace_example.png)

### Why Writing This Guide ?

As I promised to quite a few people on different places, I'm releasing a full blown guide of my Obsidian workflow. It has many cool features that I've seen people struggling with online :

1. Tasks and project management with journaling, workout logging and media tracking. Using daily and periodic notes.
2. Read-it-later with automated conversion to markdown and import inside your vault. Meaning all your past knowledge is inside Obsidian, available with a simple search alongside your notes.
3. Fast and simple one click upload obsidian publish alternative.

But there's plenty more. It took me some time here and there during the past year to come up with this setup. And don't worry, it is **easy to use** despite its awfully long name. But I'll describe it with as much depth as I can for people who wants to fine tune it.

Obviously, it is merely just a starting point, with Obsidian you can (and you always should) do something that works well for **you**. And that means creating your **own** setup. But that doesn't forbid you from using this one as a starting-point.

### Why is it the Perfect Obsidian Setup (at Least for me) ?

It embraces many relevant and high level productivity concepts alongside [Obsidian](https://obsidian.md/)'s [powerful note linking feature](https://help.obsidian.md/Getting+started/Link+notes) while still being usable as a simple "I create a simple daily checklist with a few notes" in case of existential crisis. → That means the system will **last**.

Of course using Obsidian also mean **offline access** and **data possession**. You can sync your data yourself using [obsidian-git](https://github.com/denolehov/obsidian-git) plugin. If the mobile (android) version doesn't work the way you want despite the plugin active development, you can follow one of my guides :

- [One using cron jobs to sync at regular intervals](./Using%20Git%20to%20Sync%20Your%20Obsidian%20Vault%20on%20Android%20Devices.md)
- [Another one that sync at Obsidian's app startup](./How%20to%20Use%20Obsidian%20Git%20Sync%20on%20Android.md)

Or just pay for the encrypted [obsidian-sync](https://obsidian.md/sync) official plugin.

## Core Features

- 🎨 Beautiful design using [AnuPpuccin: Personal theme for Obsidian](https://github.com/AnubisNekhet/anuppuccin).
- 🗃️ [P.A.R.A](https://fortelabs.com/blog/para/)[^1] folder organisation based on file actionability.
- ✅ [GTD](https://gettingthingsdone.com/)[^2] task management on par with a [full Todoist setup](https://todoist.com/fr/productivity-methods/getting-things-done), but with a simple and natural way of **writing tasks alongside notes**. You also get to keep your project tasks, notes and files archives when you finish a project, allowing you to access these informations in the future.
- 📅 Daily notes for task management, periodic notes for projects management (week, month, quarter and year).
- 📓 Journal section for each daily and periodic notes to write about anything that happened during a certain period of time.
- 💪 Simple workout log for storing your workout sessions but with an infinite possible personalized exercise library.
- 🎮 Media backlog Kanban board for tracking books, shows, movies or video games backlog, consuming media at the right pace, and archiving what you do. All without proprietary online services that hold you data.
- 🔗 Read-it-later / bookmark manager with automated markdown conversion for offline storage inside your vault using [Omnivore app](https://omnivore.app/). That means easy search for knowledge inside your vault across sources and personal notes.
- 📝 [Zettelkasten note-taking](https://everlaab.com/methode-zettelkasten-comment-prendre-des-notes-utiles/) on a flat structure inside `3-Resources` folder.
 1. 📎 Import sources automatically using [obsidian-omnivore](https://github.com/omnivore-app/obsidian-omnivore) plugin for an automatic markdown conversion of a webpage or document online or manually from a file or using [markdownload](https://github.com/deathau/markdownload).
 2. Highlight and take reference notes using [Omnivore app](https://omnivore.app/) or directly inside your vault using a simple markdown file.
 3. Write literature notes to summarise the source informations.
 4. Write permanent notes from key concepts directly inside literature notes using wiki-links.
- 🌐 One click upload of file and attachments to a [Hugo](https://gohugo.io/) website hosted on [Github Pages](https://pages.github.com/) thanks to [obsidian-github-publisher](https://github.com/ObsidianPublisher/obsidian-github-publisher) plugin.

## Requirements

- Obsidian app.
- [Todoist](https://todoist.com/) account for an easy, **fast** and accessible inbox on any of your devices.
- [Omnivore](https://omnivore.app/) account for read-it-later and bookmark manager with automated markdown conversion for offline use.
- [Github](https://github.com/) account for hosting your website on github pages.
- [Google](https://www.google.com/) account for importing your Google calendar inside your daily-notes.

## Quick-start : How Do I ?

### Repository

Alright, I'm in, how can I start ?

→ Here you can find a [Github repository with an example vault](https://github.com/mathisgauthey/obsidian-workflow-template) using my setup. All the plugins are configured to match with one another.

Don't forget to **login** to the following plugins using your account :

- [obsidian-todoist-plugin with your todoist axcount](https://github.com/jamiebrynes7/obsidian-todoist-plugin)
- [obsidian-google-calendar plugin with your Google account](https://github.com/YukiGasai/obsidian-google-calendar)
- [obsidian-omnivore plugin with your Omnivore account](https://github.com/omnivore-app/obsidian-omnivore)
- [obsidian-github-publisher plugin with your GitHub account](https://github.com/ObsidianPublisher/obsidian-github-publisher)

For the note-sharing part, you might want to take a look at my [guide](./Obsidian%20Publish%20Alternative,%20How%20to%20One-click%20Upload%20Your%20Notes%20on%20Your%20Own%20Website.md), along with my [own website repository](https://github.com/mathisgauthey/mathisgauthey.github.io) and how is it configured. It is based on [hugo-theme-stack](https://github.com/CaiJimmy/hugo-theme-stack).

I will briefly explain each functionality here as well, and with more details in other posts.

### Wait ! Don't Go Further

I forgot something in the initial post. Here's an update. There's a lot of quality of live improvements in this vault, here's a few examples :

- If you hit `ctrl+S` or just save the file, Obsidian will [lint](https://github.com/platers/obsidian-linter) the file ! Meaning the whole writing, the frontmatter, the titles, the spacings, even the characters used for bold or italics will be standardized. In a way that works with my other plugins !
- If you paste a link, the link will [auto-fetch](https://github.com/zolrath/obsidian-auto-link-title) a title for markdown link !
- If you paste an image, it'll [automatically](https://github.com/reorx/obsidian-paste-image-rename) prompt you for an image title after a timestamp. That way, if you use clear unused image, you'll be able to see if you deleted unwanted images or not.
- The first header will [automatically](https://github.com/dvcrn/obsidian-filename-heading-sync) mimic the note title. And if you lint the file, the title metadata will change according to the title as well.
- There's also improvements in the way footnotes are managed along with a configurable shortcut to create footnotes automatically numbered. I recommend setting `ctrl + shift + ^`.

### How Do I Use the Tasks and Projects ?

I'll explain here how to use it. But if you want to understand why I built it this way, I encourage you to read my explanations [here](./Why%20Using%20Obsidian%20for%20Life%20Management.md).

Basically you can create tasks everywhere except inside the following files and folders :

```
path does not include Archives
path does not include Templates
path does not include Workout_Log
path does not include Media Backlog
path does not include _Sources
```

There's a predefined space inside your `daily note` to add some `one-off tasks`, it is below the `Notes 📝` header. But you can use tasks alongside your notes anywhere else as long as it isn't in one of the previously mentioned files or folder.

The workflow also involves using `projects` to achieve goals & objectives. Each goal or objective then must have a `project` with an according [happens date](https://publish.obsidian.md/tasks/Queries/Filters#Happens) for viewing purposes.

But where do I create such projects to achieves my goals & objectives? Inside an `Area` file (eg: Finances) under your `2-Areas` folder. Areas are to be understood as areas of focus (GTD) or areas or responsibility (P.A.R.A), meaning areas of your life.

Each `Areas` file template has a `Projects 🎯` header. Markdown tasks inside the file are considered as `Project`, you can give it any task property you find useful but a deadline is important to use the setup properly. The task description can then be enclosed by `[[` in order to create a wikilink to a `project note` inside the `1-Projects` folder. You'll find more informations about wikilinks in the obsidian [documentation](https://help.obsidian.md/Linking+notes+and+files/Internal+links).

If you feel the need to use a recurring task like "Add recent transactions to my budget each week" inside your Finances area to maintain a standard, you might create a project called "Maintain a good budget". Inside the project note, you can create a `recurring task` and that's it. I would always recommend setting a happens date as it will help you see if it became a [habit](https://jamesclear.com/habits) by then.

But how to **display my current tasks** ? That's the job of the `daily note`. It will display tasks according to their `happens date`, and it will also display the tasks that has one of the three specific tags (that can't be used at the same time by essence) : `#next`, `#waiting` and `#delegated`. They are displayed differently and tasks using the `#next` tag will be grouped by context, meaning by their other tag(s).

There's also the `TaskBoard ✅` note where you'll find unplanned tasks (without `happens date` or `tags`) so that you can't miss a thing ! You should open this note sometimes to make sure nothing is left unattended.

In order to show which project you should be working on, you should rely on your periodic notes (weekly, monthly, quarterly and yearly) to display the relative projects based on their first happen date. The `Dashboard 🗺️` plays a similar role. There's also a callout inside the `daily note` that queries upcoming projects (with a happens date in the next 30 days) and the projects in progress (using `- [/]` tasks status).

The `Someday Maybe 💭` file is where you put your future goals and objectives in the form of a simple bullet list. Nothing fancy, we don't care it's not important as of now. But you might want to put things you want to do here, wait for a bit and decide if they're still relevant after a while. If yes, simply create a project and start working on it !

The higher horizons of existence are covered in the `Vision, Identity, Purpose & Principles ⚙️` note.

Basically :

- Visions : Where and how you see yourself in 3-5 years.
- Identity : Who you are.
- Purpose : Your ultimate goal in life, why you're in this world.
- Principles : Values you act upon everyday.

### How Do I Use the Journal ?

You can write your feelings inside your `daily note` and each `periodic notes`, that's always the last header purpose.

The daily note adds a grateful part in which you should describe the good things that happened each day, and the things you did that were good to the world.

There's also a mood tracking property (mood:1-5) that ranges from 1=bad to 5=amazing. It could be used with the [obsidian-tracker plugin](https://github.com/pyrochlore/obsidian-tracker) to create a mood chart, but I have no use for it yet myself.

I created a `Journal 📓` note with a script that queries every single journal entries from your daily notes. Basically, it finds any header containing the word "Journal", take the content, and stop at the next header found or the end of the note. If you're looking for the last time you had "fun", just `ctrl+f` inside this note in `read view` and you'll find it.

If you need to import your journal from Daylio like me, you might want to take a look at [obsidian-daylio-parser repository](https://github.com/DeutscheGabanna/Obsidian-Daylio-Parser) on Github, or my [fork of it](https://github.com/mathisgauthey/Obsidian-Daylio-Parser) that works well with my example vault.

### How Do I Use the Workout Log ?

If you right click on the `-Workout-Log` folder and select `Create new note from template`, you can select your workout template. It will be correctly named with a `YYYY-MM-DD_` timestamp and will then be found inside the `Workout Log 💪` callout of your daily note. Nothing fancy, just enough for keeping count.

It is important that the first header of your workout template keep the [templater](https://github.com/SilentVoid13/Templater) code snippet. This is how the timestamp is added to the template file name.

You'll find that I added goals to sections of my workout linked to goals in my `Sport` area. You can do something like this, or not. Experiment with queries and filters from the [dataview](https://blacksmithgu.github.io/obsidian-dataview/) plugin or the [task](https://publish.obsidian.md/tasks/Introduction) plugin, you can make very powerful things without much effort. You just need to read their doc !

> Take extra care where moving file from the `5-Templates` folder to the archives or anywhere else. **You should remove the templater code from everywhere before doing so**, otherwise it might end up in an infinite loop of template file creation because of `filename-heading-sync` and `templater` plugin working asynchronously.

### How Do I Use the Media Backlog ?

Your Media Backlog 🎮 file is a simple Kanban board. It is self explicit, just keep in mind that the daily note's `Ongoing Medias 🎮` callout will query some kanban cards. But only the one inside columns that contains `Doing`. That'll help you to know what you could be doing during your daily spare time today.

There's some predefined tags with emojis that you can find in the colorful-tag plugin settings.

If you finished something, you can add a date on the kanban board by using the `Add a date` command from right clicking the card.

You might want to add the `#ongoing` tag if there's going to be a sequel and you want to get back to it later on.

### How Do I Use the The Read-it-later and Bookmark Manager ?

This part is pretty simple. You simply need to connect your Omnivore account, add some pages to your inbox. It will then be synced to Obsidian inside the `_Sources` folder each time you use the `Omnivore button` on Obsidian left side bar. It has been configured to import inside a different daily folder based on when you saved the link. The generated markdown file will contains the document notes from Omnivore, then your highlight and content notes, and finally the whole converted markdown page. Simple as that !

It allows you to simply search inside Obsidian if you want to find past knowledge you came across. That's why I love it.

I wont describe too much functionalities here as the app and plugin are in active development. I'll let you discover the magic with their [documentation](https://docs.omnivore.app/).

### How Do I Use The Note Sharing Process ?

The whole process is detailed in [another post](./Obsidian%20Publish%20Alternative,%20How%20to%20One-click%20Upload%20Your%20Notes%20on%20Your%20Own%20Website.md).

The note sharing process requires to create a [Hugo](https://gohugo.io/) website first on Github Pages. Once it's done, you can simply change the `share` boolean to `true` in the note frontmatter, then select the command `Upload filename to DEFAULT` of the [obsidian-github-publisher](https://github.com/ObsidianPublisher/obsidian-github-publisher) plugin from the note drop down menu. It will use some [regex](https://www.wikiwand.com/en/Regular_expression) to convert wikilinks to standard [Hugo links formatting](https://gohugo.io/content-management/cross-references/), commit and push to the relevant repository on Github, make a pull request that'll be automatically accepted (allowing for easy reversing changes), and then use some Github Actions to build your website.

Attachments are automatically sent as well as linked notes as long as they have the `share` boolean set to `true` as well.

The posts will be sent to the `content/post` folder and the attachments to the `content/images` folder.

## Detailed Explanations Links

- [here](./Why%20Using%20Obsidian%20for%20Life%20Management.md)
- [guide](./Obsidian%20Publish%20Alternative,%20How%20to%20One-click%20Upload%20Your%20Notes%20on%20Your%20Own%20Website.md)

## How is the Vault Organised ?

> This setup relies heavily on Obsidian wikilinks and tags for task and project management, but also for attachment cleaning. One should take the habit to use them.

- `_Media` folder : Storing all attachments (images and pdf for example) in the same folder using the `YYYY-MM-DD_filename.extension` pattern thanks to [obsidian-paste-image-rename](https://github.com/reorx/obsidian-paste-image-rename). Beware, all the attachments must be linked inside a note, otherwise the use of plugins such as [Find orphaned files and broken links](https://github.com/Vinzent03/find-unlinked-files) and [Clean unused images](https://github.com/ozntel/oz-clear-unused-images-obsidian) might delete them.
- `_Sources` folder : Storing all the websites sources you saved automatically using [Omnivore](https://omnivore.app/) or manually using [markdownload](https://github.com/deathau/markdownload).
- `-Daily-Notes` folder : Storing daily notes for **tasks** management, quick-notes and journaling.
- `-Periodic-Notes` folder : Storing weekly, monthly, quarterly and yearly notes for **project** management and journaling.
- `-Workout_Log` folder : Storing your workout logs.
- `0-Inbox` folder : Newly created files automatically goes here. However, using the file explorer on the left you can create note wherever you want.
- `1-Projects` folder : Project files containing markdown notes, tasks, embedded attachments (attachments are still stored inside the `_Media` folder, but you can embed them inside projet notes), wikilinks to useful notes or whatever you need to complete your projects. *That's the real power of Obsidian, you can organise projects naturally, just like you would do using a piece of paper.*
- `2-Areas` folder : Containing main `areas of responsibility of your life` files. That's in these files that you'll create projects in the form of tasks with a wikilink to a project note.
- `3-Resources` folder : Contains all of your notes and stuff !
- `4-Archives` folder : Contains done or cancelled projects, no longer relevant and old resources that you might never need again… But you might also need once again, so you archive it instead of deleting it.
- `5-Templates` folder : Contains all your file templates used by the [templater plugin](https://github.com/SilentVoid13/Templater).
- `Vision, Purpose and Principles ⚙️` file : Contains your visions (3-5 year goals), who you are, what is your purpose in life and what are your principles.
- `Taskboard ✅` file : Useful to scan for unplanned tasks across your vault.
- `Someday Maybe 💭` file : Write someday maybe projects, things to do one day and goals you'd like to achieve.
- `Media Backlog 🎮` file : Kanban board of your upcoming, current and past media consumption.
- `Journal 📓` file : Contains all the Journal entries of your daily notes.
- `Dashboard 🗺️` file : Contains your active projects by dates, areas and your currently unplanned projects.

## Plugin List

```
 Plugins enabled: 35
  1: Calendar v1.5.10
  2: Better Word Count v0.9.6
  3: Auto Link Title v1.4.1
  4: Clear Unused Images v1.1.0
  5: Code Editor Shortcuts v1.14.0
  6: Colorful Tag v1.3.2
  7: Dataview v0.5.56
  8: File Explorer Note Count v1.2.1
  9: Filename Heading Sync v1.9.0
  10: Find orphaned files and broken links v1.9.0
  11: Footnote Shortcut v0.1.2
  12: Frontmatter Tag Suggest v0.4.1
  13: Icon Folder v2.1.2
  14: Kanban v1.5.3
  15: Linter v1.17.0
  16: Note Refactor v1.7.1
  17: Paste image rename v1.6.1
  18: Paste URL into selection v1.7.0
  19: Periodic Notes v0.0.17
  20: Style Settings v1.0.6
  21: Symbols Prettifier v1.1.1
  22: Tag Wrangler v0.5.11
  23: Tasks v4.3.0
  24: Templater v1.16.0
  25: Todoist Plugin v1.11.1
  26: Omnivore v1.5.3
  27: Better footnote v1.0.1
  28: Editing Toolbar v2.3.1
  29: Image Toolkit v1.3.1
  30: Quick Explorer v0.2.8
  31: Show Whitespace v0.3.1
  32: Google Calendar v1.9.19
  33: Github Publisher v6.3.2
  34: Archiver v0.23.2
  35: Commander v0.5.0
```

[^1]: Project.Areas.Resources.Archives
[^2]: Getting Things Done
