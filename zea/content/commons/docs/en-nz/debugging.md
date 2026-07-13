---
title: Debugging
description: Learn to identify, understand and fix errors encountered during the development of your TransitCore Addons.
---

# Debugging

Debugging is an essential step in developing an Addon.

Even the simplest projects can encounter syntax errors, configuration problems or unexpected behaviors. TransitCore provides several tools to quickly identify them.

<Alert severity="info">

When an error occurs, TransitCore tries to provide a message as precise as possible to help you quickly identify its source.

</Alert>

## Logs

TransitCore records all important information in its logs.

You will notably find:

- Loaded Addons.
- LuaTC errors.
- Warnings.
- Loading errors.
- Diagnostic information.

The logs are available in the following folder.

```text title="Logs folder"

.minecraft/
└── TC_Logs/

```

It is recommended to consult the logs before any modification to your code.

## Reading an error message

When an error occurs, TransitCore generally displays a message similar to this one.

```text title="Example"

[LuaTC] Runtime Error
Attempt to call nil value.

```

This message indicates:

- The system concerned.
- The type of error.
- A description of the problem.

In this example, a non-existent function was called.

## Syntax errors

Syntax errors prevent a script from being loaded.

For example:

```luatc title="Incorrect"

local speed =

```

TransitCore will immediately report this error when loading the script.

Always fix syntax errors before continuing your tests.

## Runtime errors

A runtime error occurs when a script executes, but encounters an unexpected situation.

For example:

```luatc title="Incorrect"

local train = nil

train:setSpeed(80)

```

Since `train` does not exist, LuaTC generates an error.

Before using a variable, always make sure it contains a valid value.

## Using print()

The `print()` function is one of the simplest tools to understand a script's behavior.

```luatc title="Example"

print("Initializing the Addon...")

```

You can also display the value of a variable.

```luatc title="Displaying a variable"

print(speed)

```

These messages will appear directly in the console as well as in the logs.

## Verify the manifest

If your Addon is not loaded, first check the `addon.yaml` file.

The most frequent errors are:

- a missing identifier;
- a missing mandatory property;
- a YAML syntax error;
- an incompatible version of TransitCore.

```text title="Example"

[TransitCore] Invalid addon manifest.
Missing required property: id

```

## Verify dependencies

If your Addon depends on another Addon, make sure it is properly installed.

For example:

```yaml title="addon.yaml"

dependencies:
  - common_assets

```

If a dependency is missing, TransitCore will automatically disable the Addon concerned.

## Debug progressively

When developing a new feature:

1. Add a small change.
2. Launch Minecraft.
3. Check the logs.
4. Test the behavior.
5. Fix any errors.

This method is much more effective than adding several hundred lines of code before performing a first test.

<Alert severity="success">

Develop progressively. Testing regularly makes it much easier to locate errors.

</Alert>

## Common errors

| Problem                    | Possible cause                                                                      |
| -------------------------- | ----------------------------------------------------------------------------------- |
| The Addon does not load    | The `addon.yaml` file is missing or invalid.                        |
| No script executes         | The `main.luatc` file is missing or contains an error.              |
| A resource is not found    | The file path is incorrect.                                         |
| A function causes an error | A variable is `nil` or a parameter is invalid.                      |
| An Addon is disabled       | A dependency is missing or the TransitCore version is incompatible. |

## Best practices

To facilitate debugging:

- Consult the logs after each launch.
- Test one feature at a time.
- Use `print()` to track the execution of your scripts.
- Fix errors as soon as they appear.
- Organize your code in small modules that are easy to maintain.

<Alert severity="warning">

Avoid hiding errors or ignoring them. Even if your Addon seems to work, an unfixed error can cause unexpected behaviors or make diagnosis more difficult later on.

</Alert>

## Need help?

If you cannot resolve a problem:

- Consult the TransitCore logs.
- Check the API documentation.
- Compare your code with the provided examples.
- Reproduce the problem in a minimal project before asking for help.

Providing the complete error message as well as the logs concerned will allow obtaining a faster and more precise response.

## Congratulations!

You have completed the **Getting started** section.

You now know the basics of TransitCore, know how to create an Addon, organize your project, write LuaTC scripts, run your Addon and diagnose the most common errors.

You are now ready to explore the rest of the documentation, notably the **Guides**, **LuaTC** and the **API Reference**, to develop more complete Addons.