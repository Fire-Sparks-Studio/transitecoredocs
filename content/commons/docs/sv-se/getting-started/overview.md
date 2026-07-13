---
title: Översikt
description: Upptäck vad TransitCore är, hur det fungerar och de principer som har lett dess design.
---

# Översikt

Välkommen till **TransitCore**.

TransitCore är ett modulärt järnvägssimuleringsramverk för Minecraft, utformat för att skapa realistiska järnvägsnätverk genom ett kraftfullt Addon-system och skriptspråket **LuaTC**.

Till skillnad från traditionella järnvägsmoddar tillhandahåller TransitCore inte direkt fordon eller infrastruktur. Ramverket tillhandahåller simuleringsmotorn, medan tåg, tunnelbanor, spårvagnar, spår, signaler och annat innehåll distribueras som oberoende Addon.

<Alert severity="info">

TransitCore separerar helt **motorn** från **innehållet**. Ramverket tillhandahåller de olika simuleringssystemen, medan Addon bidrar med fordon, spår, signaler, stationer och alla andra järnvägselement.

</Alert>

## Varför TransitCore?

TransitCore har utvecklats kring fyra grundläggande principer.

### Realism

Målet med TransitCore är att reproducera hur ett järnvägsnät fungerar så troget som möjligt, samtidigt som det förblir fullt integrerat i Minecraft.

Ramverket stöder bland annat:

- Avancerad fordonssimulering.
- Realistiska bromssystem.
- Järnvägssignalering.
- Elektriska system.
- Hantering av resenärer.
- Flerspelar-synkronisering.
- Höghastighetsjärnvägslinjer.

### Modularitet

Allt i TransitCore är designat modulärt.

Själva ramverket innehåller endast de motorer som krävs för att fungera.

Fordon, infrastruktur, ljud, texturer, användargränssnitt och spelutökningar distribueras som Addon som kan installeras, uppdateras eller avinstalleras oberoende av varandra.

### Prestanda

TransitCore är utformat för att effektivt hantera stora järnvägsnät.

Grafikrendering, fysik, nätverk och simulering optimeras för att begränsa onödiga beräkningar och samtidigt upprätthålla realistiskt beteende.

### Utbygbarhet

Alla funktioner som erbjuds av TransitCore är tillgängliga via **LuaTC**, ramverkets officiella skriptspråk.

Utvecklare kan därmed skapa kompletta Addon utan att behöva ändra TransitCore:s Java-kod.

## Arkitektur

TransitCore består av flera oberoende system som arbetar tillsammans.

```text title="TransitCore-arkitektur"
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

Varje system ansvarar för en specifik del av ramverket och kommunicerar med de andra genom stabila, offentliga API:er.

## LuaTC

LuaTC är TransitCore:s officiella skriptspråk.

Baserat på Lua, utökas det med API:er som är speciellt utformade för järnvägssimulering. Det gör det möjligt för utvecklare att interagera med ramverket utan att direkt behöva komma åt Minecrafts interna mekanismer.

```luatc title="Skapa ett fordon"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

Majoriteten av Addon kan utvecklas helt i LuaTC. Java behövs endast för att utöka TransitCore:s interna funktionalitet.

</Alert>

## Addon

TransitCore bygger på en fullständigt Addon-baserad arkitektur.

Varje Addon laddas oberoende och kommunicerar med ramverket via LuaTC.

Ett Addon kan till exempel lägga till:

- Tåg.
- Tunnelbanor.
- Spårvagnar.
- Bergbanor.
- Järnvägsspår.
- Signaler.
- Kontaktledningar.
- Stationer.
- Användargränssnitt.
- Ljud.
- Spelutökningar.

Om ett Addon stöter på ett fel under laddningen inaktiverar TransitCore det automatiskt utan att hindra ramverket eller andra Addon från att starta.

```text title="Exempel på Addon-struktur"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Addon-isolering">

Ett felaktigt Addon kan inte förhindra att TransitCore startar. Ramverket upptäcker automatiskt felet, inaktiverar endast det berörda Addon och fortsätter att ladda alla andra.

</Alert>

## Dokumentationen

Dokumentationen är uppdelad i flera avsnitt.

| Avsnitt | Beskrivning |
|---------|-------------|
| Komma igång | Installera TransitCore och skapa ditt första Addon. |
| LuaTC | Upptäck ramverkets officiella skriptspråk. |
| Guider | Detaljerade handledningar som täcker TransitCore:s huvudsystem. |
| API-referens | Komplett dokumentation av tjänster, klasser, metoder och händelser. |
| Exempel | Exempelprojekt som illustrerar god praxis och ramverkets funktioner. |

## Open Source

TransitCore är ett öppen källkods-projekt utvecklat av **Fire Sparks Studio**.

Källkoden, dokumentationen och ärendehanteringssystemet är offentligt tillgängliga för att möjliggöra för gemenskapen att föreslå förbättringar, rapportera anomalier och bidra till utvecklingen av ramverket.

## Nästa steg

Om du upptäcker TransitCore för första gången, fortsätt med **Installation** för att förbereda din utvecklingsmiljö och skapa ditt första Addon.