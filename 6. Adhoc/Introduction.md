# 6.0 Adhoc Script Language (Game Code/UI Editing)
## 1. Introduction

The Adhoc Scripting Language was introduced in Gran Turismo 4. It is an in-house developed custom scripting language by Polyphony Digital. Generally most of the game code is within them, and its existence is justified by multiple concurrently working developers not having to compile the main executable all at the same time often, as it is usually a time consuming process.

In general, the executable `EBOOT.BIN` is really just the game engine, its framework, car/graphics handler, etc. It only executes what the adhoc scripts are asking it to do.

Before explaining what each file format is, it is important to understand certain folders related to it.
* `projects` - This is where each "menu" is stored, within its corresponding sub-folder. For instance, GT5's main menu is `gttop`. The actual race menu is `race`. The booting process is `boot`.
* `scripts` - Stores function utilities for the projects to use in general. Most importantly, it contains a `main.adc` file. This one also stores utilities but also the critical game loop.
* `products` - This is the least important one. It just defines some UI widgets.

For the formats, there are four to keep in mind.
Format | Editable | Description |
------------ | ------------- | ------------- | 
`.adc` | See Specific Section | **Ad**hoc **C**ompiled - This is the game code itself. It is in a compiled form, so it cannot be edited out of the bat.
`.mproject/mwidget`  | Yes | UI Projects/Widgets -  These are essentially the UI layout definition, and sets properties for each widget. Adhoc Scripts are directly linked to them and manipulates them as a real UI framework.
`.gpb` | Yes | UI Assets - Containers for each project that contains images
`.mpackage` | Yes | GT6 Only. These contain bundles of `.adc` and `.mwidget` files that are properly split. **This file is always loaded for any project first. If missing, the game will fallback to loading an individual script and project file.**
