---
title: Addon Manifest
description: Discover the addon.yaml file and learn how to correctly configure your TransitCore Addon.
---

# Addon Manifest

Each TransitCore Addon must mandatory contain an `addon.yaml` file.

This file constitutes the manifest of your Addon. It allows TransitCore to identify it, verify its compatibility and correctly load its resources during startup.

<Alert severity="warning">

The `addon.yaml` file is mandatory. Without it, TransitCore will not detect your Addon.

</Alert>

## Location

The manifest must always be placed at the root of your project.

```text title="Project structure"

MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
└── ...

```

TransitCore automatically looks for this file when loading Addons.

## Minimal example

The simplest manifest looks like this.

```yaml title="addon.yaml"

id: my_first_addon
name: My First Addon
version: 1.0.0
author: YourName
description: My first TransitCore Addon.

```

This file contains the essential information necessary for loading your Addon.

## General structure

Here is a more complete example.

```yaml title="addon.yaml"

id: metro_pack
name: Metro Pack
version: 1.2.0

author: Fire Sparks Studio
description: Adds several realistic metros.

website: https://example.com
license: MIT

transitcore:
  minimum: 1.0.0

dependencies:
  - common_assets
  - railway_signals

```

Not all properties are mandatory.

## Main properties

| Property | Mandatory | Description |
|-----------|-------------|-------------|
| `id` | Yes | Unique identifier of the Addon. |
| `name` | Yes | Displayed name of the Addon. |
| `version` | Yes | Current version of the Addon. |
| `author` | Yes | Main author. |
| `description` | Yes | Short description of the Addon. |
| `website` | No | Official website. |
| `license` | No | Project license. |
| `dependencies` | No | List of dependencies. |

## The identifier

The identifier (`id`) is used internally by TransitCore.

It must be unique.

```yaml title="Example"

id: metro_pack

```

It is recommended:

- to use only lowercase letters;
- to separate words with underscores (`_`);
- to avoid spaces and special characters.

Examples:

```yaml title="Valid examples"

id: metro_pack
id: french_trains
id: lyon_network

```

## The name

The name is displayed to players as well as in the logs.

```yaml title="Example"

name: Metro Pack

```

Unlike the identifier, the name can contain spaces, uppercase letters and special characters.

## The version

Each Addon has a version.

```yaml title="Example"

version: 1.0.0

```

It is recommended to use the **SemVer** format:

```
MAJOR.MINOR.PATCH
```

For example:

- `1.0.0`
- `1.2.4`
- `2.0.0`

## The author

This property indicates the main creator of the Addon.

```yaml title="Example"

author: Fire Sparks Studio

```

If several people work on the project, you can indicate the responsible organization.

## The description

The description briefly presents your Addon.

```yaml title="Example"

description: Adds several realistic French metros.

```

Try to remain concise while clearly explaining the content of your Addon.

## The website

You can provide an official website.

```yaml title="Example"

website: https://example.com

```

This property is optional.

## The license

The license indicates the usage conditions of your Addon.

```yaml title="Example"

license: MIT

```

Among the most common licenses:

- MIT
- LGPL-3.0
- GPL-3.0
- Apache-2.0

## TransitCore compatibility

You can specify the minimum version of TransitCore required.

```yaml title="Example"

transitcore:
  minimum: 1.0.0

```

TransitCore will refuse to load an Addon incompatible with the installed version.

## Dependencies

An Addon can depend on other Addons.

```yaml title="Example"

dependencies:
  - common_assets
  - french_signals

```

Before loading your Addon, TransitCore automatically checks that all dependencies are available.

<Alert severity="info">

If a dependency is missing, the Addon concerned will not be loaded to avoid any unexpected behavior.

</Alert>

## Validation

At startup, TransitCore automatically checks:

- the presence of the manifest;
- mandatory properties;
- the syntax of the file;
- version compatibility;
- declared dependencies.

In case of an error, a detailed message is recorded in the logs.

```text title="Example"

[TransitCore] Invalid addon manifest.
Missing required property: id

```

## Best practices

To ensure the compatibility of your Addon:

- choose a unique identifier;
- use semantic versioning (SemVer);
- write a clear description;
- declare all necessary dependencies;
- update the version with each new release.

<Alert severity="success">

The manifest is the first thing TransitCore reads when loading an Addon. Take the time to keep it up to date, as it contains all the essential information about your project.

</Alert>

## Next step

Your manifest is now correctly configured.

You can continue with **The basics of LuaTC** to discover the scripting language used to develop TransitCore Addons.