---
title: Run your Addon
description: Discover how to load, test and update your Addon during development.
---

# Run your Addon

Once your Addon is created, you can launch it directly with TransitCore to verify its operation.

TransitCore automatically detects all Addons present in the `TC_Addons` folder and loads them at game startup.

<Alert severity="info">

Each time Minecraft is launched, TransitCore automatically analyzes the `TC_Addons` folder and loads all Addons whose manifest is valid.

</Alert>

## Verify the project structure

Before launching Minecraft, make sure your project is correctly organized.

```text title="Example structure"

MyAddon/
├── addon.yaml
├── scripts/
│   └── main.luatc
├── models/
├── textures/
└── sounds/

```

The `addon.yaml` file as well as the `scripts` folder are essential for loading your Addon.

## Launch Minecraft

Launch Minecraft with TransitCore installed.

During startup, TransitCore performs several checks:

- Searching for Addons.
- Reading manifests.
- Checking dependencies.
- Loading resources.
- Initializing LuaTC scripts.

If no error is detected, your Addon is loaded automatically.

```text title="Console"

[TransitCore] Loading addon: MyAddon
[TransitCore] Initialising LuaTC runtime...
[TransitCore] Addon loaded successfully.

```

## Verify that the Addon is loaded

After loading, you can consult the console to verify that TransitCore has detected your Addon.

For example:

```text title="Console"

[TransitCore] Loading addon: Metro Pack
[TransitCore] Registering resources...
[TransitCore] Loading scripts...
[TransitCore] Ready.

```

If your Addon does not appear in the logs, check your project structure as well as the content of the `addon.yaml` file.

## Test your scripts

You can display information in the console using the `print()` function.

```luatc title="main.luatc"

print("TransitCore is ready!")

```

This method is very practical to quickly verify that a script is executed.

## Modify an Addon

During development, you will regularly modify your scripts, models and resources.

After each modification:

1. Save your files.
2. Relaunch Minecraft.
3. Check the logs.
4. Test the new features.

This method allows quickly detecting errors.

## Check the logs

TransitCore records all important information in its logs.

```text title="Logs folder"

.minecraft/Config/TC_Config/
└── TC_Logs/

```

The logs notably contain:

- Loaded Addons.
- LuaTC errors.
- Warnings.
- Debug information.
- Framework messages.

<Alert severity="success">

Consult the logs regularly during development. They allow quickly identifying the origin of most problems.

</Alert>

## Update an Addon

When you modify your Addon, remember to also update its version number in the `addon.yaml` file.

```yaml title="addon.yaml"

version: 1.1.0

```

Using consistent versioning facilitates tracking changes and releasing new versions.

## Test progressively

It is recommended to add features one by one.

After each important change:

- Launch Minecraft.
- Check the logs.
- Test only the feature concerned.
- Immediately fix any errors.

This approach makes development simpler and avoids accumulating several problems that are difficult to identify.

## Best practices

During development:

- Test your Addon frequently.
- Fix errors as soon as they appear.
- Regularly update the version number.
- Consult the logs after each launch.
- Add new features progressively.
- Maintain a clear project structure.

<Alert severity="warning">

Avoid developing several important features before testing them. Regular testing makes it much easier to identify the source of a problem.

</Alert>

## Next step

You now know how to load and test an Addon with TransitCore.

Continue with **Debugging** to learn how to analyze errors, interpret logs and resolve the most common problems.