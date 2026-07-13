---
title: Votre premier Addon
description: Créez votre premier Addon TransitCore et découvrez comment il est chargé par le framework.
---

# Votre premier Addon

Il est maintenant temps de créer votre premier Addon TransitCore.

Dans ce guide, vous allez créer un Addon minimal capable d'être détecté et chargé automatiquement par TransitCore.

À la fin de cette page, vous disposerez d'une structure de projet fonctionnelle sur laquelle vous pourrez construire vos futurs développements.

<Alert severity="info">

Un Addon est une extension indépendante qui permet d'ajouter de nouvelles fonctionnalités à TransitCore, comme des véhicules, des infrastructures, des scripts ou des interfaces utilisateur.

</Alert>

## Créer le dossier de l'Addon

Commencez par ouvrir le dossier `TC_Addons` créé par TransitCore.

Créez ensuite un nouveau dossier qui contiendra votre Addon.

```text title="Initial structure"

TC_Addons/
└── MyFirstAddon/

```

Le nom du dossier est libre, mais il est recommandé d'utiliser un nom simple, sans espaces ni caractères spéciaux.

## Créer le manifeste

Chaque Addon doit obligatoirement contenir un fichier `addon.yaml`.

Ce fichier permet à TransitCore d'identifier l'Addon et de récupérer ses informations principales.

Créez le fichier suivant :

```yaml title="addon.yaml"

id: my_first_addon
name: My First Addon
version: 1.0.0
author: VotreNom
description: Mon premier Addon TransitCore.

```

<Alert severity="success">

Le fichier `addon.yaml` est obligatoire. Sans lui, TransitCore ignorera complètement votre Addon lors du démarrage.

</Alert>

## Ajouter un dossier de scripts

Créez maintenant un dossier `scripts`.

Votre projet devrait ressembler à ceci.

```text title="Current structure"

MyFirstAddon/
├── addon.yaml
└── scripts/

```

Tous les scripts LuaTC de votre Addon seront placés dans ce dossier.

## Créer le point d'entrée

Dans le dossier `scripts`, créez un fichier nommé `main.luatc`.

Ce fichier constitue le point d'entrée de votre Addon.

```text title="Structure"

MyFirstAddon/
├── addon.yaml
└── scripts/
    └── main.luatc

```

## Écrire votre premier script

Ajoutez le code suivant dans `main.luatc`.

```luatc title="main.luatc"

print("Hello TransitCore!")

```

Lorsque TransitCore chargera votre Addon, ce message sera affiché dans la console.

## Démarrer Minecraft

Lancez Minecraft avec TransitCore installé.

Pendant le démarrage, TransitCore analyse automatiquement le dossier `TC_Addons`, détecte les Addons présents et charge ceux dont le manifeste est valide.

Si tout s'est correctement déroulé, votre Addon sera chargé automatiquement.

```text title="Console"

[TransitCore] Loading addon: My First Addon
Hello TransitCore!
[TransitCore] Addon loaded successfully.

```

<Alert severity="success">

Félicitations ! Votre premier Addon est maintenant chargé par TransitCore.

</Alert>

## Ajouter de nouvelles ressources

Vous pouvez dès maintenant enrichir votre Addon en ajoutant d'autres dossiers.

Par exemple :

```text title="Complete structure"

MyFirstAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
├── animations/
├── lang/
└── ui/

```

Vous n'êtes pas obligé de créer tous ces dossiers immédiatement.

Ajoutez uniquement ceux dont votre Addon a besoin.

## Tester régulièrement

Il est recommandé de tester votre Addon après chaque modification importante.

Cette méthode permet d'identifier rapidement l'origine d'un problème et facilite le débogage.

Évitez d'ajouter un grand nombre de fonctionnalités avant de vérifier que tout fonctionne correctement.

## Bonnes pratiques

Lors de la création d'un nouvel Addon :

- Choisissez un identifiant unique.
- Utilisez une structure de projet claire.
- Testez régulièrement votre Addon.
- Organisez vos scripts par fonctionnalité.
- Ajoutez progressivement de nouvelles ressources.
- Documentez votre projet avec un fichier `README.md`.

<Alert severity="warning">

Évitez de développer l'ensemble de votre Addon dans un unique fichier `main.luatc`. Dès que votre projet grandit, répartissez votre code dans plusieurs modules afin de faciliter sa maintenance.

</Alert>

## Étape suivante

Votre premier Addon est maintenant prêt.

Vous pouvez poursuivre avec **Manifeste d'Addon** afin de découvrir toutes les propriétés disponibles dans le fichier `addon.yaml` et apprendre à configurer correctement votre projet.