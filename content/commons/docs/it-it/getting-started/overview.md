---
title: Panoramica
description: Scopri cos'è TransitCore, come funziona e i principi che ne hanno guidato la progettazione.
---

# Panoramica

Benvenuto in **TransitCore**.

TransitCore è un framework modulare di simulazione ferroviaria per Minecraft, progettato per creare reti ferroviarie realistiche grazie a un potente sistema di Addon e al linguaggio di scripting **LuaTC**.

A differenza delle tradizionali mod ferroviarie, TransitCore non fornisce direttamente veicoli o infrastrutture. Il framework mette a disposizione il motore di simulazione, mentre i treni, le metropolitane, i tram, i binari, i segnali e altri contenuti vengono distribuiti come Addon indipendenti.

<Alert severity="info">

TransitCore separa completamente il **motore** dal **contenuto**. Il framework fornisce i diversi sistemi di simulazione, mentre gli Addon apportano i veicoli, i binari, i segnali, le stazioni e tutti gli altri elementi ferroviari.

</Alert>

## Perché TransitCore?

TransitCore è stato sviluppato attorno a quattro principi fondamentali.

### Realismo

L'obiettivo di TransitCore è riprodurre il funzionamento di una rete ferroviaria nel modo più fedele possibile, rimanendo perfettamente integrato in Minecraft.

Il framework supporta in particolare:

- Una simulazione avanzata dei veicoli.
- Sistemi di frenatura realistici.
- La segnalazione ferroviaria.
- I sistemi elettrici.
- La gestione dei passeggeri.
- La sincronizzazione multiplayer.
- Le linee ferroviarie ad alta velocità.

### Modularità

In TransitCore tutto è progettato in modo modulare.

Il framework stesso contiene unicamente i motori necessari al suo funzionamento.

Veicoli, infrastrutture, suoni, texture, interfacce utente ed estensioni di gameplay sono distribuiti come Addon che possono essere installati, aggiornati o rimossi indipendentemente gli uni dagli altri.

### Prestazioni

TransitCore è progettato per gestire in modo efficiente reti ferroviarie di grandi dimensioni.

Il rendering grafico, la fisica, la rete e la simulazione sono ottimizzati per limitare i calcoli non necessari mantenendo un comportamento realistico.

### Estensibilità

Tutte le funzionalità offerte da TransitCore sono accessibili tramite **LuaTC**, il linguaggio di scripting ufficiale del framework.

Gli sviluppatori possono quindi creare Addon completi senza dover modificare il codice Java di TransitCore.

## Architettura

TransitCore è composto da diversi sistemi indipendenti che lavorano insieme.

```text title="Architettura di TransitCore"
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

Ogni sistema è responsabile di una parte precisa del framework e comunica con gli altri attraverso API pubbliche e stabili.

## LuaTC

LuaTC è il linguaggio di scripting ufficiale di TransitCore.

Basato su Lua, lo estende con API progettate specificamente per la simulazione ferroviaria. Consente agli sviluppatori di interagire con il framework senza dover accedere direttamente ai meccanismi interni di Minecraft.

```luatc title="Creare un veicolo"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

La maggior parte degli Addon può essere sviluppata interamente in LuaTC. Java è necessario solo per estendere il funzionamento interno di TransitCore.

</Alert>

## Gli Addon

TransitCore si basa su un'architettura completamente basata sugli Addon.

Ogni Addon è caricato indipendentemente e comunica con il framework tramite LuaTC.

Un Addon può aggiungere, ad esempio:

- Treni.
- Metropolitane.
- Tram.
- Funicolari.
- Binari ferroviari.
- Segnali.
- Linee aeree.
- Stazioni.
- Interfacce utente.
- Suoni.
- Estensioni di gameplay.

Se un Addon riscontra un errore durante il caricamento, TransitCore lo disabilita automaticamente senza impedire al framework o agli altri Addon di avviarsi.

```text title="Esempio di struttura di un Addon"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Isolamento degli Addon">

Un Addon difettoso non può impedire a TransitCore di avviarsi. Il framework rileva automaticamente l'errore, disabilita esclusivamente l'Addon interessato e prosegue il caricamento di tutti gli altri.

</Alert>

## La documentazione

La documentazione è organizzata in diverse sezioni.

| Sezione | Descrizione |
|---------|-------------|
| Per iniziare | Installare TransitCore e creare il primo Addon. |
| LuaTC | Scoprire il linguaggio di scripting ufficiale del framework. |
| Guide | Tutorial dettagliati che coprono i principali sistemi di TransitCore. |
| Riferimento API | Documentazione completa dei servizi, classi, metodi ed eventi. |
| Esempi | Progetti di esempio che illustrano le buone pratiche e le funzionalità del framework. |

## Open Source

TransitCore è un progetto open source sviluppato da **Fire Sparks Studio**.

Il codice sorgente, la documentazione e il sistema di tracciamento dei problemi sono accessibili pubblicamente per consentire alla community di proporre miglioramenti, segnalare anomalie e contribuire allo sviluppo del framework.

## Prossimo passo

Se stai scoprendo TransitCore, continua con **Installazione** per preparare il tuo ambiente di sviluppo e creare il tuo primo Addon.