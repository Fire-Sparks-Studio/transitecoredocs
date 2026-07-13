---
title: Overzicht
description: Ontdek wat TransitCore is, hoe het werkt en de principes die het ontwerp hebben geleid.
---

# Overzicht

Welkom bij **TransitCore**.

TransitCore is een modulair spoorwegsimulatieframework voor Minecraft, ontworpen om realistische spoorwegnetwerken te creëren via een krachtig Addon-systeem en de scripttaal **LuaTC**.

In tegenstelling tot traditionele spoorwegmods levert TransitCore niet direct voertuigen of infrastructuur. Het framework biedt de simulatie-engine, terwijl treinen, metro's, trams, sporen, signalen en andere inhoud worden verspreid als onafhankelijke Addons.

<Alert severity="info">

TransitCore scheidt de **engine** volledig van de **inhoud**. Het framework levert de verschillende simulatiesystemen, terwijl Addons de voertuigen, sporen, signalen, stations en alle andere spoorwegelementen aandragen.

</Alert>

## Waarom TransitCore?

TransitCore is ontwikkeld rond vier fundamentele principes.

### Realisme

Het doel van TransitCore is de werking van een spoorwegnet zo getrouw mogelijk te reproduceren, terwijl het perfect geïntegreerd blijft in Minecraft.

Het framework ondersteunt onder andere:

- Geavanceerde voertuigsimulatie.
- Realistische remsystemen.
- Spoorwegseinen.
- Elektrische systemen.
- Reizigersbeheer.
- Multiplayer-synchronisatie.
- Hogesnelheidsspoorlijnen.

### Modulariteit

Alles in TransitCore is modulair opgebouwd.

Het framework zelf bevat uitsluitend de engines die nodig zijn voor werking.

Voertuigen, infrastructuur, geluiden, texturen, gebruikersinterfaces en gameplay-uitbreidingen worden verspreid als Addons die onafhankelijk van elkaar kunnen worden geïnstalleerd, bijgewerkt of verwijderd.

### Prestaties

TransitCore is ontworpen om grote spoorwegnetwerken efficiënt te verwerken.

Rendering, fysica, netwerk en simulatie zijn geoptimaliseerd om onnodige berekeningen te beperken met behoud van realistisch gedrag.

### Uitbreidbaarheid

Alle functies die TransitCore biedt, zijn toegankelijk via **LuaTC**, de officiële scripttaal van het framework.

Ontwikkelaars kunnen zo complete Addons maken zonder de Java-code van TransitCore te hoeven aanpassen.

## Architectuur

TransitCore bestaat uit meerdere onafhankelijke systemen die samenwerken.

```text title="TransitCore-architectuur"
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

Elk systeem is verantwoordelijk voor een specifiek deel van het framework en communiceert met de andere via stabiele, openbare API's.

## LuaTC

LuaTC is de officiële scripttaal van TransitCore.

Gebaseerd op Lua, wordt het uitgebreid met API's die speciaal voor spoorwegsimulatie zijn ontworpen. Het stelt ontwikkelaars in staat om met het framework te werken zonder direct toegang te hoeven krijgen tot de interne mechanismen van Minecraft.

```luatc title="Een voertuig maken"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

Het merendeel van de Addons kan volledig in LuaTC worden ontwikkeld. Java is alleen nodig om de interne werking van TransitCore uit te breiden.

</Alert>

## De Addons

TransitCore leunt op een volledig op Addons gebaseerde architectuur.

Elke Addon wordt onafhankelijk geladen en communiceert met het framework via LuaTC.

Een Addon kan bijvoorbeeld toevoegen:

- Treinen.
- Metro's.
- Trams.
- Kabelspoorwegen.
- Spoorwegen.
- Seinen.
- Bovenleidingen.
- Stations.
- Gebruikersinterfaces.
- Geluiden.
- Gameplay-uitbreidingen.

Als een Addon een fout tegenkomt tijdens het laden, schakelt TransitCore deze automatisch uit zonder te verhinderen dat het framework of de andere Addons opstarten.

```text title="Voorbeeld van een Addon-structuur"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Addon-isolatie">

Een defecte Addon kan niet verhinderen dat TransitCore opstart. Het framework detecteert automatisch de fout, schakelt uitsluitend de betreffende Addon uit en gaat door met het laden van alle andere.

</Alert>

## De documentatie

De documentatie is ingedeeld in meerdere secties.

| Sectie | Beschrijving |
|---------|-------------|
| Aan de slag | TransitCore installeren en je eerste Addon maken. |
| LuaTC | De officiële scripttaal van het framework ontdekken. |
| Gidsen | Gedetailleerde tutorials over de belangrijkste systemen van TransitCore. |
| API-referentie | Volledige documentatie van services, klassen, methoden en events. |
| Voorbeelden | Voorbeeldprojecten die best practices en frameworkfuncties illustreren. |

## Open Source

TransitCore is een open-sourceproject ontwikkeld door **Fire Sparks Studio**.

De broncode, documentatie en het issue-trackingsysteem zijn publiek toegankelijk om de gemeenschap in staat te stellen verbeteringen voor te stellen, anomalieën te melden en bij te dragen aan de ontwikkeling van het framework.

## Volgende stap

Als je TransitCore voor het eerst ontdekt, ga verder met **Installatie** om je ontwikkelomgeving voor te bereiden en je eerste Addon te maken.