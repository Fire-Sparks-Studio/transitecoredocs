---
title: Overview
description: Learn what TransitCore is, how it works, and how to build railway addons using LuaTC.
---

# Overview

Welcome to **TransitCore**, a modular railway simulation framework for Minecraft.

TransitCore provides everything required to build realistic railway systems, including trains, metros, trams, funiculars, signaling systems, catenaries, stations, animations, physics, sounds, and more.

Unlike traditional Minecraft mods, TransitCore separates the **simulation engine** from the **content**.

The framework provides the engine.

Addons provide the content.

This architecture allows developers to create completely independent addons without modifying TransitCore itself.



## Philosophy

TransitCore is built around four core principles.

### Realism

TransitCore aims to provide the most realistic railway simulation possible while remaining performant inside Minecraft.

The framework includes systems for:

- Railway physics
- Vehicle simulation
- Signaling
- Electrical systems
- Dispatching
- Animations
- Multiplayer synchronization



### Modularity

Everything is designed to be modular.

The TransitCore engine contains only the simulation framework.

Vehicles, tracks, stations, sounds, textures, signaling systems and countries are distributed as independent addons.

Developers are free to create their own content without changing the engine.



### Performance

Performance is a priority.

TransitCore is designed to efficiently simulate large railway networks while minimizing unnecessary calculations.

The engine uses optimized rendering, caching and event-driven systems whenever possible.



### Extensibility

TransitCore exposes a complete scripting API called **LuaTC**.

LuaTC allows addon developers to create new vehicles, railway systems and gameplay features without interacting directly with the Java engine.



## Architecture

TransitCore is divided into multiple independent systems.

```text
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
├── Addon Loader
└── LuaTC Runtime
```

Every system communicates through a stable public API.



## What is LuaTC?

LuaTC is TransitCore's scripting language.

It is based on Lua and extends it with TransitCore's API.

Instead of interacting with Minecraft internals, developers work exclusively with TransitCore objects.

```luatc title="Train creation"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
```

LuaTC focuses on describing behaviour while the Java engine handles rendering, networking, animations and physics.



## Addons

Everything in TransitCore is distributed as an addon.

Examples include:

- Railway vehicles
- Track systems
- Signaling systems
- Catenary systems
- Stations
- Sounds
- User interfaces
- Gameplay extensions

Each addon is isolated and loaded independently by the TransitCore Addon Loader.

A faulty addon will never prevent TransitCore or other addons from loading.



## Why TransitCore?

TransitCore has been designed to solve many limitations found in traditional railway mods.

It provides:

- A modular architecture
- A powerful addon system
- Realistic railway simulation
- Advanced signaling
- Accurate vehicle physics
- Flexible animation systems
- Multiplayer support
- Modern scripting through LuaTC
- Extensive documentation
- Long-term API stability



## Documentation

The documentation is organized into several sections.

### Getting Started

Learn how to install TransitCore, create your first addon and understand the basics of LuaTC.

### Guides

Step-by-step tutorials covering common development tasks.

### API Reference

Complete reference for every LuaTC class, service, method and event.

### Examples

Ready-to-use sample addons demonstrating best practices.



# Next Steps

If this is your first time using TransitCore, continue with **Getting Started** to learn how to create your first addon.