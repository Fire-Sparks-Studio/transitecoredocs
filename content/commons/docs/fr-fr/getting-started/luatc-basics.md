---
title: Les bases de LuaTC
description: Découvrez les bases de LuaTC et apprenez à écrire vos premiers scripts TransitCore.
---

# Les bases de LuaTC

**LuaTC** est le langage de script officiel de TransitCore.

Basé sur Lua, il a été étendu afin d'interagir avec tous les systèmes du framework, comme les véhicules, les signaux, les voies, les composants ou encore le monde.

La plupart des Addons peuvent être développés entièrement en LuaTC, sans avoir à écrire une seule ligne de Java.

<Alert severity="info">

LuaTC est spécialement conçu pour le développement d'Addons TransitCore. Il propose des API dédiées à la simulation ferroviaire tout en conservant la simplicité de Lua.

</Alert>

## Votre premier script

Le point d'entrée d'un Addon est généralement le fichier `main.luatc`.

Vous pouvez y écrire votre premier script.

```luatc title="main.luatc"
print("Hello TransitCore!")
```

Au chargement de l'Addon, ce message sera affiché dans la console.

## Variables

Les variables permettent de stocker des informations afin de les réutiliser par la suite.

```luatc title="Variables"
local trainName = "TGV Duplex"
local maxSpeed = 320
local isElectric = true
```

Le mot-clé `local` permet de créer une variable accessible uniquement dans le script courant.

Il est recommandé d'utiliser des variables locales dès que possible.

## Types de données

LuaTC reprend les principaux types de données de Lua.

| Type | Description |
|------|-------------|
| `string` | Texte. |
| `number` | Valeur numérique. |
| `boolean` | Valeur vraie ou fausse. |
| `table` | Collection de données. |
| `nil` | Valeur absente. |

Exemple :

```luatc title="Types"
local line = "Ligne A"
local speed = 80
local powered = true
```

## Fonctions

Les fonctions permettent de regrouper du code réutilisable.

```luatc title="Fonction"
local function openDoors()

    print("Ouverture des portes")

end

openDoors()
```

Les fonctions peuvent également recevoir des paramètres.

```luatc title="Paramètres"
local function setSpeed(speed)

    print(speed)

end

setSpeed(120)
```

## Conditions

Les conditions permettent d'exécuter du code uniquement lorsqu'une condition est remplie.

```luatc title="Condition"
local speed = 120

if speed > 100 then

    print("Grande vitesse")

end
```

Vous pouvez également utiliser `elseif` et `else`.

## Boucles

Les boucles permettent de répéter une action.

```luatc title="Boucle"
for i = 1, 5 do

    print(i)

end
```

Il existe également les boucles `while` et `repeat`.

## Tables

Les tables sont utilisées pour stocker plusieurs valeurs.

```luatc title="Table"
local stations = {

    "Gare Centrale",
    "Université",
    "Aéroport"

}
```

Vous pouvez accéder à une valeur grâce à son index.

```luatc title="Accès à une valeur"
print(stations[1])
```

## Commentaires

Les commentaires servent à documenter votre code.

Ils sont ignorés lors de l'exécution.

```luatc title="Commentaires"
-- Ceci est un commentaire

--[[

Ceci est
un commentaire
multiligne.

]]
```

Commentez uniquement lorsque cela apporte une réelle valeur à la compréhension du code.

## Utiliser l'API TransitCore

LuaTC permet d'interagir directement avec TransitCore.

Par exemple, pour créer un véhicule :

```luatc title="Créer un véhicule"
local vehicle = tc.vehicle.create(tc.VehicleType.TRAIN)

vehicle:setName("TGV Duplex")
vehicle:setMaximumSpeed(320)
```

Les différents services disponibles sont documentés dans la section **Référence API**.

## Organiser son code

À mesure que votre Addon évolue, évitez de tout écrire dans `main.luatc`.

Préférez répartir votre code dans plusieurs modules.

```text title="Organisation recommandée"
scripts/
├── main.luatc
├── vehicles/
├── railway/
├── stations/
├── ui/
└── shared/
```

Une organisation claire facilite la maintenance du projet et encourage la réutilisation du code.

<Alert severity="success">

Un fichier doit idéalement avoir une seule responsabilité. Préférez plusieurs petits modules plutôt qu'un unique script de plusieurs centaines de lignes.

</Alert>

## Erreurs

Une erreur dans un script peut empêcher certaines fonctionnalités de fonctionner correctement.

TransitCore affiche automatiquement les erreurs rencontrées dans les journaux.

```text title="Exemple"
[LuaTC] Runtime Error
Attempt to call nil value.
```

Consultez toujours les journaux avant de modifier votre code.

## Bonnes pratiques

Lorsque vous développez en LuaTC :

- utilisez des variables locales ;
- donnez des noms explicites à vos variables et fonctions ;
- découpez votre code en plusieurs modules ;
- évitez les duplications de code ;
- testez régulièrement votre Addon ;
- commentez uniquement lorsque cela est utile.

## Étape suivante

Vous connaissez maintenant les bases de LuaTC et pouvez commencer à développer vos propres fonctionnalités.

Poursuivez avec **Exécuter votre Addon** afin d'apprendre à lancer, tester et mettre à jour vos Addons pendant le développement.