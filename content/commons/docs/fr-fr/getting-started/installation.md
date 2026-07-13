---
title: Installation
description: Installez TransitCore et préparez votre environnement de développement.
---

# Installation

Ce guide explique comment installer TransitCore et préparer votre environnement de développement afin de créer vos propres Addons.

À la fin de cette page, vous disposerez :

- De TransitCore installé.
- D'un environnement Minecraft fonctionnel.
- Du support LuaTC.
- D'un projet prêt à accueillir votre premier Addon.

<Alert severity="info">

TransitCore est actuellement développé pour **NeoForge** et nécessite une version compatible de Minecraft. Vérifiez toujours que la version de votre jeu correspond à celle prise en charge par TransitCore.

</Alert>

## Prérequis

Avant d'installer TransitCore, assurez-vous que votre ordinateur dispose des logiciels suivants.

| Logiciel | Minimum requis | Recommandé |
|----------|----------------|------------|
| Java | Version 21 ou supérieure | Dernière version LTS |
| Minecraft | Version compatible | Dernière version prise en charge |
| NeoForge | Version compatible | Dernière version prise en charge |
| Git | Facultatif | Dernière version |
| Visual Studio Code ou IntelliJ IDEA | Facultatif | Dernière version |

## Installer TransitCore

Téléchargez la dernière version de TransitCore.

Placez ensuite le fichier du mod dans le dossier `mods` de votre installation Minecraft.

```text title="Dossier Minecraft"
.minecraft/
├── mods/
│   └── transitcore.jar
└── ...
```

Lancez Minecraft une première fois afin de permettre à TransitCore de créer automatiquement les dossiers dont il a besoin.

<Alert severity="success">

Lors du premier lancement, TransitCore génère automatiquement tous les dossiers nécessaires à son fonctionnement.

</Alert>

## Dossiers générés

Après son premier démarrage, TransitCore crée plusieurs dossiers dans votre répertoire Minecraft.

```text title="Dossiers de TransitCore"
.minecraft/
├── TC_Addons/
├── TC_Cache/
├── TC_Logs/
├── TC_Config/
└── mods/
```

| Dossier | Description |
|---------|-------------|
| `TC_Addons` | Contient tous les Addons installés. |
| `TC_Cache` | Stocke les fichiers de cache générés par le framework. |
| `TC_Logs` | Contient les journaux de TransitCore. |
| `TC_Config` | Contient les fichiers de configuration du framework. |

## Installer le support LuaTC

TransitCore propose des outils officiels pour faciliter le développement en LuaTC.

Les éditeurs actuellement pris en charge sont :

- Visual Studio Code
- IntelliJ IDEA

Les extensions officielles offrent notamment :

- La coloration syntaxique.
- L'auto-complétion.
- Les diagnostics.
- La documentation intégrée.
- La navigation dans le code.
- Le formatage automatique.

<Alert severity="info">

Les extensions LuaTC sont facultatives, mais fortement recommandées afin d'améliorer votre confort de développement.

</Alert>

## Vérifier l'installation

Lancez Minecraft.

Si TransitCore est correctement installé, vous devriez voir un message similaire au suivant dans la console.

```text title="Sortie de la console"
[TransitCore] TransitCore successfully initialized.
[TransitCore] Loading addons...
[TransitCore] Ready.
```

En cas de problème, consultez les journaux générés par TransitCore.

```text title="Dossier des journaux"
.minecraft/
└── TC_Logs/
```

## Mettre à jour TransitCore

Pour installer une nouvelle version de TransitCore :

1. Fermez Minecraft.
2. Remplacez le fichier JAR existant par la nouvelle version.
3. Relancez Minecraft.

Lorsque cela est possible, TransitCore migre automatiquement les fichiers de configuration compatibles.

<Alert severity="warning">

Avant toute mise à jour, il est fortement recommandé d'effectuer une sauvegarde de votre monde, en particulier si vous utilisez une version Alpha ou Beta.

</Alert>

## Désinstaller TransitCore

Pour supprimer complètement TransitCore :

1. Supprimez le fichier JAR de TransitCore du dossier `mods`.
2. Supprimez les Addons dont vous n'avez plus besoin dans `TC_Addons`.
3. Si vous le souhaitez, supprimez également les dossiers générés par TransitCore.

```text title="Dossiers pouvant être supprimés"
TC_Addons/
TC_Cache/
TC_Config/
TC_Logs/
```

La suppression de ces dossiers effacera définitivement les Addons installés, les fichiers de configuration ainsi que les données mises en cache.

## Étape suivante

Votre environnement de développement est maintenant prêt.

Poursuivez avec **Structure du projet** afin de découvrir comment est organisé un projet TransitCore.