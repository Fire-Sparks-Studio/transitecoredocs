---
title: Manifeste d'Addon
description: Découvrez le fichier addon.yaml et apprenez à configurer correctement votre Addon TransitCore.
---

# Manifeste d'Addon

Chaque Addon TransitCore doit obligatoirement contenir un fichier `addon.yaml`.

Ce fichier constitue le manifeste de votre Addon. Il permet à TransitCore de l'identifier, de vérifier sa compatibilité et de charger correctement ses ressources lors du démarrage.

<Alert severity="warning">

Le fichier `addon.yaml` est obligatoire. Sans lui, TransitCore ne détectera pas votre Addon.

</Alert>

## Emplacement

Le manifeste doit toujours être placé à la racine de votre projet.

```text title="Structure du projet"

MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
└── ...

```

TransitCore recherche automatiquement ce fichier lors du chargement des Addons.

## Exemple minimal

Le manifeste le plus simple ressemble à ceci.

```yaml title="addon.yaml"

id: my_first_addon
name: My First Addon
version: 1.0.0
author: VotreNom
description: Mon premier Addon TransitCore.

```

Ce fichier contient les informations essentielles nécessaires au chargement de votre Addon.

## Structure générale

Voici un exemple plus complet.

```yaml title="addon.yaml"

id: metro_pack
name: Metro Pack
version: 1.2.0

author: Fire Sparks Studio
description: Ajoute plusieurs métros réalistes.

website: https://example.com
license: MIT

transitcore:
  minimum: 1.0.0

dependencies:
  - common_assets
  - railway_signals

```

Toutes les propriétés ne sont pas obligatoires.

## Propriétés principales

| Propriété | Obligatoire | Description |
|-----------|-------------|-------------|
| `id` | Oui | Identifiant unique de l'Addon. |
| `name` | Oui | Nom affiché de l'Addon. |
| `version` | Oui | Version actuelle de l'Addon. |
| `author` | Oui | Auteur principal. |
| `description` | Oui | Courte description de l'Addon. |
| `website` | Non | Site web officiel. |
| `license` | Non | Licence du projet. |
| `dependencies` | Non | Liste des dépendances. |

## L'identifiant

L'identifiant (`id`) est utilisé en interne par TransitCore.

Il doit être unique.

```yaml title="Exemple"

id: metro_pack

```

Il est recommandé :

- d'utiliser uniquement des lettres minuscules ;
- de séparer les mots avec des underscores (`_`) ;
- d'éviter les espaces et les caractères spéciaux.

Exemples :

```yaml title="Exemples valides"

id: metro_pack
id: french_trains
id: lyon_network

```

## Le nom

Le nom est affiché aux joueurs ainsi que dans les journaux.

```yaml title="Exemple"

name: Metro Pack

```

Contrairement à l'identifiant, le nom peut contenir des espaces, des majuscules et des caractères spéciaux.

## La version

Chaque Addon possède une version.

```yaml title="Exemple"

version: 1.0.0

```

Il est recommandé d'utiliser le format **SemVer** :

```
MAJEURE.MINEURE.CORRECTIF
```

Par exemple :

- `1.0.0`
- `1.2.4`
- `2.0.0`

## L'auteur

Cette propriété indique le créateur principal de l'Addon.

```yaml title="Exemple"

author: Fire Sparks Studio

```

Si plusieurs personnes travaillent sur le projet, vous pouvez indiquer l'organisation responsable.

## La description

La description présente brièvement votre Addon.

```yaml title="Exemple"

description: Ajoute plusieurs métros français réalistes.

```

Essayez de rester concis tout en expliquant clairement le contenu de votre Addon.

## Le site web

Vous pouvez renseigner un site web officiel.

```yaml title="Exemple"

website: https://example.com

```

Cette propriété est facultative.

## La licence

La licence indique les conditions d'utilisation de votre Addon.

```yaml title="Exemple"

license: MIT

```

Parmi les licences les plus courantes :

- MIT
- LGPL-3.0
- GPL-3.0
- Apache-2.0

## Compatibilité TransitCore

Vous pouvez préciser la version minimale de TransitCore requise.

```yaml title="Exemple"

transitcore:
  minimum: 1.0.0

```

TransitCore refusera de charger un Addon incompatible avec la version installée.

## Dépendances

Un Addon peut dépendre d'autres Addons.

```yaml title="Exemple"

dependencies:
  - common_assets
  - french_signals

```

Avant de charger votre Addon, TransitCore vérifie automatiquement que toutes les dépendances sont disponibles.

<Alert severity="info">

Si une dépendance est absente, l'Addon concerné ne sera pas chargé afin d'éviter tout comportement inattendu.

</Alert>

## Validation

Au démarrage, TransitCore vérifie automatiquement :

- la présence du manifeste ;
- les propriétés obligatoires ;
- la syntaxe du fichier ;
- la compatibilité de la version ;
- les dépendances déclarées.

En cas d'erreur, un message détaillé est enregistré dans les journaux.

```text title="Exemple"

[TransitCore] Invalid addon manifest.
Missing required property: id

```

## Bonnes pratiques

Pour garantir la compatibilité de votre Addon :

- choisissez un identifiant unique ;
- utilisez le versionnage sémantique (SemVer) ;
- rédigez une description claire ;
- déclarez toutes les dépendances nécessaires ;
- mettez à jour la version à chaque nouvelle publication.

<Alert severity="success">

Le manifeste est la première chose que TransitCore lit lorsqu'il charge un Addon. Prenez le temps de le maintenir à jour, car il contient toutes les informations essentielles concernant votre projet.

</Alert>

## Étape suivante

Votre manifeste est maintenant correctement configuré.

Vous pouvez poursuivre avec **Les bases de LuaTC** afin de découvrir le langage de script utilisé pour développer des Addons TransitCore.