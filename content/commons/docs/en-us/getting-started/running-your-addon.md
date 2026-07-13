---
title: Running Your Addon
description: Learn how TransitCore discovers, loads and executes addons during startup.
---

# Running Your Addon

Once your addon has been created, TransitCore automatically detects and loads it during startup.

This page explains how the loading process works, what happens when an addon starts and how to diagnose common loading issues.

<Alert severity="info">

TransitCore automatically scans every addon located inside the `TC_Addons` directory. No additional configuration is required.

</Alert>

## Startup sequence

Each time Minecraft starts, TransitCore performs the following steps.

1. Initialize the TransitCore framework.
2. Scan the `TC_Addons` directory.
3. Detect every available addon.
4. Read each `addon.yaml` manifest.
5. Validate addon information.
6. Resolve dependencies.
7. Load LuaTC scripts.
8. Register resources.
9. Enable the addon.

If every step completes successfully, the addon becomes available immediately.

## Addon discovery

TransitCore searches every folder located inside the `TC_Addons` directory.

```text title="Addon discovery"
.minecraft/
└── TC_Addons/
    ├── MyFirstAddon/
    ├── FrenchSignals/
    ├── JapaneseRollingStock/
    └── ModernStations/
```

Each folder is treated as a potential addon.

TransitCore ignores directories that do not contain a valid `addon.yaml`.

## Manifest validation

Before loading an addon, TransitCore validates its manifest.

Validation includes:

- Addon identifier
- Version
- Entry point
- Dependencies
- Supported TransitCore version

If validation fails, the addon is skipped.

```text title="Console output"
[TransitCore] Loading addon "French Signals"

[TransitCore] Invalid addon manifest.

[TransitCore] Addon disabled.
```

## Loading LuaTC

Once the manifest has been validated, TransitCore executes the entry script.

```yaml title="addon.yaml"
entry: scripts/main.luatc
```

The specified script becomes the starting point of the addon.

Additional scripts may then be loaded by the addon itself.

## Resource registration

During startup, TransitCore registers every supported resource contained in the addon.

This may include:

- Vehicles
- Tracks
- Signals
- Models
- Textures
- Animations
- Sounds
- User interfaces
- Localization files

Resources become available once the addon has finished loading.

## Console output

A successful startup may produce output similar to the following.

```text title="Console output"
[TransitCore] Initializing...

[TransitCore] Discovering addons...

[TransitCore] Loading "My First Addon"

[TransitCore] Registering resources...

[TransitCore] Addon loaded successfully.
```

## Loading errors

If an error occurs while loading an addon, TransitCore reports it in the logs.

```text title="Console output"
[TransitCore] Loading "My First Addon"

[TransitCore] LuaTC Runtime Error

[TransitCore] Addon disabled.
```

<Alert severity="warning" title="Addon Isolation">

A faulty addon never prevents TransitCore from starting.

Only the addon that caused the error is disabled. Every remaining addon continues loading normally.

</Alert>

## Reading the logs

TransitCore generates detailed log files during startup.

These logs contain useful information about:

- Loaded addons
- Validation errors
- LuaTC exceptions
- Missing resources
- Dependency issues

Log files are stored inside:

```text title="Log directory"
.minecraft/
└── TC_Logs/
```

Whenever an addon fails to load, checking the logs should always be the first troubleshooting step.

## Reloading addons

Depending on the current development tools and configuration, TransitCore may support reloading addons without restarting Minecraft.

When available, reloading allows developers to quickly test LuaTC scripts and configuration changes.

<Alert severity="info">

Support for live reloading depends on the development environment and the type of resources being modified.

Some resources may still require restarting Minecraft.

</Alert>

## Troubleshooting

If your addon does not load correctly, verify the following:

- The addon is located inside `TC_Addons`.
- The `addon.yaml` file exists.
- The manifest is valid.
- The entry script exists.
- All dependencies are installed.
- No LuaTC errors are present.
- TransitCore and the addon are compatible.

Most loading issues can be resolved by checking these items.

## Best practices

To simplify development:

- Keep startup scripts small.
- Register resources in dedicated modules.
- Read the logs after every startup.
- Test changes frequently.
- Fix warnings before they become errors.

Following these practices makes addons easier to debug and maintain.

## Next Steps

Continue with **Debugging** to learn how to identify, understand and resolve errors while developing TransitCore addons.