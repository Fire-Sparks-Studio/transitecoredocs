---
title: Project Structure
description: Learn how TransitCore projects are organized and how the different parts of an addon work together.
---

# Project Structure

Every TransitCore addon follows a well-defined project structure.

Keeping a consistent organization makes projects easier to maintain, simplifies collaboration and allows TransitCore to automatically discover assets, scripts and configuration files.

<Alert severity="info">

TransitCore automatically scans the addon directory and loads supported resources according to the standard project structure.

</Alert>

## Standard project layout

A typical addon looks like the following.

```text title="Example addon structure"
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

Each directory has a specific purpose.

## Root directory

The root directory contains the addon manifest and every resource used by the addon.

```text title="Root directory"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
└── ...
```

TransitCore identifies an addon by the presence of the `addon.yaml` file.

Without this file, the directory is ignored during startup.

## Manifest

The manifest describes the addon.

It contains information such as:

- Addon name
- Identifier
- Version
- Author
- Description
- Dependencies
- Minimum TransitCore version

The manifest is always located at the root of the project.

```text title="Manifest location"
MyAddon/
└── addon.yaml
```

The manifest format is explained in detail in the **Addon Manifest** guide.

## Scripts

The `scripts` directory contains every LuaTC script executed by TransitCore.

```text title="Scripts directory"
scripts/
├── main.luatc
├── vehicles/
├── signals/
├── ui/
└── utilities/
```

Scripts are responsible for defining:

- Vehicles
- Signals
- Components
- Events
- Gameplay logic
- User interfaces

<Alert severity="success">

Keep scripts organized by feature instead of placing everything inside a single file.

</Alert>

## Models

The `models` directory contains every 3D model used by the addon.

Supported formats depend on the installed model loader.

```text title="Models directory"
models/
├── trains/
├── signals/
├── tracks/
├── stations/
└── props/
```

TransitCore loads models through the Node API.

## Textures

Textures used by models are stored inside the `textures` directory.

```text title="Textures directory"
textures/
├── vehicles/
├── signals/
├── tracks/
└── ui/
```

Keeping textures grouped by category improves readability.

## Animations

Animations are stored separately from models.

```text title="Animations directory"
animations/
├── doors/
├── cab/
├── bogies/
└── pantographs/
```

Animations can later be associated with Nodes from LuaTC.

## Sounds

The `sounds` directory contains every audio resource used by the addon.

```text title="Sounds directory"
sounds/
├── engines/
├── brakes/
├── doors/
├── announcements/
└── ambience/
```

TransitCore supports positional audio and multiple sound categories.

## Localization

Translations are stored inside the `lang` directory.

```text title="Language files"
lang/
├── en_us.json
├── fr_fr.json
└── ja_jp.json
```

Every visible text should be localized instead of being hardcoded inside LuaTC scripts.

## User Interface

Graphical resources and interface definitions are stored inside the `ui` directory.

```text title="UI directory"
ui/
├── images/
├── icons/
├── layouts/
└── themes/
```

This directory contains everything related to the user interface of the addon.

## Recommended organization

As projects grow, splitting content by feature becomes increasingly important.

For example:

```text title="Large project example"
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

This approach makes large projects easier to maintain and encourages code reuse.

<Alert severity="warning">

Avoid placing every script inside a single folder. Organizing files by feature makes projects significantly easier to understand and maintain.

</Alert>

## Best practices

When creating a new addon, consider the following recommendations:

- Keep related files together.
- Use descriptive file names.
- Avoid duplicate assets.
- Organize scripts by feature.
- Store reusable code inside shared modules.
- Keep the project structure consistent between addons.

Following the standard structure also makes it easier for other developers to contribute to your project.

## Next Steps

Now that you understand how a TransitCore project is organized, continue with **Folder Structure** to learn how each directory is discovered and managed by the framework.