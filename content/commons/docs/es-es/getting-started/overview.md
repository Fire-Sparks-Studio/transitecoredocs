---
title: Descripción general
description: Descubra qué es TransitCore, cómo funciona y los principios que guiaron su diseño.
---

# Descripción general

Bienvenido a **TransitCore**.

TransitCore es un framework modular de simulación ferroviaria para Minecraft, diseñado para crear redes ferroviarias realistas mediante un potente sistema de Addons y el lenguaje de script **LuaTC**.

A diferencia de los mods ferroviarios tradicionales, TransitCore no proporciona directamente vehículos ni infraestructuras. El framework pone a disposición el motor de simulación, mientras que los trenes, metros, tranvías, vías, señales y otros contenidos se distribuyen como Addons independientes.

<Alert severity="info">

TransitCore separa completamente el **motor** del **contenido**. El framework proporciona los diferentes sistemas de simulación, mientras que los Addons aportan los vehículos, las vías, las señales, las estaciones y todos los demás elementos ferroviarios.

</Alert>

## ¿Por qué TransitCore?

TransitCore se ha desarrollado en torno a cuatro principios fundamentales.

### Realismo

El objetivo de TransitCore es reproducir el funcionamiento de una red ferroviaria de la manera más fiel posible, manteniéndose perfectamente integrado en Minecraft.

El framework admite, entre otros:

- Una simulación avanzada de los vehículos.
- Sistemas de frenado realistas.
- La señalización ferroviaria.
- Los sistemas eléctricos.
- La gestión de viajeros.
- La sincronización multijugador.
- Las líneas ferroviarias de alta velocidad.

### Modularidad

Todo en TransitCore está diseñado de forma modular.

El propio framework contiene únicamente los motores necesarios para su funcionamiento.

Los vehículos, infraestructuras, sonidos, texturas, interfaces de usuario y extensiones de jugabilidad se distribuyen como Addons que pueden instalarse, actualizarse o eliminarse independientemente unos de otros.

### Rendimiento

TransitCore está diseñado para gestionar de forma eficiente redes ferroviarias de gran tamaño.

El renderizado gráfico, la física, la red y la simulación están optimizados para limitar los cálculos innecesarios manteniendo un comportamiento realista.

### Extensibilidad

Todas las funcionalidades que ofrece TransitCore son accesibles a través de **LuaTC**, el lenguaje de script oficial del framework.

Los desarrolladores pueden así crear Addons completos sin tener que modificar el código Java de TransitCore.

## Arquitectura

TransitCore está compuesto por varios sistemas independientes que funcionan conjuntamente.

```text title="Arquitectura de TransitCore"
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

Cada sistema es responsable de una parte precisa del framework y se comunica con los demás a través de APIs públicas y estables.

## LuaTC

LuaTC es el lenguaje de script oficial de TransitCore.

Basado en Lua, lo extiende con APIs diseñadas específicamente para la simulación ferroviaria. Permite a los desarrolladores interactuar con el framework sin tener que acceder directamente a los mecanismos internos de Minecraft.

```luatc title="Crear un vehículo"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

La mayoría de los Addons pueden desarrollarse íntegramente en LuaTC. Java solo es necesario para extender el funcionamiento interno de TransitCore.

</Alert>

## Los Addons

TransitCore se basa en una arquitectura totalmente basada en Addons.

Cada Addon se carga de forma independiente y se comunica con el framework a través de LuaTC.

Un Addon puede añadir, por ejemplo:

- Trenes.
- Metros.
- Tranvías.
- Funiculares.
- Vías ferroviarias.
- Señales.
- Catenarias.
- Estaciones.
- Interfaces de usuario.
- Sonidos.
- Extensiones de jugabilidad.

Si un Addon encuentra un error durante su carga, TransitCore lo desactiva automáticamente sin impedir que el framework o los demás Addons se inicien.

```text title="Ejemplo de estructura de un Addon"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Aislamiento de los Addons">

Un Addon defectuoso no puede impedir que TransitCore se inicie. El framework detecta automáticamente el error, desactiva únicamente el Addon afectado y prosigue la carga de todos los demás.

</Alert>

## La documentación

La documentación está organizada en varias secciones.

| Sección | Descripción |
|---------|-------------|
| Primeros pasos | Instalar TransitCore y crear su primer Addon. |
| LuaTC | Descubrir el lenguaje de script oficial del framework. |
| Guías | Tutoriales detallados que cubren los principales sistemas de TransitCore. |
| Referencia API | Documentación completa de los servicios, clases, métodos y eventos. |
| Ejemplos | Proyectos de ejemplo que ilustran las buenas prácticas y las funcionalidades del framework. |

## Open Source

TransitCore es un proyecto de código abierto desarrollado por **Fire Sparks Studio**.

El código fuente, la documentación y el sistema de seguimiento de problemas son accesibles públicamente para permitir a la comunidad proponer mejoras, notificar anomalías y contribuir al desarrollo del framework.

## Siguiente paso

Si está descubriendo TransitCore, continúe con **Instalación** para preparar su entorno de desarrollo y crear su primer Addon.