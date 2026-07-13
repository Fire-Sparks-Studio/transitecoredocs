---
title: Vue d'ensemble
description: Découvrez ce qu'est TransitCore, son fonctionnement et les principes qui ont guidé sa conception.
---

# Vue d'ensemble

Bienvenue dans **TransitCore**.

TransitCore est un framework de simulation ferroviaire modulaire pour Minecraft, conçu pour créer des réseaux ferroviaires réalistes grâce à un puissant système d'Addons et au langage de script **LuaTC**.

Contrairement aux mods ferroviaires traditionnels, TransitCore ne fournit pas directement de véhicules ou d'infrastructures. Le framework met à disposition le moteur de simulation, tandis que les trains, métros, tramways, voies, signaux et autres contenus sont distribués sous forme d'Addons indépendants.

<Alert severity="info">

TransitCore sépare complètement le **moteur** du **contenu**. Le framework fournit les différents systèmes de simulation, tandis que les Addons apportent les véhicules, les voies, les signaux, les gares et tous les autres éléments ferroviaires.

</Alert>

## Pourquoi TransitCore ?

TransitCore a été développé autour de quatre principes fondamentaux.

### Réalisme

L'objectif de TransitCore est de reproduire le fonctionnement d'un réseau ferroviaire de la manière la plus fidèle possible, tout en restant parfaitement intégré à Minecraft.

Le framework prend notamment en charge :

- Une simulation avancée des véhicules.
- Des systèmes de freinage réalistes.
- La signalisation ferroviaire.
- Les systèmes électriques.
- La gestion des voyageurs.
- La synchronisation multijoueur.
- Les lignes ferroviaires à grande vitesse.

### Modularité

Tout dans TransitCore est conçu de manière modulaire.

Le framework lui-même contient uniquement les moteurs nécessaires à son fonctionnement.

Les véhicules, infrastructures, sons, textures, interfaces utilisateur et extensions de gameplay sont distribués sous forme d'Addons pouvant être installés, mis à jour ou supprimés indépendamment les uns des autres.

### Performances

TransitCore est conçu pour gérer efficacement des réseaux ferroviaires de grande taille.

Le rendu graphique, la physique, le réseau et la simulation sont optimisés afin de limiter les calculs inutiles tout en conservant un comportement réaliste.

### Extensibilité

Toutes les fonctionnalités proposées par TransitCore sont accessibles via **LuaTC**, le langage de script officiel du framework.

Les développeurs peuvent ainsi créer des Addons complets sans avoir à modifier le code Java de TransitCore.

## Architecture

TransitCore est composé de plusieurs systèmes indépendants qui fonctionnent ensemble.

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

Chaque système est responsable d'une partie précise du framework et communique avec les autres au travers d'API publiques et stables.

## LuaTC

LuaTC est le langage de script officiel de TransitCore.

Basé sur Lua, il l'étend avec des API spécialement conçues pour la simulation ferroviaire. Il permet aux développeurs d'interagir avec le framework sans avoir à accéder directement aux mécanismes internes de Minecraft.

```luatc title="Create a vehicle"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

La majorité des Addons peuvent être développés entièrement en LuaTC. Java n'est nécessaire que pour étendre le fonctionnement interne de TransitCore.

</Alert>

## Les Addons

TransitCore repose sur une architecture entièrement basée sur les Addons.

Chaque Addon est chargé indépendamment et communique avec le framework au travers de LuaTC.

Un Addon peut ajouter, par exemple :

- Des trains.
- Des métros.
- Des tramways.
- Des funiculaires.
- Des voies ferrées.
- Des signaux.
- Des caténaires.
- Des gares.
- Des interfaces utilisateur.
- Des sons.
- Des extensions de gameplay.

Si un Addon rencontre une erreur lors de son chargement, TransitCore le désactive automatiquement sans empêcher le framework ou les autres Addons de démarrer.

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

Un Addon défectueux ne peut pas empêcher TransitCore de démarrer. Le framework détecte automatiquement l'erreur, désactive uniquement l'Addon concerné et poursuit le chargement de tous les autres.

</Alert>

## La documentation

La documentation est organisée en plusieurs sections.

| Section       | Description                                                                                            |
| ------------- | ------------------------------------------------------------------------------------------------------ |
| Bien démarrer | Installer TransitCore et créer votre premier Addon.                                    |
| LuaTC         | Découvrir le langage de script officiel du framework.                                  |
| Guides        | Tutoriels détaillés couvrant les principaux systèmes de TransitCore.                   |
| Référence API | Documentation complète des services, classes, méthodes et événements.                  |
| Exemples      | Projets d'exemple illustrant les bonnes pratiques et les fonctionnalités du framework. |

## Open Source

TransitCore est un projet open source développé par **Fire Sparks Studio**.

Le code source, la documentation ainsi que le système de suivi des problèmes sont accessibles publiquement afin de permettre à la communauté de proposer des améliorations, signaler des anomalies et contribuer au développement du framework.

## Étape suivante

Si vous découvrez TransitCore, poursuivez avec **Installation** afin de préparer votre environnement de développement et créer votre premier Addon.