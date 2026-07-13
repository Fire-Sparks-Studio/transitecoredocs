---
title: Project structure
description: Discover how a TransitCore project is organized and how the different elements of an Addon work together.
---

# Project structure

Each TransitCore Addon follows a clearly defined project structure.

A consistent organization facilitates maintenance, encourages collaboration between developers and allows TransitCore to automatically detect scripts, resources and configuration files.

<Alert severity="info">

TransitCore automatically analyzes the content of an Addon and loads supported resources based on the recommended project structure.

</Alert>

## Standard project structure

A TransitCore Addon is generally organized as follows.

```text title="Example Addon structure"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── animations/
├── sounds/
├── lang/
├── ui/
└── README.md
```

Each folder has a very specific role.

## Project root

The project root contains the Addon manifest as well as all the resources used.

```text title="Project root"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
└── ...
```

TransitCore identifies an Addon by the presence of the `addon.yaml` file.

Without this file, the folder is ignored during startup.

## The manifest

The manifest describes the main information of the Addon.

It notably contains:

- The name of the Addon.
- Its unique identifier.
- Its version.
- Its author.
- Its description.
- Its dependencies.
- The minimum version of TransitCore required.

The manifest is always located at the root of the project.

```text title="Manifest location"
MyAddon/
└── addon.yaml
```

The operation of the manifest is detailed in the **Addon Manifest** page.

## Scripts

The `scripts` folder contains all LuaTC scripts executed by TransitCore.

```text title="Scripts folder"
scripts/
├── main.luatc
├── vehicles/
├── signals/
├── ui/
└── utilities/
```

Scripts notably allow defining:

- Vehicles.
- Signals.
- Components.
- Events.
- Game mechanics.
- User interfaces.

<Alert severity="success">

Organize your scripts by feature rather than grouping all your code in a single file.

</Alert>

## 3D models

The `models` folder contains all 3D models used by your Addon.

The supported formats depend on the installed model loader.

```text title="Models folder"
models/
├── trains/
├── signals/
├── tracks/
├── stations/
└── props/
```

Models are loaded via the **Node** API of TransitCore.

## Textures

Textures are stored in the `textures` folder.

```text title="Textures folder"
textures/
├── vehicles/
├── signals/
├── tracks/
└── ui/
```

Sorting textures by category facilitates their maintenance, especially on large projects.

## Animations

The `animations` folder groups all animations used by the Addon.

```text title="Animations folder"
animations/
├── doors/
├── cab/
├── bogies/
└── pantographs/
```

Animations can then be associated with **Nodes** and controlled from LuaTC.

## Sounds

The `sounds` folder contains all audio resources of the Addon.

```text title="Sounds folder"
sounds/
├── engines/
├── brakes/
├── doors/
├── announcements/
└── ambience/
```

TransitCore supports positional sounds as well as several audio categories.

## Localization

Translation files are stored in the `lang` folder.

```text title="Language files"
lang/
├── en_us.json
├── fr_fr.json
└── ja_jp.json
```

All texts visible to players should be localized rather than directly written in LuaTC scripts.

This makes it easy to offer several languages without modifying the Addon code.

## User interface

Graphic resources and user interface elements are grouped in the `ui` folder.

```text title="User interface folder"
ui/
├── images/
├── icons/
├── layouts/
└── themes/
```

This folder contains all the elements necessary to create your Addon's interfaces.

## Recommended organization

As a project grows, it is advisable to organize files by feature.

For example:

```text title="Example of a large project"
scripts/
├── vehicles/
│   ├── metro/
│   ├── tram/
│   └── train/
├── railway/
├── signaling/
├── stations/
├── ui/
└── shared/
```

This organization improves project readability, facilitates maintenance and promotes code reuse.

<Alert severity="warning">

Avoid placing all your scripts in a single folder. A clear organization makes the project simpler to understand, maintain and evolve.

</Alert>

## Best practices

When creating a new Addon:

- Group files related to the same feature.
- Use explicit file names.
- Avoid duplicated resources.
- Organize your scripts by feature.
- Place reusable code in shared modules.
- Keep the same project structure for all your Addons.

A consistent structure also makes it easier for other developers to contribute to your project.

## Next step

Now that you know the general organization of a TransitCore project, continue with **Folder structure** to discover the role of each folder and how TransitCore uses them.