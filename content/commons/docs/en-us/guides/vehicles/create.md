---
title: Creating a Vehicle
description: Learn how to create and configure your first TransitCore Vehicle.
---

# Creating a Vehicle

This guide explains how to create your first Vehicle in TransitCore.

A Vehicle represents **one rolling stock unit**, such as a locomotive, passenger coach, freight wagon, tram, metro car or maintenance vehicle.

At the end of this guide, you will have:

- Created your first Vehicle.
- Registered functional Nodes.
- Attached Nodes to your 3D model.
- Understood the architecture of TransitCore Vehicles.

<Alert severity="info">

A Vehicle represents **a single rolling stock unit**. Complete trains are created by coupling multiple Vehicles together.

</Alert>

## What is a Vehicle?

In TransitCore, a Vehicle is the base object representing one piece of rolling stock.

Examples include:

- Locomotive
- Passenger coach
- Freight wagon
- Metro car
- Tram
- Funicular vehicle
- Maintenance vehicle

TransitCore does **not** provide a `Train` object.

Instead, players create trains by coupling compatible Vehicles together.

```text title="Train composition"
Vehicle
⇄
Vehicle
⇄
Vehicle
```

This allows complete freedom when creating train formations.

## Creating a Vehicle

Vehicles are created using the `VehicleService`.

```luatc title="Creating a Vehicle"
local vehicle = VehicleService:create({

    name = "TGV Duplex",

    description = "French high-speed train built by Alstom.",

    manufacturer = "Alstom",

    type = VehicleType.Train,

    mass = 383000,

    maxSpeed = 320,

    brakeForce = 320,

    tractionForce = 280,

    powerRequired = 25000

})
```

<Alert severity="info">

Vehicle dimensions such as length, width and height are automatically retrieved from the imported 3D model.

</Alert>

## Vehicle properties

The Vehicle configuration currently supports the following properties.

| Property | Description |
|----------|-------------|
| `name` | Display name of the Vehicle. |
| `description` | Short description shown in the Train Spawner. |
| `manufacturer` | Vehicle manufacturer. |
| `type` | Vehicle category. |
| `mass` | Vehicle mass in kilograms. |
| `maxSpeed` | Maximum operating speed. |
| `brakeForce` | Braking force. |
| `tractionForce` | Available traction force. |
| `powerRequired` | Required supply voltage or power level. |

## Nodes

Vehicles are built using Nodes.

A Node represents a functional part of a Vehicle.

Examples include:

- Doors
- Bogies
- Couplers
- Pantographs
- Lights
- Buttons
- Screens

Each Node is created individually before being attached to the Vehicle.

## Creating a Node

```luatc title="Creating a Door Node"
local door = NodeService:create(NodeType.Door)
```

## Attaching a Node

Nodes are attached to an Anchor defined inside the 3D model.

```luatc title="Attach a Door"
door:attachTo("Door_Left_01")
```

The Anchor name corresponds to a Blender Empty.

TransitCore automatically retrieves:

- Position
- Rotation
- Orientation

No coordinates need to be written in LuaTC.

## Registering the Node

Once configured, simply register the Node inside the Vehicle.

```luatc title="Register the Door"
vehicle:addNode(door)
```

TransitCore automatically:

- Validates the Node.
- Finds the corresponding Anchor.
- Registers the Node.
- Links it to the Vehicle.
- Initializes it.

## Available Node Types

TransitCore currently provides the following Node types.

| Node Type | Description |
|-----------|-------------|
| Door | Passenger or service doors. |
| Button | Interactive buttons. |
| Lever | Control levers. |
| Switch | Vehicle switches. |
| Bogie | Vehicle bogies. |
| Coupler | Vehicle couplers. |
| Pantograph | Overhead power collection. |
| ThirdRail | Third rail power collection. |
| RackRail | Rack railway mechanism. |
| Light | Lighting elements. |
| Screen | Information displays. |
| Seat | Passenger or driver seats. |
| Fan | Cooling fans. |
| Gauge | Analog gauges. |
| Part | Generic custom object. |

<Alert severity="info">

`NodeType.Part` can be used for custom decorative or mechanical elements that do not require a dedicated Node type.

</Alert>

## Animations

Animations are created inside your 3D software.

TransitCore plays them using the AnimationService.

During playback, TransitCore automatically updates:

- Collision
- Synchronization
- Transformations

The animation is always the source of truth.

## Sounds

Sounds are managed using the SoundService.

```luatc title="Playing a Sound"
local doorOpen = SoundService:getSound("sounds/doors/open.wav")

doorOpen:play(door)
```

The Node automatically becomes the sound emitter.

## What's next?

Your first Vehicle is now created.

Continue with **Vehicle Nodes** to learn how each Node type works and how to implement custom behaviors.