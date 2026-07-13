---
title: Přehled
description: Zjistěte, co je TransitCore, jak funguje a jaké principy stály za jeho návrhem.
---

# Přehled

Vítejte v **TransitCore**.

TransitCore je modulární framework pro simulaci železnice v Minecraftu, navržený pro vytváření realistických železničních sítí díky výkonnému systému Addonů a skriptovacímu jazyku **LuaTC**.

Na rozdíl od tradičních železničních modů TransitCore přímo neposkytuje vozidla ani infrastrukturu. Framework dodává simulační engine, zatímco vlaky, metro, tramvaje, koleje, návěstidla a další obsah jsou distribuovány jako nezávislé Addony.

<Alert severity="info">

TransitCore zcela odděluje **engine** od **obsahu**. Framework poskytuje různé simulační systémy, zatímco Addony přinášejí vozidla, koleje, návěstidla, stanice a všechny další železniční prvky.

</Alert>

## Proč TransitCore?

TransitCore byl vyvíjen na základě čtyř základních principů.

### Realismus

Cílem TransitCore je co nejvěrněji reprodukovat fungování železniční sítě a přitom zůstat plně integrován v Minecraftu.

Framework mimo jiné podporuje:

- Pokročilou simulaci vozidel.
- Realistické brzdové systémy.
- Železniční návěstní systémy.
- Elektrické systémy.
- Správu cestujících.
- Synchronizaci pro více hráčů.
- Vysokorychlostní železniční tratě.

### Modularita

Vše v TransitCore je navrženo modulárně.

Samotný framework obsahuje pouze motory nezbytné pro svou funkčnost.

Vozidla, infrastruktura, zvuky, textury, uživatelská rozhraní a rozšíření hratelnosti jsou distribuována jako Addony, které lze instalovat, aktualizovat nebo odebírat nezávisle na sobě.

### Výkon

TransitCore je navržen tak, aby efektivně zvládal rozsáhlé železniční sítě.

Vykreslování, fyzika, síť a simulace jsou optimalizovány tak, aby omezily zbytečné výpočty a zároveň zachovaly realistické chování.

### Rozšiřitelnost

Všechny funkce nabízené TransitCore jsou přístupné přes **LuaTC**, oficiální skriptovací jazyk frameworku.

Vývojáři tak mohou vytvářet kompletní Addony, aniž by museli upravovat kód Java v TransitCore.

## Architektura

TransitCore se skládá z několika nezávislých systémů, které spolupracují.

```text title="Architektura TransitCore"
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

Každý systém odpovídá za konkrétní část frameworku a komunikuje s ostatními prostřednictvím stabilních veřejných API.

## LuaTC

LuaTC je oficiální skriptovací jazyk TransitCore.

Na základě Lua je rozšířen o API speciálně navržená pro simulaci železnice. Umožňuje vývojářům interagovat s frameworkem, aniž by museli přímo přistupovat k interním mechanismům Minecraftu.

```luatc title="Vytvoření vozidla"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

Většina Addonů může být vyvinuta kompletně v LuaTC. Java je potřeba pouze pro rozšíření vnitřního fungování TransitCore.

</Alert>

## Addony

TransitCore se opírá o architekturu plně založenou na Addonech.

Každý Addon se načítá nezávisle a komunikuje s frameworkem prostřednictvím LuaTC.

Addon může přidat například:

- Vlaky.
- Metro.
- Tramvaje.
- Lanové dráhy.
- Železniční tratě.
- Návěstidla.
- Trolejové vedení.
- Stanice.
- Uživatelská rozhraní.
- Zvuky.
- Rozšíření hratelnosti.

Pokud Addon během načítání narazí na chybu, TransitCore jej automaticky zakáže, aniž by zabránil startu frameworku nebo ostatních Addonů.

```text title="Příklad struktury Addonu"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Izolace Addonů">

Vadný Addon nemůže zabránit spuštění TransitCore. Framework automaticky rozpozná chybu, zakáže pouze dotčený Addon a pokračuje v načítání všech ostatních.

</Alert>

## Dokumentace

Dokumentace je rozdělena do několika sekcí.

| Sekce | Popis |
|---------|-------------|
| Začínáme | Nainstalovat TransitCore a vytvořit svůj první Addon. |
| LuaTC | Objevit oficiální skriptovací jazyk frameworku. |
| Návody | Podrobné tutoriály zabývající se hlavními systémy TransitCore. |
| Reference API | Kompletní dokumentace služeb, tříd, metod a událostí. |
| Příklady | Ukázkové projekty ilustrující osvědčené postupy a funkce frameworku. |

## Open Source

TransitCore je open source projekt vyvíjený studiem **Fire Sparks Studio**.

Zdrojový kód, dokumentace a systém pro sledování problémů jsou veřejně přístupné, aby mohla komunita navrhovat vylepšení, hlásit anomálie a přispívat k vývoji frameworku.

## Další krok

Pokud TransitCore teprve objevujete, pokračujte na **Instalace**, abyste si připravili vývojové prostředí a vytvořili svůj první Addon.