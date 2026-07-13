---
title: Structure du projet
description: Découvrez comment est organisé un projet TransitCore et comment les différents éléments d'un Addon fonctionnent ensemble.
---

# Structure du projet

Chaque Addon TransitCore suit une structure de projet clairement définie.

Une organisation cohérente facilite la maintenance, encourage la collaboration entre développeurs et permet à TransitCore de détecter automatiquement les scripts, les ressources et les fichiers de configuration.

<Alert severity="info">

TransitCore analyse automatiquement le contenu d'un Addon et charge les ressources prises en charge en s'appuyant sur la structure de projet recommandée.

</Alert>

## Structure standard d'un projet

Un Addon TransitCore est généralement organisé de la manière suivante.

```text title="Exemple de structure d'un Addon"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── animations/
├── sounds/
├── lang/
├── ui/
└── README.md
```

Chaque dossier possède un rôle bien précis.

## Racine du projet

La racine du projet contient le manifeste de l'Addon ainsi que l'ensemble des ressources utilisées.

```text title="Racine du projet"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
└── ...
```

TransitCore identifie un Addon grâce à la présence du fichier `addon.yaml`.

Sans ce fichier, le dossier est ignoré lors du démarrage.

## Le manifeste

Le manifeste décrit les informations principales de l'Addon.

Il contient notamment :

- Le nom de l'Addon.
- Son identifiant unique.
- Sa version.
- Son auteur.
- Sa description.
- Ses dépendances.
- La version minimale de TransitCore requise.

Le manifeste se trouve toujours à la racine du projet.

```text title="Emplacement du manifeste"
MyAddon/
└── addon.yaml
```

Le fonctionnement du manifeste est détaillé dans la page **Manifeste d'Addon**.

## Scripts

Le dossier `scripts` contient tous les scripts LuaTC exécutés par TransitCore.

```text title="Dossier des scripts"
scripts/
├── main.luatc
├── vehicles/
├── signals/
├── ui/
└── utilities/
```

Les scripts permettent notamment de définir :

- Les véhicules.
- Les signaux.
- Les composants.
- Les événements.
- Les mécaniques de jeu.
- Les interfaces utilisateur.

<Alert severity="success">

Organisez vos scripts par fonctionnalité plutôt que de regrouper tout votre code dans un seul fichier.

</Alert>

## Modèles 3D

Le dossier `models` contient tous les modèles 3D utilisés par votre Addon.

Les formats pris en charge dépendent du chargeur de modèles installé.

```text title="Dossier des modèles"
models/
├── trains/
├── signals/
├── tracks/
├── stations/
└── props/
```

Les modèles sont chargés via l'API **Node** de TransitCore.

## Textures

Les textures sont stockées dans le dossier `textures`.

```text title="Dossier des textures"
textures/
├── vehicles/
├── signals/
├── tracks/
└── ui/
```

Classer les textures par catégorie facilite leur maintenance, en particulier sur les projets de grande taille.

## Animations

Le dossier `animations` regroupe toutes les animations utilisées par l'Addon.

```text title="Dossier des animations"
animations/
├── doors/
├── cab/
├── bogies/
└── pantographs/
```

Les animations peuvent ensuite être associées à des **Nodes** et contrôlées depuis LuaTC.

## Sons

Le dossier `sounds` contient toutes les ressources audio de l'Addon.

```text title="Dossier des sons"
sounds/
├── engines/
├── brakes/
├── doors/
├── announcements/
└── ambience/
```

TransitCore prend en charge les sons positionnels ainsi que plusieurs catégories audio.

## Localisation

Les fichiers de traduction sont stockés dans le dossier `lang`.

```text title="Fichiers de langue"
lang/
├── en_us.json
├── fr_fr.json
└── ja_jp.json
```

Tous les textes visibles par les joueurs devraient être localisés plutôt que directement écrits dans les scripts LuaTC.

Cela permet de proposer facilement plusieurs langues sans modifier le code de l'Addon.

## Interface utilisateur

Les ressources graphiques et les éléments de l'interface utilisateur sont regroupés dans le dossier `ui`.

```text title="Dossier de l'interface utilisateur"
ui/
├── images/
├── icons/
├── layouts/
└── themes/
```

Ce dossier contient tous les éléments nécessaires à la création des interfaces de votre Addon.

## Organisation recommandée

À mesure qu'un projet grandit, il est conseillé d'organiser les fichiers par fonctionnalité.

Par exemple :

```text title="Exemple d'un projet de grande taille"
scripts/
├── vehicles/
│   ├── metro/
│   ├── tram/
│   └── train/
├── railway/
├── signaling/
├── stations/
├── ui/
└── shared/
```

Cette organisation améliore la lisibilité du projet, facilite la maintenance et favorise la réutilisation du code.

<Alert severity="warning">

Évitez de placer tous vos scripts dans un seul dossier. Une organisation claire rend le projet plus simple à comprendre, à maintenir et à faire évoluer.

</Alert>

## Bonnes pratiques

Lors de la création d'un nouvel Addon :

- Regroupez les fichiers liés à une même fonctionnalité.
- Utilisez des noms de fichiers explicites.
- Évitez les ressources dupliquées.
- Organisez vos scripts par fonctionnalité.
- Placez le code réutilisable dans des modules partagés.
- Conservez la même structure de projet pour tous vos Addons.

Une structure cohérente facilite également la contribution d'autres développeurs à votre projet.

## Étape suivante

Maintenant que vous connaissez l'organisation générale d'un projet TransitCore, poursuivez avec **Structure des dossiers** afin de découvrir le rôle de chaque dossier et la manière dont TransitCore les utilise.