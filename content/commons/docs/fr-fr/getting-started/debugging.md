---
title: Débogage
description: Apprenez à identifier, comprendre et corriger les erreurs rencontrées lors du développement de vos Addons TransitCore.
---

# Débogage

Le débogage est une étape essentielle du développement d'un Addon.

Même les projets les plus simples peuvent rencontrer des erreurs de syntaxe, des problèmes de configuration ou des comportements inattendus. TransitCore fournit plusieurs outils permettant de les identifier rapidement.

<Alert severity="info">

Lorsqu'une erreur se produit, TransitCore tente de fournir un message aussi précis que possible afin de vous aider à identifier rapidement son origine.

</Alert>

## Les journaux

TransitCore enregistre toutes les informations importantes dans ses journaux.

Vous y trouverez notamment :

- Les Addons chargés.
- Les erreurs LuaTC.
- Les avertissements.
- Les erreurs de chargement.
- Les informations de diagnostic.

Les journaux sont disponibles dans le dossier suivant.

```text title="Dossier des journaux"

.minecraft/
└── TC_Logs/

```

Il est recommandé de consulter les journaux avant toute modification de votre code.

## Lire un message d'erreur

Lorsqu'une erreur survient, TransitCore affiche généralement un message similaire à celui-ci.

```text title="Exemple"

[LuaTC] Runtime Error
Attempt to call nil value.

```

Ce message indique :

- Le système concerné.
- Le type d'erreur.
- Une description du problème.

Dans cet exemple, une fonction inexistante a été appelée.

## Erreurs de syntaxe

Les erreurs de syntaxe empêchent un script d'être chargé.

Par exemple :

```luatc title="Incorrect"

local speed =

```

TransitCore signalera immédiatement cette erreur lors du chargement du script.

Corrigez toujours les erreurs de syntaxe avant de poursuivre vos tests.

## Erreurs d'exécution

Une erreur d'exécution se produit lorsqu'un script s'exécute, mais rencontre une situation inattendue.

Par exemple :

```luatc title="Incorrect"

local train = nil

train:setSpeed(80)

```

Comme `train` n'existe pas, LuaTC génère une erreur.

Avant d'utiliser une variable, assurez-vous toujours qu'elle contient une valeur valide.

## Utiliser print()

La fonction `print()` est l'un des outils les plus simples pour comprendre le comportement d'un script.

```luatc title="Exemple"

print("Initialisation de l'Addon...")

```

Vous pouvez également afficher la valeur d'une variable.

```luatc title="Afficher une variable"

print(speed)

```

Ces messages apparaîtront directement dans la console ainsi que dans les journaux.

## Vérifier le manifeste

Si votre Addon n'est pas chargé, vérifiez en priorité le fichier `addon.yaml`.

Les erreurs les plus fréquentes sont :

- un identifiant manquant ;
- une propriété obligatoire absente ;
- une erreur de syntaxe YAML ;
- une version incompatible de TransitCore.

```text title="Exemple"

[TransitCore] Invalid addon manifest.
Missing required property: id

```

## Vérifier les dépendances

Si votre Addon dépend d'un autre Addon, assurez-vous que celui-ci est bien installé.

Par exemple :

```yaml title="addon.yaml"

dependencies:
  - common_assets

```

Si une dépendance est absente, TransitCore désactivera automatiquement l'Addon concerné.

## Déboguer progressivement

Lorsque vous développez une nouvelle fonctionnalité :

1. Ajoutez une petite modification.
2. Lancez Minecraft.
3. Vérifiez les journaux.
4. Testez le comportement.
5. Corrigez les éventuelles erreurs.

Cette méthode est beaucoup plus efficace que d'ajouter plusieurs centaines de lignes de code avant d'effectuer un premier test.

<Alert severity="success">

Développez progressivement. Tester régulièrement permet de localiser les erreurs beaucoup plus facilement.

</Alert>

## Erreurs courantes

| Problème | Cause possible |
|----------|----------------|
| L'Addon ne se charge pas | Le fichier `addon.yaml` est absent ou invalide. |
| Aucun script ne s'exécute | Le fichier `main.luatc` est manquant ou contient une erreur. |
| Une ressource est introuvable | Le chemin du fichier est incorrect. |
| Une fonction provoque une erreur | Une variable est `nil` ou un paramètre est invalide. |
| Un Addon est désactivé | Une dépendance est absente ou la version de TransitCore est incompatible. |

## Bonnes pratiques

Pour faciliter le débogage :

- Consultez les journaux après chaque lancement.
- Testez une seule fonctionnalité à la fois.
- Utilisez `print()` pour suivre l'exécution de vos scripts.
- Corrigez les erreurs dès leur apparition.
- Organisez votre code en petits modules faciles à maintenir.

<Alert severity="warning">

Évitez de masquer les erreurs ou de les ignorer. Même si votre Addon semble fonctionner, une erreur non corrigée peut provoquer des comportements inattendus ou rendre le diagnostic plus difficile par la suite.

</Alert>

## Besoin d'aide ?

Si vous ne parvenez pas à résoudre un problème :

- Consultez les journaux de TransitCore.
- Vérifiez la documentation de l'API.
- Comparez votre code avec les exemples fournis.
- Reproduisez le problème dans un projet minimal avant de demander de l'aide.

Fournir le message d'erreur complet ainsi que les journaux concernés permettra d'obtenir une réponse plus rapide et plus précise.

## Félicitations !

Vous avez terminé la section **Bien démarrer**.

Vous connaissez désormais les bases de TransitCore, savez créer un Addon, organiser votre projet, écrire des scripts LuaTC, exécuter votre Addon et diagnostiquer les erreurs les plus courantes.

Vous êtes maintenant prêt à explorer le reste de la documentation, notamment les **Guides**, **LuaTC** et la **Référence API**, afin de développer des Addons plus complets.