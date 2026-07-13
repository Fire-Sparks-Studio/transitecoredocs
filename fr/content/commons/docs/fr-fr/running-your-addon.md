---
title: Exécuter votre Addon
description: Découvrez comment charger, tester et mettre à jour votre Addon pendant son développement.
---

# Exécuter votre Addon

Une fois votre Addon créé, vous pouvez le lancer directement avec TransitCore afin de vérifier son fonctionnement.

TransitCore détecte automatiquement tous les Addons présents dans le dossier `TC_Addons` et les charge au démarrage du jeu.

<Alert severity="info">

À chaque lancement de Minecraft, TransitCore analyse automatiquement le dossier `TC_Addons` et charge tous les Addons dont le manifeste est valide.

</Alert>

## Vérifier la structure du projet

Avant de lancer Minecraft, assurez-vous que votre projet est correctement organisé.

```text title="Example structure"

MyAddon/
├── addon.yaml
├── scripts/
│   └── main.luatc
├── models/
├── textures/
└── sounds/

```

Le fichier `addon.yaml` ainsi que le dossier `scripts` sont indispensables au chargement de votre Addon.

## Démarrer Minecraft

Lancez Minecraft avec TransitCore installé.

Pendant le démarrage, TransitCore effectue plusieurs vérifications :

- Recherche des Addons.
- Lecture des manifestes.
- Vérification des dépendances.
- Chargement des ressources.
- Initialisation des scripts LuaTC.

Si aucune erreur n'est détectée, votre Addon est chargé automatiquement.

```text title="Console"

[TransitCore] Loading addon: MyAddon
[TransitCore] Initialising LuaTC runtime...
[TransitCore] Addon loaded successfully.

```

## Vérifier que l'Addon est chargé

Après le chargement, vous pouvez consulter la console afin de vérifier que TransitCore a bien détecté votre Addon.

Par exemple :

```text title="Console"

[TransitCore] Loading addon: Metro Pack
[TransitCore] Registering resources...
[TransitCore] Loading scripts...
[TransitCore] Ready.

```

Si votre Addon n'apparaît pas dans les journaux, vérifiez la structure de votre projet ainsi que le contenu du fichier `addon.yaml`.

## Tester vos scripts

Vous pouvez afficher des informations dans la console grâce à la fonction `print()`.

```luatc title="main.luatc"

print("TransitCore est prêt !")

```

Cette méthode est très pratique pour vérifier rapidement qu'un script est bien exécuté.

## Modifier un Addon

Pendant le développement, vous serez amené à modifier régulièrement vos scripts, modèles et ressources.

Après chaque modification :

1. Enregistrez vos fichiers.
2. Relancez Minecraft.
3. Vérifiez les journaux.
4. Testez les nouvelles fonctionnalités.

Cette méthode permet de détecter rapidement les erreurs.

## Vérifier les journaux

TransitCore enregistre toutes les informations importantes dans ses journaux.

```text title="Logs folder"

.minecraft/
└── TC_Logs/

```

Les journaux contiennent notamment :

- Les Addons chargés.
- Les erreurs LuaTC.
- Les avertissements.
- Les informations de débogage.
- Les messages du framework.

<Alert severity="success">

Consultez régulièrement les journaux pendant le développement. Ils permettent d'identifier rapidement l'origine de la plupart des problèmes.

</Alert>

## Mettre à jour un Addon

Lorsque vous modifiez votre Addon, pensez également à mettre à jour son numéro de version dans le fichier `addon.yaml`.

```yaml title="addon.yaml"

version: 1.1.0

```

Utiliser un versionnage cohérent facilite le suivi des évolutions et la publication de nouvelles versions.

## Tester progressivement

Il est recommandé d'ajouter les fonctionnalités une par une.

Après chaque modification importante :

- Lancez Minecraft.
- Vérifiez les journaux.
- Testez uniquement la fonctionnalité concernée.
- Corrigez immédiatement les éventuelles erreurs.

Cette approche rend le développement plus simple et évite d'accumuler plusieurs problèmes difficiles à identifier.

## Bonnes pratiques

Pendant le développement :

- Testez fréquemment votre Addon.
- Corrigez les erreurs dès leur apparition.
- Mettez régulièrement à jour le numéro de version.
- Consultez les journaux après chaque lancement.
- Ajoutez les nouvelles fonctionnalités progressivement.
- Conservez une structure de projet claire.

<Alert severity="warning">

Évitez de développer plusieurs fonctionnalités importantes avant de les tester. Des tests réguliers permettent d'identifier beaucoup plus facilement l'origine d'un problème.

</Alert>

## Étape suivante

Vous savez maintenant comment charger et tester un Addon avec TransitCore.

Poursuivez avec **Débogage** afin d'apprendre à analyser les erreurs, interpréter les journaux et résoudre les problèmes les plus courants.