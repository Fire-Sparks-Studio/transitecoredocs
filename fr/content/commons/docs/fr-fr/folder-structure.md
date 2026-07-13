---
title: Structure des dossiers
description: Découvrez comment TransitCore organise les fichiers d'un Addon et le rôle de chaque dossier.
---

# Structure des dossiers

Chaque Addon TransitCore suit une organisation de fichiers standardisée.

Adopter cette structure facilite la maintenance du projet, améliore sa lisibilité et permet à TransitCore de détecter automatiquement les ressources sans configuration supplémentaire.

<Alert severity="info">

TransitCore analyse automatiquement les dossiers connus d'un Addon. En respectant la structure recommandée, toutes les ressources sont détectées et chargées de manière cohérente.

</Alert>

## Structure standard

Un Addon est généralement organisé de la manière suivante.

```text title="Addon structure"
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

Chaque dossier possède un rôle bien défini.

## Racine du projet

La racine contient le manifeste de l'Addon ainsi que l'ensemble des ressources utilisées par celui-ci.

```text title="Project root"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
└── ...
```

TransitCore identifie un Addon grâce au fichier `addon.yaml`.

Sans ce fichier, le dossier est ignoré lors du démarrage.

## scripts/

Le dossier `scripts` contient tous les scripts LuaTC exécutés par l'Addon.

```text title="Scripts folder"
scripts/
├── main.luatc
├── vehicles/
├── signals/
├── stations/
├── ui/
└── shared/
```

On y retrouve généralement :

- Les définitions des véhicules.
- La logique des signaux.
- Les systèmes ferroviaires.
- Les mécaniques de gameplay.
- Les modules utilitaires.
- Les bibliothèques partagées.

Le fichier `main.luatc` est généralement utilisé comme point d'entrée de l'Addon.

## models/

Le dossier `models` contient tous les modèles 3D utilisés par l'Addon.

```text title="Models folder"
models/
├── vehicles/
├── signals/
├── tracks/
├── stations/
└── props/
```

Les formats pris en charge dépendent du chargeur de modèles installé.

Les modèles sont ensuite chargés via le système **Node** et peuvent être manipulés depuis LuaTC.

## textures/

Toutes les textures sont regroupées dans le dossier `textures`.

```text title="Textures folder"
textures/
├── vehicles/
├── signals/
├── tracks/
├── ui/
└── misc/
```

Organiser les textures par catégorie simplifie leur maintenance, en particulier lorsque le projet prend de l'ampleur.

## animations/

Le dossier `animations` contient toutes les animations utilisées par les modèles.

```text title="Animations folder"
animations/
├── doors/
├── cab/
├── pantographs/
├── bogies/
└── indicators/
```

Les animations sont associées à des **Nodes** et contrôlées depuis LuaTC.

Les éléments animés les plus courants sont :

- Les portes.
- Les boutons.
- Les interrupteurs.
- Les pantographes.
- Les essuie-glaces.
- Les commandes du poste de conduite.

## sounds/

Le dossier `sounds` contient toutes les ressources audio de l'Addon.

```text title="Sounds folder"
sounds/
├── engines/
├── brakes/
├── doors/
├── announcements/
├── ambience/
└── ui/
```

TransitCore détecte automatiquement les fichiers audio compatibles et les rend accessibles via le service audio.

## lang/

Le dossier `lang` contient les fichiers de traduction.

```text title="Language files"
lang/
├── en_us.json
├── fr_fr.json
├── de_de.json
└── ja_jp.json
```

Tous les textes affichés au joueur devraient être localisés plutôt que directement écrits dans les scripts LuaTC.

Cela permet de proposer plusieurs langues sans modifier le code de l'Addon.

## ui/

Le dossier `ui` regroupe toutes les ressources liées à l'interface utilisateur.

```text title="User interface folder"
ui/
├── icons/
├── images/
├── layouts/
└── themes/
```

On peut notamment y retrouver :

- Les icônes.
- Les menus.
- Les panneaux de configuration.
- Les tableaux de bord.
- Les textures d'interface.

## README.md

Bien qu'il soit facultatif, il est fortement recommandé d'ajouter un fichier `README.md` à votre Addon.

```text title="Documentation"
README.md
```

Ce fichier peut contenir :

- Une présentation de l'Addon.
- Les instructions d'installation.
- Les informations de compatibilité.
- Les limitations connues.
- La licence.
- Les crédits.

Un README bien rédigé facilite la compréhension du projet et encourage les contributions de la communauté.

## Organisation recommandée

Lorsque votre Addon devient plus important, il est conseillé d'organiser les fichiers par fonctionnalité.

```text title="Example of a large Addon"
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

Cette organisation améliore la lisibilité du code, facilite sa maintenance et encourage sa réutilisation.

<Alert severity="success">

Organisez vos fichiers par fonctionnalité plutôt que de tout regrouper dans un seul dossier. Une structure cohérente rend les Addons plus simples à maintenir et à faire évoluer.

</Alert>

## Dossiers gérés par TransitCore

TransitCore crée automatiquement plusieurs dossiers dans votre répertoire Minecraft.

Par exemple :

```text title="TransitCore folders"
.minecraft/
├── TC_Cache/
├── TC_Logs/
└── TC_Config/
```

Ces dossiers sont gérés automatiquement par le framework.

Il est généralement déconseillé de les modifier manuellement, sauf indication contraire dans la documentation.

## Bonnes pratiques

Pour organiser efficacement un Addon :

- Regroupez les fichiers liés à une même fonctionnalité.
- Utilisez des noms de fichiers explicites.
- Placez le code réutilisable dans des modules partagés.
- Évitez les ressources dupliquées.
- Adoptez une convention de nommage cohérente.
- Utilisez la même structure pour tous vos Addons.

Une organisation prévisible facilite le développement, la maintenance et la collaboration.

## Étape suivante

Maintenant que vous connaissez le rôle de chaque dossier, poursuivez avec **Votre premier Addon** afin de créer votre premier projet TransitCore.