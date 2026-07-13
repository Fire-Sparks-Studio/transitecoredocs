---
title: The basics of LuaTC
description: Discover the basics of LuaTC and learn to write your first TransitCore scripts.
---

# The basics of LuaTC

**LuaTC** is the official scripting language of TransitCore.

Based on Lua, it has been extended to interact with all the systems of the framework, such as vehicles, signals, tracks, components or the world.

Most Addons can be developed entirely in LuaTC, without having to write a single line of Java.

<Alert severity="info">

LuaTC is specially designed for developing TransitCore Addons. It offers APIs dedicated to railway simulation while maintaining the simplicity of Lua.

</Alert>

## Your first script

The entry point of an Addon is generally the `main.luatc` file.

You can write your first script there.

```luatc title="main.luatc"
print("Hello TransitCore!")
```

When the Addon is loaded, this message will be displayed in the console.

## Variables

Variables allow storing information to reuse it later.

```luatc title="Variables"
local trainName = "TGV Duplex"
local maxSpeed = 320
local isElectric = true
```

The `local` keyword creates a variable accessible only in the current script.

It is recommended to use local variables whenever possible.

## Data types

LuaTC reuses the main Lua data types.

| Type | Description |
|------|-------------|
| `string` | Text. |
| `number` | Numeric value. |
| `boolean` | True or false value. |
| `table` | Collection of data. |
| `nil` | Absent value. |

Example:

```luatc title="Types"
local line = "Line A"
local speed = 80
local powered = true
```

## Functions

Functions allow grouping reusable code.

```luatc title="Function"
local function openDoors()

    print("Opening doors")

end

openDoors()
```

Functions can also receive parameters.

```luatc title="Parameters"
local function setSpeed(speed)

    print(speed)

end

setSpeed(120)
```

## Conditions

Conditions allow executing code only when a condition is met.

```luatc title="Condition"
local speed = 120

if speed > 100 then

    print("High speed")

end
```

You can also use `elseif` and `else`.

## Loops

Loops allow repeating an action.

```luatc title="Loop"
for i = 1, 5 do

    print(i)

end
```

There are also `while` and `repeat` loops.

## Tables

Tables are used to store multiple values.

```luatc title="Table"
local stations = {

    "Central Station",
    "University",
    "Airport"

}
```

You can access a value via its index.

```luatc title="Accessing a value"
print(stations[1])
```

## Comments

Comments serve to document your code.

They are ignored during execution.

```luatc title="Comments"
-- This is a comment

--[[

This is
a multiline
comment.

]]
```

Comment only when it adds real value to understanding the code.

## Using the TransitCore API

LuaTC allows interacting directly with TransitCore.

For example, to create a vehicle:

```text title="Create a vehicle"
local vehicle = tc.vehicle.create(tc.VehicleType.TRAIN)

vehicle:setName("TGV Duplex")
vehicle:setMaximumSpeed(320)
```

The different services available are documented in the **API Reference** section.

## Organizing your code

As your Addon evolves, avoid writing everything in `main.luatc`.

Prefer distributing your code across several modules.

```text title="Recommended organization"
scripts/
├── main.luatc
├── vehicles/
├── railway/
├── stations/
├── ui/
└── shared/
```

A clear organization facilitates project maintenance and encourages code reuse.

<Alert severity="success">

A file should ideally have a single responsibility. Prefer several small modules rather than a single script of several hundred lines.

</Alert>

## Errors

An error in a script can prevent certain features from working correctly.

TransitCore automatically displays encountered errors in the logs.

```text title="Example"
[LuaTC] Runtime Error
Attempt to call nil value.
```

Always consult the logs before modifying your code.

## Best practices

When developing in LuaTC:

- use local variables;
- give explicit names to your variables and functions;
- split your code into several modules;
- avoid code duplication;
- test your Addon regularly;
- comment only when useful.

## Next step

You now know the basics of LuaTC and can start developing your own features.

Continue with **Run your Addon** to learn how to launch, test and update your Addons during development.