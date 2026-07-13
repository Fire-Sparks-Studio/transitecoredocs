---
title: Overview
description: Learn what TransitCore is, how it works, and why it was created.
---

# Overview

Welcome to **TransitCore**.

TransitCore is a modular railway simulation framework for Minecraft designed to build realistic railway networks through a powerful addon system and the **LuaTC** scripting language.

Rather than providing a predefined collection of vehicles, TransitCore provides the engine responsible for simulation, rendering, networking, signaling and physics. Vehicles, infrastructure and additional content are distributed as independent addons.

<Alert severity="info">

TransitCore separates the **engine** from the **content**. The framework provides the systems, while addons provide vehicles, tracks, signals, stations and every other railway asset.

</Alert>

## Why TransitCore?

TransitCore was designed around four fundamental principles.

### Realism

The objective is to reproduce railway systems as accurately as possible while remaining fully integrated into Minecraft.

The framework includes support for:

- Advanced vehicle simulation
- Realistic braking systems
- Railway signaling
- Electrical systems
- Passenger operations
- Multiplayer synchronization
- High-speed railway operations

### Modularity

Everything in TransitCore is modular.

The framework itself only contains the simulation engine.

Railway vehicles, infrastructure, sounds, textures, user interfaces and gameplay extensions are distributed as addons that can be installed, updated or removed independently.

### Performance

TransitCore has been designed to efficiently handle large railway networks.

Rendering, physics, networking and simulation are optimized to reduce unnecessary calculations while maintaining accurate behaviour.

### Extensibility

Every feature exposed by TransitCore is accessible through **LuaTC**, the official scripting language of the framework.

Developers can create complete addons without modifying the Java source code.

## Architecture

TransitCore is composed of multiple independent systems working together.

```text title="TransitCore Architecture"
TransitCore
├── Core Engine
├── Physics Engine
├── Rendering Engine
├── Railway Engine
├── Signaling Engine
├── Electrical Engine
├── Audio Engine
├── Animation Engine
├── Networking Engine
├── LuaTC Runtime
└── Addon Loader
```

Each subsystem is responsible for a specific part of the framework and communicates through stable public APIs.

## LuaTC

LuaTC is the official scripting language used by TransitCore.

It extends Lua with APIs specifically designed for railway simulation, allowing developers to interact with the framework without accessing Minecraft internals.

```luatc title="Creating a simple vehicle"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

Most addons can be developed entirely in LuaTC. Java is only required when extending the engine itself.

</Alert>

## Addons

TransitCore uses an addon-based architecture.

Each addon is loaded independently and communicates with the engine through LuaTC.

Typical addons include:

- Railway vehicles
- Tracks
- Signals
- Catenaries
- Stations
- User interfaces
- Sounds
- Gameplay extensions

If an addon fails to load, TransitCore automatically disables it without preventing the framework or other addons from starting.

```text title="Example addon structure"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Addon Isolation">

A faulty addon cannot crash the entire framework. TransitCore automatically reports the error, disables the addon and continues loading every remaining addon.

</Alert>

## Documentation

The documentation is organized into several sections.

| Section | Description |
|---------|-------------|
| Getting Started | Install TransitCore and create your first addon. |
| LuaTC | Learn the scripting language used by the framework. |
| Guides | Step-by-step tutorials covering every major system. |
| API Reference | Complete reference for services, classes and methods. |
| Examples | Ready-to-use sample projects demonstrating best practices. |

## Open Source

TransitCore is an open-source project developed by Fire Sparks Studio.

The documentation, issue tracker and source code are publicly available, allowing the community to contribute improvements, report issues and propose new features.

## Next Steps

If you're new to TransitCore, continue with **Installation** to set up the development environment and create your first addon.