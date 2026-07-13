---
title: Übersicht
description: Erfahren Sie, was TransitCore ist, wie es funktioniert und welche Prinzipien seinem Design zugrunde liegen.
---

# Übersicht

Willkommen bei **TransitCore**.

TransitCore ist ein modulares Eisenbahnsimulations-Framework für Minecraft, das darauf ausgelegt ist, realistische Schienennetze durch ein leistungsfähiges Addon-System und die Skriptsprache **LuaTC** zu erstellen.

Im Gegensatz zu herkömmlichen Eisenbahn-Mods liefert TransitCore keine Fahrzeuge oder Infrastruktur direkt mit. Das Framework stellt die Simulations-Engine bereit, während Züge, U-Bahnen, Straßenbahnen, Gleise, Signale und andere Inhalte als unabhängige Addons vertrieben werden.

<Alert severity="info">

TransitCore trennt die **Engine** vollständig vom **Inhalt**. Das Framework stellt die verschiedenen Simulationssysteme bereit, während die Addons die Fahrzeuge, Gleise, Signale, Bahnhöfe und alle anderen Eisenbahnelemente einbringen.

</Alert>

## Warum TransitCore?

TransitCore wurde rund um vier Grundprinzipien entwickelt.

### Realismus

Das Ziel von TransitCore ist es, die Funktionsweise eines Eisenbahnnetzes so originalgetreu wie möglich nachzubilden und dennoch vollständig in Minecraft integriert zu bleiben.

Das Framework unterstützt unter anderem:

- Eine fortschrittliche Fahrzeugsimulation.
- Realistische Bremssysteme.
- Die Eisenbahnsignalisierung.
- Die elektrischen Systeme.
- Das Fahrgastmanagement.
- Die Mehrspieler-Synchronisierung.
- Hochgeschwindigkeits-Eisenbahnstrecken.

### Modularität

Alles in TransitCore ist modular aufgebaut.

Das Framework selbst enthält ausschließlich die für seinen Betrieb notwendigen Engines.

Fahrzeuge, Infrastruktur, Sounds, Texturen, Benutzeroberflächen und Gameplay-Erweiterungen werden als Addons vertrieben, die unabhängig voneinander installiert, aktualisiert oder entfernt werden können.

### Leistung

TransitCore ist darauf ausgelegt, große Eisenbahnnetze effizient zu verarbeiten.

Rendering, Physik, Netzwerk und Simulation sind so optimiert, dass unnötige Berechnungen reduziert werden, ohne das realistische Verhalten zu beeinträchtigen.

### Erweiterbarkeit

Alle von TransitCore angebotenen Funktionen sind über **LuaTC** erreichbar, die offizielle Skriptsprache des Frameworks.

Entwickler können so vollständige Addons erstellen, ohne den Java-Code von TransitCore ändern zu müssen.

## Architektur

TransitCore besteht aus mehreren unabhängigen Systemen, die zusammenarbeiten.

```text title="TransitCore-Architektur"
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

Jedes System ist für einen bestimmten Teil des Frameworks verantwortlich und kommuniziert mit den anderen über stabile, öffentliche APIs.

## LuaTC

LuaTC ist die offizielle Skriptsprache von TransitCore.

Basierend auf Lua wird sie um APIs erweitert, die speziell für die Eisenbahnsimulation entwickelt wurden. Sie ermöglicht Entwicklern die Interaktion mit dem Framework, ohne direkt auf die internen Mechanismen von Minecraft zugreifen zu müssen.

```luatc title="Ein Fahrzeug erstellen"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

Die meisten Addons können vollständig in LuaTC entwickelt werden. Java ist nur erforderlich, um die interne Funktionsweise von TransitCore zu erweitern.

</Alert>

## Die Addons

TransitCore baut auf einer vollständig Addon-basierten Architektur auf.

Jedes Addon wird unabhängig geladen und kommuniziert über LuaTC mit dem Framework.

Ein Addon kann etwa Folgendes hinzufügen:

- Züge.
- U-Bahnen.
- Straßenbahnen.
- Standseilbahnen.
- Eisenbahngleise.
- Signale.
- Oberleitungen.
- Bahnhöfe.
- Benutzeroberflächen.
- Sounds.
- Gameplay-Erweiterungen.

Wenn beim Laden eines Addons ein Fehler auftritt, deaktiviert TransitCore es automatisch, ohne das Framework oder andere Addons am Start zu hindern.

```text title="Beispiel für die Struktur eines Addons"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Addon-Isolation">

Ein fehlerhaftes Addon kann nicht verhindern, dass TransitCore startet. Das Framework erkennt den Fehler automatisch, deaktiviert nur das betroffene Addon und setzt das Laden aller anderen fort.

</Alert>

## Die Dokumentation

Die Dokumentation ist in mehrere Abschnitte gegliedert.

| Abschnitt | Beschreibung |
|---------|-------------|
| Erste Schritte | TransitCore installieren und Ihr erstes Addon erstellen. |
| LuaTC | Die offizielle Skriptsprache des Frameworks entdecken. |
| Anleitungen | Ausführliche Tutorials zu den wichtigsten Systemen von TransitCore. |
| API-Referenz | Vollständige Dokumentation der Dienste, Klassen, Methoden und Ereignisse. |
| Beispiele | Beispielprojekte, die bewährte Methoden und Framework-Funktionen veranschaulichen. |

## Open Source

TransitCore ist ein Open-Source-Projekt, das von **Fire Sparks Studio** entwickelt wird.

Der Quellcode, die Dokumentation sowie das Issue-Tracking-System sind öffentlich zugänglich, um der Community zu ermöglichen, Verbesserungen vorzuschlagen, Anomalien zu melden und zur Entwicklung des Frameworks beizutragen.

## Nächster Schritt

Wenn Sie TransitCore gerade entdecken, fahren Sie mit **Installation** fort, um Ihre Entwicklungsumgebung vorzubereiten und Ihr erstes Addon zu erstellen.