---
title: Installation
description: Install TransitCore and prepare your development environment.
---

# Installation

This guide explains how to install TransitCore and prepare your development environment for addon development.

By the end of this guide, you will have:

- TransitCore installed.
- A working Minecraft development environment.
- LuaTC support.
- A project ready to create your first addon.

<Alert severity="info">

TransitCore currently targets **NeoForge** and requires a compatible version of Minecraft. Always verify that your game version matches the version supported by TransitCore.

</Alert>

## Requirements

Before installing TransitCore, make sure your computer meets the following requirements.

| Software | Required | Recommended |
|----------|----------|-------------|
| Java | 21 or newer | Latest LTS |
| Minecraft | Supported version | Latest supported version |
| NeoForge | Supported version | Latest supported version |
| Git | Optional | Latest version |
| Visual Studio Code or IntelliJ IDEA | Optional | Latest version |

## Installing TransitCore

Download the latest TransitCore release.

Place the TransitCore mod inside your Minecraft `mods` folder.

```text title="Minecraft directory"
.minecraft/
├── mods/
│   └── transitcore.jar
└── ...
```

Launch Minecraft once to allow TransitCore to generate its working directories.

<Alert severity="success">

After the first launch, TransitCore automatically creates all required folders inside your Minecraft directory.

</Alert>

## Generated folders

TransitCore creates several directories used by the framework.

```text title="TransitCore folders"
.minecraft/
├── TC_Addons/
├── TC_Cache/
├── TC_Logs/
├── TC_Config/
└── mods/
```

| Folder | Description |
|---------|-------------|
| TC_Addons | Contains every installed addon. |
| TC_Cache | Stores generated cache files used by the framework. |
| TC_Logs | Stores TransitCore log files. |
| TC_Config | Contains framework configuration files. |

## Installing LuaTC Support

TransitCore provides official tooling for LuaTC development.

Supported editors include:

- Visual Studio Code
- IntelliJ IDEA

The official extensions provide:

- Syntax highlighting
- Auto-completion
- Diagnostics
- Documentation
- Code navigation
- Formatting

<Alert severity="info">

The LuaTC extensions are optional but highly recommended for addon development.

</Alert>

## Verify your installation

Start Minecraft.

If TransitCore loads successfully, the log should contain a message similar to the following.

```text title="Console output"
[TransitCore] TransitCore successfully initialized.
[TransitCore] Loading addons...
[TransitCore] Ready.
```

If any errors occur, check the TransitCore log files.

```text title="Log directory"
.minecraft/
└── TC_Logs/
```

## Updating TransitCore

To update TransitCore:

1. Close Minecraft.
2. Replace the existing TransitCore JAR.
3. Start Minecraft again.

TransitCore automatically migrates compatible configuration files whenever possible.

<Alert severity="warning">

Always create a backup of your world before updating to a newer version, especially when using alpha or beta releases.

</Alert>

## Uninstalling TransitCore

To completely remove TransitCore:

1. Delete the TransitCore JAR from the `mods` folder.
2. Remove any unused addons from `TC_Addons`.
3. Optionally delete the TransitCore directories.

```text title="Directories to remove"
TC_Addons/
TC_Cache/
TC_Config/
TC_Logs/
```

Removing these folders permanently deletes every installed addon, configuration file and cached data.

## Next Steps

Your development environment is now ready.

Continue with **Project Structure** to learn how a TransitCore project is organized.