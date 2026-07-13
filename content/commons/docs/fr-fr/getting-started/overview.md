---
title: Vue d'ensemble
description: Découvrez ce qu'est TransitCore, son fonctionnement et les principes qui ont guidé sa conception.
---

# Vue d'ensemble

Bienvenue dans **TransitCore**.

TransitCore est un framework modulaire de simulation ferroviaire pour Minecraft conçu pour permettre la création de réseaux ferroviaires réalistes grâce à un puissant système d'addons et au langage de script **LuaTC**.

Contrairement aux mods ferroviaires traditionnels, TransitCore ne fournit pas directement des trains, des métros ou des infrastructures. Le framework fournit le moteur de simulation, tandis que le contenu est distribué sous forme d'addons indépendants.

<Alert severity="info">

TransitCore sépare entièrement **le moteur** du **contenu**. Le framework fournit les systèmes de simulation, tandis que les addons ajoutent les véhicules, les voies, la signalisation, les gares, les caténaires et tout autre contenu.

</Alert>

## Pourquoi TransitCore ?

TransitCore repose sur quatre principes fondamentaux.

### Réalisme

L'objectif de TransitCore est de reproduire le fonctionnement des systèmes ferroviaires de la manière la plus fidèle possible tout en restant parfaitement intégré à Minecraft.

Le framework prend notamment en charge :

- La simulation avancée des véhicules.
- Les systèmes de freinage réalistes.
- La signalisation ferroviaire.
- Les systèmes électriques.
- L'exploitation des gares et des voyageurs.
- La synchronisation multijoueur.
- Les trains à grande vitesse.

### Modularité

Tout dans TransitCore est conçu pour être modulaire.

Le framework ne contient que le moteur de simulation.

Les véhicules, les infrastructures, les sons, les textures, les interfaces utilisateur et les extensions de gameplay sont distribués sous forme d'addons pouvant être installés, mis à jour ou supprimés indépendamment.

### Performances

TransitCore est conçu pour gérer efficacement des réseaux ferroviaires de grande taille.

Le rendu, la physique, le réseau et la simulation sont optimisés afin de limiter les calculs inutiles tout en conservant un comportement réaliste.

### Extensibilité

Toutes les fonctionnalités du framework sont accessibles via **LuaTC**, le langage officiel de TransitCore.

Les développeurs peuvent créer des addons complets sans modifier le code Java du moteur.

## Architecture

TransitCore est composé de plusieurs systèmes indépendants qui fonctionnent ensemble.

```text title="Architecture de TransitCore"
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

Chaque système est responsable d'une partie spécifique du framework et communique avec les autres grâce à une API publique stable.

## LuaTC

LuaTC est le langage de script officiel de TransitCore.

Il étend Lua avec une API spécialement conçue pour la simulation ferroviaire, permettant aux développeurs d'interagir avec le framework sans accéder directement aux systèmes internes de Minecraft.

```luatc title="Création d'un véhicule"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

La majorité des addons peuvent être développés entièrement en LuaTC. Le développement Java est uniquement nécessaire pour étendre le moteur de TransitCore.

</Alert>

## Les addons

TransitCore repose sur une architecture entièrement basée sur les addons.

Chaque addon est chargé indépendamment et communique avec le moteur grâce à LuaTC.

Les addons peuvent notamment ajouter :

- Des trains.
- Des métros.
- Des tramways.
- Des funiculaires.
- Des voies.
- Des signaux.
- Des caténaires.
- Des gares.
- Des interfaces utilisateur.
- Des sons.
- Des extensions de gameplay.

Si un addon rencontre une erreur au démarrage, TransitCore le désactive automatiquement sans empêcher le framework ou les autres addons de continuer à fonctionner.

```text title="Structure d'un addon"
MonAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Isolation des addons">

Un addon défaillant ne peut pas empêcher TransitCore de démarrer. Le framework détecte automatiquement les erreurs, désactive uniquement l'addon concerné et poursuit le chargement des autres addons.

</Alert>

## Documentation

La documentation est organisée en plusieurs sections.

| Section | Description |
|---------|-------------|
| Premiers pas | Installer TransitCore et créer son premier addon. |
| LuaTC | Découvrir le langage de script officiel du framework. |
| Guides | Tutoriels détaillés sur chaque système de TransitCore. |
| Référence API | Documentation complète des services, classes, méthodes et événements. |
| Exemples | Projets d'exemple illustrant les bonnes pratiques. |

## Projet open source

TransitCore est un projet open source développé par **Fire Sparks Studio**.

Le code source, la documentation et le suivi des problèmes sont accessibles publiquement afin de permettre à la communauté de proposer des améliorations, de signaler des anomalies et de contribuer au développement du framework.

## Étape suivante

Si vous découvrez TransitCore, poursuivez avec **Installation** afin de configurer votre environnement de développement et créer votre premier addon.