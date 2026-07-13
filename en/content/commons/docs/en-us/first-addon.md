---
title: Your first Addon
description: Create your first TransitCore Addon and discover how it is loaded by the framework.
---

# Your first Addon

It is now time to create your first TransitCore Addon.

In this guide, you will create a minimal Addon capable of being detected and loaded automatically by TransitCore.

At the end of this page, you will have a functional project structure on which you can build your future developments.

<Alert severity="info">

An Addon is an independent extension that allows adding new features to TransitCore, such as vehicles, infrastructure, scripts or user interfaces.

</Alert>

## Create the Addon folder

Start by opening the `TC_Addons` folder created by TransitCore.

Then create a new folder that will contain your Addon.

```text title="Initial structure"

TC_Addons/
└── MyFirstAddon/

```

The folder name is free, but it is recommended to use a simple name, without spaces or special characters.

## Create the manifest

Each Addon must mandatory contain an `addon.yaml` file.

This file allows TransitCore to identify the Addon and retrieve its main information.

Create the following file:

```yaml title="addon.yaml"

id: my_first_addon
name: My First Addon
version: 1.0.0
author: YourName
description: My first TransitCore Addon.

```

<Alert severity="success">

The `addon.yaml` file is mandatory. Without it, TransitCore will completely ignore your Addon during startup.

</Alert>

## Add a scripts folder

Now create a `scripts` folder.

Your project should look like this.

```text title="Current structure"

MyFirstAddon/
├── addon.yaml
└── scripts/

```

All LuaTC scripts of your Addon will be placed in this folder.

## Create the entry point

In the `scripts` folder, create a file named `main.luatc`.

This file constitutes the entry point of your Addon.

```text title="Structure"

MyFirstAddon/
├── addon.yaml
└── scripts/
    └── main.luatc

```

## Write your first script

Add the following code in `main.luatc`.

```luatc title="main.luatc"

print("Hello TransitCore!")

```

When TransitCore loads your Addon, this message will be displayed in the console.

## Launch Minecraft

Launch Minecraft with TransitCore installed.

During startup, TransitCore automatically analyzes the `TC_Addons` folder, detects the Addons present and loads those whose manifest is valid.

If everything went correctly, your Addon will be loaded automatically.

```text title="Console"

[TransitCore] Loading addon: My First Addon
Hello TransitCore!
[TransitCore] Addon loaded successfully.

```

<Alert severity="success">

Congratulations! Your first Addon is now loaded by TransitCore.

</Alert>

## Add new resources

You can now enrich your Addon by adding other folders.

For example:

```text title="Complete structure"

MyFirstAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
├── animations/
├── lang/
└── ui/

```

You are not required to create all these folders immediately.

Add only those your Addon needs.

## Test regularly

It is recommended to test your Addon after each important change.

This method allows quickly identifying the source of a problem and facilitates debugging.

Avoid adding a large number of features before checking that everything works correctly.

## Best practices

When creating a new Addon:

- Choose a unique identifier.
- Use a clear project structure.
- Test your Addon regularly.
- Organize your scripts by feature.
- Add new resources progressively.
- Document your project with a `README.md` file.

<Alert severity="warning">

Avoid developing your entire Addon in a single `main.luatc` file. As soon as your project grows, distribute your code in several modules to facilitate its maintenance.

</Alert>

## Next step

Your first Addon is now ready.

You can continue with **Addon Manifest** to discover all the properties available in the `addon.yaml` file and learn how to correctly configure your project.