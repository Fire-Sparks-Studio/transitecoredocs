---
title: Your First Addon
description: Create your first TransitCore addon and learn how addons are discovered and loaded.
---

# Your First Addon

In this guide, you will create your first TransitCore addon.

The objective is not to create a complete train or railway system, but to understand how an addon is structured and how TransitCore loads it.

By the end of this guide, you will have:

- Created your first addon.
- Learned the required project structure.
- Written your first LuaTC script.
- Successfully loaded your addon in TransitCore.

<Alert severity="info">

Every TransitCore addon is loaded independently. If one addon fails to load, TransitCore continues loading every other addon.

</Alert>

## Creating the addon directory

TransitCore automatically searches for addons inside the `TC_Addons` directory.

Create a new folder.

```text title="Addon directory"
.minecraft/
└── TC_Addons/
    └── MyFirstAddon/
```

The folder name can be anything, but it should match the name of your project.

## Creating the manifest

Every addon requires a manifest file named `addon.yaml`.

Create the following file.

```yaml title="addon.yaml"
id: my_first_addon
name: My First Addon
version: 1.0.0

author: Your Name

description: My first TransitCore addon.

entry: scripts/main.luatc
```

The manifest tells TransitCore how to identify and load your addon.

Without this file, the directory is ignored.

## Creating the project structure

Create the following directories.

```text title="Project structure"
MyFirstAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

Most of these folders are empty for now, but they will be used later as your addon grows.

## Creating your first LuaTC script

Inside the `scripts` directory, create a file named `main.luatc`.

```luatc title="scripts/main.luatc"
tc.logger:info("Hello TransitCore!")
```

This script writes a message to the TransitCore log during startup.

<Alert severity="success">

Congratulations! You have written your first LuaTC script.

</Alert>

## Loading the addon

Start Minecraft with TransitCore installed.

During startup, TransitCore scans every directory inside `TC_Addons`.

If the manifest is valid, the addon is loaded automatically.

A successful startup should produce a message similar to the following.

```text title="Console output"
[TransitCore] Loading addon "My First Addon"
[TransitCore] Hello TransitCore!
[TransitCore] Addon loaded successfully.
```

## Understanding what happened

During startup, TransitCore performs several steps.

1. Scan the `TC_Addons` directory.
2. Detect every addon.
3. Read each `addon.yaml`.
4. Validate the manifest.
5. Load LuaTC scripts.
6. Register resources.
7. Enable the addon.

This process is repeated for every installed addon.

## Handling errors

If an addon contains an error, TransitCore reports the problem without stopping the framework.

```text title="Console output"
[TransitCore] Loading addon "My First Addon"
[TransitCore] Error while loading addon.
[TransitCore] Addon disabled.
```

<Alert severity="warning" title="Addon Isolation">

A faulty addon cannot prevent TransitCore from starting.

Only the addon that caused the error is disabled. Every other addon continues loading normally.

</Alert>

## What's next?

Your addon currently contains a single LuaTC script.

The next step is to start creating actual content such as:

- Vehicles
- Tracks
- Signals
- Stations
- Components
- User interfaces

As your project grows, you will also add models, textures, animations and sounds.

## Project recap

Your project should now look like this.

```text title="Current project structure"
MyFirstAddon/
├── addon.yaml
├── scripts/
│   └── main.luatc
├── models/
├── textures/
├── sounds/
└── lang/
```

## Next Steps

Continue with **Addon Manifest** to learn how the manifest works and discover every available configuration option.