---
title: LuaTC Basics
description: Learn the fundamentals of LuaTC and understand how scripts interact with TransitCore.
---

# LuaTC Basics

LuaTC is the official scripting language of TransitCore.

It is based on Lua and extends it with APIs specifically designed for railway simulation. Through LuaTC, addons can interact with every major system provided by TransitCore, including vehicles, tracks, signals, animations and user interfaces.

Unlike Java, LuaTC is designed to be simple to learn while remaining powerful enough to create complete addons.

<Alert severity="info">

LuaTC is fully compatible with the Lua language. TransitCore extends it by providing additional APIs, services and annotations specifically designed for addon development.

</Alert>

## Your first script

A LuaTC script is simply a text file with the `.luatc` extension.

```luatc title="main.luatc"
tc.logger:info("Hello TransitCore!")
```

When the addon is loaded, the message is written to the TransitCore log.

## The `tc` namespace

Every LuaTC script has access to the global `tc` namespace.

This namespace provides access to every service exposed by TransitCore.

For example:

```luatc title="Getting a service"
local vehicle = tc.vehicle

local signal = tc.signal

local track = tc.track
```

Each service exposes functions related to a specific part of the framework.

## Variables

Variables are declared using the `local` keyword.

```luatc title="Variables"
local speed = 160

local name = "TGV Duplex"

local enabled = true
```

Whenever possible, prefer local variables instead of global variables.

<Alert severity="success">

Using local variables improves readability and prevents accidental conflicts between scripts.

</Alert>

## Calling methods

LuaTC primarily uses methods to interact with objects.

```luatc title="Calling a method"
train:setName("TGV Duplex")

train:setMaximumSpeed(320)
```

Methods are called using the `:` operator.

This automatically passes the object as the first argument.

## Functions

Functions group reusable logic.

```luatc title="Functions"
local function spawnTrain()

    tc.logger:info("Train spawned.")

end

spawnTrain()
```

Functions make scripts easier to read and maintain.

## Comments

Comments are ignored by TransitCore.

They are useful for documenting your code.

```luatc title="Comments"
-- This is a comment.

local speed = 160
```

## Organizing your code

As projects grow, scripts should be split into multiple files.

```text title="Example"
scripts/
├── main.luatc
├── vehicles/
├── signals/
├── ui/
└── shared/
```

Avoid placing every function inside a single file.

## TransitCore services

Most LuaTC scripts interact with one or more services.

Some of the most commonly used services include:

| Service | Description |
|---------|-------------|
| `tc.vehicle` | Creates and manages vehicles. |
| `tc.track` | Creates and edits railway tracks. |
| `tc.signal` | Manages railway signaling. |
| `tc.physics` | Provides access to the physics engine. |
| `tc.animation` | Controls animations. |
| `tc.audio` | Plays and manages sounds. |
| `tc.world` | Interacts with the Minecraft world. |
| `tc.player` | Interacts with players. |

Each service is documented in the **LuaTC** and **API Reference** sections.

## Error handling

If a LuaTC script throws an error, TransitCore reports it in the logs.

The framework automatically disables the faulty addon without affecting the remaining addons.

```text title="Example"
[TransitCore] Loading addon "Example"

[TransitCore] LuaTC Runtime Error

[TransitCore] Addon disabled.
```

<Alert severity="warning">

Errors inside one addon never prevent TransitCore from loading the framework or other addons.

</Alert>

## Best practices

When writing LuaTC scripts:

- Keep functions short and focused.
- Prefer local variables.
- Organize scripts by feature.
- Write descriptive names.
- Comment complex logic when necessary.
- Split large projects into multiple modules.

Following these practices will make your addon easier to maintain as it grows.

## What's next?

You now understand the basic structure of a LuaTC script.

Continue with **Running Your Addon** to learn how TransitCore loads, executes and reloads LuaTC addons during development.