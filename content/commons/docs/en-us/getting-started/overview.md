---
title: Overview
description: Discover what TransitCore is, how it works and the principles that guided its design.
---

# Overview

Welcome to **TransitCore**.

TransitCore is a modular railway simulation framework for Minecraft, designed to create realistic railway networks through a powerful Addon system and the **LuaTC** scripting language.

Unlike traditional railway mods, TransitCore does not directly provide vehicles or infrastructure. The framework provides the simulation engine, while trains, metros, trams, tracks, signals and other content are distributed as independent Addons.

<Alert severity="info">

TransitCore completely separates the **engine** from the **content**. The framework provides the various simulation systems, while Addons bring the vehicles, tracks, signals, stations and all other railway elements.

</Alert>

## Why TransitCore?

TransitCore was developed around four fundamental principles.

### Realism

The goal of TransitCore is to reproduce the operation of a railway network as faithfully as possible, while remaining perfectly integrated into Minecraft.

The framework notably supports:

- Advanced vehicle simulation.
- Realistic braking systems.
- Railway signaling.
- Electrical systems.
- Passenger management.
- Multiplayer synchronization.
- High-speed railway lines.

### Modularity

Everything in TransitCore is designed in a modular way.

The framework itself contains only the engines necessary for its operation.

Vehicles, infrastructure, sounds, textures, user interfaces and gameplay extensions are distributed as Addons that can be installed, updated or removed independently of each other.

### Performance

TransitCore is designed to efficiently handle large railway networks.

Rendering, physics, networking and simulation are optimized to limit unnecessary computations while maintaining realistic behavior.

### Extensibility

All the features offered by TransitCore are accessible via **LuaTC**, the official scripting language of the framework.

Developers can thus create complete Addons without having to modify the Java code of TransitCore.

## Architecture

TransitCore is composed of several independent systems that work together.

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

Each system is responsible for a specific part of the framework and communicates with the others through stable public APIs.

## LuaTC

LuaTC is the official scripting language of TransitCore.

Based on Lua, it extends it with APIs specifically designed for railway simulation. It allows developers to interact with the framework without having to directly access Minecraft's internal mechanisms.

```luatc title="Create a vehicle"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

The majority of Addons can be developed entirely in LuaTC. Java is only necessary to extend the internal operation of TransitCore.

</Alert>

## Addons

TransitCore relies on a fully Addon-based architecture.

Each Addon is loaded independently and communicates with the framework through LuaTC.

An Addon can add, for example:

- Trains.
- Metros.
- Trams.
- Funiculars.
- Railway tracks.
- Signals.
- Catenaries.
- Stations.
- User interfaces.
- Sounds.
- Gameplay extensions.

If an Addon encounters an error during loading, TransitCore automatically disables it without preventing the framework or other Addons from starting.

```text title="Example Addon structure"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Addon Isolation">

A faulty Addon cannot prevent TransitCore from starting. The framework automatically detects the error, disables only the Addon concerned and continues loading all the others.

</Alert>

## The documentation

The documentation is organized into several sections.

| Section | Description |
|---------|-------------|
| Getting started | Install TransitCore and create your first Addon. |
| LuaTC | Discover the official scripting language of the framework. |
| Guides | Detailed tutorials covering the main systems of TransitCore. |
| API Reference | Complete documentation of services, classes, methods and events. |
| Examples | Example projects illustrating best practices and framework features. |

## Open Source

TransitCore is an open source project developed by **Fire Sparks Studio**.

The source code, documentation and issue tracking system are publicly accessible to allow the community to propose improvements, report anomalies and contribute to the development of the framework.

## Next step

If you are discovering TransitCore, continue with **Installation** to prepare your development environment and create your first Addon.