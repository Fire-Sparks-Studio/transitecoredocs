---
title: Debugging
description: Learn how to identify, understand and resolve issues while developing TransitCore addons.
---

# Debugging

Developing addons inevitably involves testing, experimentation and debugging.

TransitCore provides detailed logging, validation and runtime error reporting to help you quickly identify problems without affecting the rest of the framework.

<Alert severity="info">

A runtime error inside one addon never prevents TransitCore or other addons from loading. The faulty addon is isolated and disabled automatically.

</Alert>

## Understanding the startup logs

Every time Minecraft starts, TransitCore records information about the loading process.

Typical information includes:

- Framework initialization
- Addon discovery
- Manifest validation
- Dependency resolution
- LuaTC execution
- Resource registration
- Runtime errors
- Warnings

Monitoring the console during development is the easiest way to detect problems.

```text title="Console output"
[TransitCore] Initializing...

[TransitCore] Discovering addons...

[TransitCore] Loading addon "French Signals"

[TransitCore] Registering resources...

[TransitCore] Addon loaded successfully.
```

## Log files

TransitCore stores detailed logs inside its dedicated log directory.

```text title="Log directory"
.minecraft/
└── TC_Logs/
```

The log files contain additional information that may not appear directly in the Minecraft console.

They are especially useful when reporting issues or diagnosing unexpected behavior.

## Common startup errors

Some errors occur before the addon is even executed.

These include:

- Missing `addon.yaml`
- Invalid manifest
- Missing entry script
- Invalid version
- Missing dependency
- Unsupported TransitCore version

Example:

```text title="Manifest error"
[TransitCore] Loading addon "Example"

[TransitCore] Invalid addon manifest.

[TransitCore] Addon disabled.
```

## LuaTC runtime errors

Errors may also occur while executing LuaTC scripts.

```luatc title="Example"
local train = nil

train:setName("Example")
```

Produces:

```text title="Runtime error"
LuaTC Runtime Error

Attempt to index a nil value.
```

The stack trace identifies the file and line responsible for the error.

## Syntax errors

LuaTC validates scripts before execution.

Example:

```luatc title="Invalid script"
local value =
```

Produces:

```text title="Syntax error"
Unexpected end of file.
```

Syntax errors prevent the script from executing.

## Resource errors

TransitCore also validates resources referenced by addons.

Typical issues include:

- Missing models
- Missing textures
- Missing animations
- Missing sounds
- Invalid file paths
- Duplicate identifiers

Whenever possible, TransitCore reports the exact resource that caused the problem.

## Dependency errors

If an addon depends on another addon that is not installed, TransitCore reports the issue.

```text title="Dependency error"
Missing dependency:

tc_common
```

The addon is skipped until every required dependency becomes available.

## Reading stack traces

When an unexpected error occurs, TransitCore displays a stack trace.

The stack trace indicates:

- The file where the error occurred.
- The line number.
- The function being executed.
- The sequence of calls leading to the error.

Reading the stack trace is often the fastest way to identify the source of a problem.

## Debugging tips

When debugging an addon:

- Read the first reported error.
- Avoid ignoring warnings.
- Test changes incrementally.
- Verify file names and paths.
- Check the addon manifest.
- Confirm that dependencies are installed.
- Restart the game after major changes if hot reload is unavailable.

<Alert severity="success">

Most issues can be resolved by carefully reading the first error reported in the logs. Later errors are often a consequence of the first one.

</Alert>

## Logging information

LuaTC provides logging utilities that help developers inspect addon behavior.

```luatc title="Logging a message"
tc.logger:info("Vehicle registered.")

tc.logger:warning("Configuration missing.")

tc.logger:error("Unable to load resource.")
```

Logging important steps during initialization makes debugging much easier.

## Isolating problems

When an addon becomes large, isolate problems by testing one system at a time.

For example:

- Test the manifest.
- Test LuaTC scripts.
- Test models.
- Test animations.
- Test sounds.
- Test user interfaces.

Adding components progressively makes it easier to determine where an issue originates.

## Reporting issues

If you encounter a problem you cannot resolve, include the following information when reporting it:

- TransitCore version
- Minecraft version
- NeoForge version
- Addon version
- Complete log files
- Steps to reproduce the issue
- Screenshots if applicable

Providing detailed information significantly improves the quality of bug reports.

## Best practices

To reduce debugging time:

- Keep scripts modular.
- Use meaningful variable names.
- Validate resources before testing.
- Organize files consistently.
- Log important events during startup.
- Read warnings before they become errors.

Following these practices will make your addons easier to maintain and troubleshoot.

## Next Steps

Congratulations!

You have completed the **Getting Started** section.

Continue with **LuaTC Overview** to begin learning the TransitCore scripting language in greater detail.