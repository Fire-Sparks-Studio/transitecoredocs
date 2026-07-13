---
title: Folder structure
description: Discover how TransitCore organizes an Addon's files and the role of each folder.
---

# Folder structure

Each TransitCore Addon follows a standardized file organization.

Adopting this structure facilitates project maintenance, improves its readability and allows TransitCore to automatically detect resources without additional configuration.

<Alert severity="info">

TransitCore automatically analyzes an Addon's known folders. By following the recommended structure, all resources are detected and loaded consistently.

</Alert>

## Standard structure

An Addon is generally organized as follows.

```text title="Addon structure"
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

Each folder has a well-defined role.

## Project root

The root contains the Addon manifest as well as all the resources used by it.

```text title="Project root"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
└── ...
```

TransitCore identifies an Addon through the `addon.yaml` file.

Without this file, the folder is ignored during startup.

## scripts/

The `scripts` folder contains all LuaTC scripts executed by the Addon.

```text title="Scripts folder"
scripts/
├── main.luatc
├── vehicles/
├── signals/
├── stations/
├── ui/
└── shared/
```

It generally contains:

- Vehicle definitions.
- Signal logic.
- Railway systems.
- Gameplay mechanics.
- Utility modules.
- Shared libraries.

The `main.luatc` file is generally used as the Addon's entry point.

## models/

The `models` folder contains all 3D models used by the Addon.

```text title="Models folder"
models/
├── vehicles/
├── signals/
├── tracks/
├── stations/
└── props/
```

The supported formats depend on the installed model loader.

Models are then loaded via the **Node** system and can be manipulated from LuaTC.

## textures/

All textures are grouped in the `textures` folder.

```text title="Textures folder"
textures/
├── vehicles/
├── signals/
├── tracks/
├── ui/
└── misc/
```

Organizing textures by category simplifies their maintenance, especially as the project grows.

## animations/

The `animations` folder contains all animations used by the models.

```text title="Animations folder"
animations/
├── doors/
├── cab/
├── pantographs/
├── bogies/
└── indicators/
```

Animations are associated with **Nodes** and controlled from LuaTC.

The most common animated elements are:

- Doors.
- Buttons.
- Switches.
- Pantographs.
- Wipers.
- Cab controls.

## sounds/

The `sounds` folder contains all audio resources of the Addon.

```text title="Sounds folder"
sounds/
├── engines/
├── brakes/
├── doors/
├── announcements/
├── ambience/
└── ui/
```

TransitCore automatically detects compatible audio files and makes them accessible via the audio service.

## lang/

The `lang` folder contains translation files.

```text title="Language files"
lang/
├── en_us.json
├── fr_fr.json
├── de_de.json
└── ja_jp.json
```

All texts displayed to the player should be localized rather than directly written in LuaTC scripts.

This makes it possible to offer several languages without modifying the Addon code.

## ui/

The `ui` folder groups all resources related to the user interface.

```text title="User interface folder"
ui/
├── icons/
├── images/
├── layouts/
└── themes/
```

It may notably contain:

- Icons.
- Menus.
- Configuration panels.
- Dashboards.
- Interface textures.

## README.md

Although optional, it is strongly recommended to add a `README.md` file to your Addon.

```text title="Documentation"
README.md
```

This file can contain:

- A presentation of the Addon.
- Installation instructions.
- Compatibility information.
- Known limitations.
- The license.
- Credits.

A well-written README facilitates understanding of the project and encourages community contributions.

## Recommended organization

When your Addon becomes larger, it is advisable to organize files by feature.

```text title="Example of a large Addon"
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

This organization improves code readability, facilitates its maintenance and encourages its reuse.

<Alert severity="success">

Organize your files by feature rather than grouping everything in a single folder. A consistent structure makes Addons simpler to maintain and evolve.

</Alert>

## Folders managed by TransitCore

TransitCore automatically creates several folders in your Minecraft directory.

For example:

```text title="TransitCore folders"
.minecraft/
├── TC_Cache/
├── TC_Logs/
└── TC_Config/
```

These folders are managed automatically by the framework.

It is generally discouraged to modify them manually, unless otherwise indicated in the documentation.

## Best practices

To efficiently organize an Addon:

- Group files related to the same feature.
- Use explicit file names.
- Place reusable code in shared modules.
- Avoid duplicated resources.
- Adopt a consistent naming convention.
- Use the same structure for all your Addons.

A predictable organization facilitates development, maintenance and collaboration.

## Next step

Now that you know the role of each folder, continue with **Your first Addon** to create your first TransitCore project.