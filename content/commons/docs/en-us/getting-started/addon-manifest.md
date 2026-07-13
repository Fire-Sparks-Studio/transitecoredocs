---
title: Addon Manifest
description: Learn how the addon manifest works and how TransitCore uses it to identify, validate and load addons.
---

# Addon Manifest

Every TransitCore addon requires a manifest file.

The manifest provides information about the addon and tells TransitCore how it should be loaded.

Without a valid manifest, TransitCore ignores the addon during startup.

<Alert severity="info">

Every addon must contain a file named `addon.yaml` located at the root of the project.

</Alert>

## Manifest location

The manifest must always be placed at the root of the addon directory.

```text title="Addon structure"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
└── ...
```

TransitCore searches for this file when scanning the `TC_Addons` directory.

## Basic manifest

A minimal manifest looks like this.

```yaml title="addon.yaml"
id: my_first_addon
name: My First Addon

version: 1.0.0

author: Your Name

description: My first TransitCore addon.

entry: scripts/main.luatc
```

## Properties

The following table describes the most common manifest properties.

| Property | Required | Description |
|----------|:--------:|-------------|
| `id` | Yes | Unique identifier of the addon. |
| `name` | Yes | Display name shown inside TransitCore. |
| `version` | Yes | Current addon version. |
| `author` | Yes | Addon author. |
| `description` | No | Short description of the addon. |
| `entry` | Yes | Main LuaTC file executed during startup. |

## Addon identifier

Every addon must define a unique identifier.

```yaml title="Example"
id: french_signals
```

Identifiers should:

- Use lowercase letters.
- Use underscores instead of spaces.
- Never change once the addon has been published.

<Alert severity="warning">

Changing an addon identifier after release may break compatibility with saved worlds and addon dependencies.

</Alert>

## Version

The version identifies the current release of the addon.

TransitCore follows Semantic Versioning.

```yaml title="Example"
version: 1.2.0
```

Typical version progression:

| Version | Meaning |
|----------|---------|
| 1.0.0 | First stable release |
| 1.1.0 | New features |
| 1.1.1 | Bug fixes |
| 2.0.0 | Breaking changes |

## Author

The author field identifies the creator of the addon.

```yaml title="Example"
author: Fire Sparks Studio
```

Future versions of TransitCore may support multiple authors.

## Description

The description provides a short summary of the addon.

```yaml title="Example"
description: Adds realistic French railway signals.
```

Descriptions should remain concise.

## Entry point

The entry point specifies which LuaTC script is executed when the addon starts.

```yaml title="Example"
entry: scripts/main.luatc
```

TransitCore loads this file first.

Additional scripts can then be loaded from the entry script.

## Dependencies

An addon can require other addons.

```yaml title="Example"
dependencies:
  - tc_common
  - french_assets
```

TransitCore verifies that every dependency is available before loading the addon.

If a dependency is missing, the addon is not loaded.

<Alert severity="warning">

Missing dependencies prevent an addon from loading but do not stop TransitCore or other addons from starting.

</Alert>

## Supported TransitCore versions

An addon can specify the versions of TransitCore it supports.

```yaml title="Example"
transitcore:

  minimum: 1.0.0

  maximum: 1.x
```

This helps prevent compatibility issues between different framework versions.

## Optional information

Additional metadata may also be included.

```yaml title="Example"
website: https://example.com

repository: https://github.com/example/project

license: LGPL-3.0

issues: https://github.com/example/project/issues
```

These properties are optional but recommended for publicly distributed addons.

## Complete example

```yaml title="addon.yaml"
id: french_signals

name: French Signals

version: 1.2.0

author: Fire Sparks Studio

description: Adds realistic SNCF railway signals.

entry: scripts/main.luatc

dependencies:
  - tc_common

transitcore:
  minimum: 1.0.0

website: https://example.com

repository: https://github.com/example/project

license: LGPL-3.0
```

## Validation

During startup, TransitCore validates every manifest before loading the addon.

Validation includes:

- Required properties.
- Identifier format.
- Version format.
- Entry file.
- Dependency resolution.
- TransitCore compatibility.

If validation fails, the addon is skipped.

```text title="Console output"
[TransitCore] Loading addon "French Signals"

[TransitCore] Invalid manifest.

[TransitCore] Addon disabled.
```

<Alert severity="danger" title="Manifest Errors">

An invalid manifest prevents the addon from loading.

TransitCore reports the error in the logs and continues loading every remaining addon.

</Alert>

## Best practices

When creating a manifest:

- Use a unique identifier.
- Follow Semantic Versioning.
- Keep the description concise.
- Declare every required dependency.
- Specify supported TransitCore versions.
- Keep the manifest at the root of the project.

## Next Steps

Continue with **LuaTC Basics** to learn the fundamentals of the LuaTC scripting language and begin writing your first TransitCore scripts.