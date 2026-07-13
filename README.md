# TransitCore Documentation

This repository holds the **source content** for the official TransitCore
documentation, hosted at
<https://firesparks.mceteams.com/transitcore/docs>.

TransitCore is a modular railway simulation framework for Minecraft (NeoForge),
developed by **Fire Sparks Studio**. The framework and its LuaTC scripting
language let the community build realistic railway networks through Addons —
trains, metros, trams, tracks, signals, catenaries, stations and more. This
repository documents how to install, use and extend TransitCore; it does **not**
contain the mod source code.

---

## What lives here

| Path | Purpose |
|------|---------|
| `content/commons/docs/` | Markdown documentation pages, one folder per language. |
| `content/commons/navigation/` | YAML navigation files (sidebar/sections), one folder per language. |
| `crowdin.yml` | Crowdin configuration: declares the English source and where translations are written. |
| `LICENSE` | Documentation license — [CC BY-SA 4.0](#license). |
| `CODE_OF_CONDUCT.md` | Community standards based on the Contributor Covenant 2.1. |
| `CONTRIBUTING.md` | How to contribute to the docs, translations and the mod. |

This repository **does not** contain the mod source. For that, see
[Fire-Sparks-Studio/transitcore](https://github.com/Fire-Sparks-Studio/transitcore).

---

## How this repository is used

Every Markdown page under `content/commons/` is published to the TransitCore
documentation website:

> <https://firesparks.mceteams.com/transitcore/docs>

The website reads the files in `content/commons/docs/` (page content) and
`content/commons/navigation/` (sidebars / table of contents) directly from this
repository, so merging a change here is enough to update the live site.

### Source language

The **canonical source** is written in **English** and lives under:

```
content/commons/docs/en-us/
content/commons/navigation/en-us/
```

This is also what Crowdin uses as its source (see `crowdin.yml`). All content
changes — wording, new pages, structural edits — must be made against the
English source first. The `fr-fr/` folder is a manually maintained French
reference translation kept in sync by the maintainers; it should only be edited
alongside the corresponding English source.

### Supported locales

Documentation is available (or in progress) in the following locales:

| Code | Language | Maintained as |
|------|----------|----------------|
| `en-us` | English (United States) | Canonical source — edit directly |
| `fr-fr` | French (France) | Manual reference translation — edit alongside source |
| `cs-cz`, `de-de`, `es-es`, `it-it`, `ja-jp`, `pt-pt`, `en-nz`, … | Other languages | Crowd-sourced via Crowdin — do not edit directly in Git |

New languages can be requested through the Crowdin project (see
[Contributing](#contributing)).

---

## Repository structure

```text
transitecoredocs/
├── content/
│   └── commons/
│       ├── docs/
│       │   ├── en-us/                 # canonical English source
│       │   │   └── getting-started/
│       │   ├── fr-fr/                  # manual French reference translation
│       │   └── <locale>/              # other languages, synced by Crowdin
│       └── navigation/
│           ├── index.yaml
│           ├── en-us/                 # English navigation
│           ├── fr-fr/
│           └── <locale>/              # other languages, synced by Crowdin
├── crowdin.yml                         # Crowdin source/translation mapping
├── .gitattributes                      # LF normalization
├── LICENSE                             # CC BY-SA 4.0
├── CODE_OF_CONDUCT.md                 # Contributor Covenant 2.1
├── CONTRIBUTING.md                     # Contributor guide
└── README.md                           # This file
```

Each documentation page is a single Markdown file with a YAML front matter
(`title`, `description`) and optional `<Alert>` callouts. See
[CONTRIBUTING.md](./CONTRIBUTING.md) for the full Markdown conventions.

---

## Contributing

We welcome contributions of all kinds — fixing typos, improving explanations,
adding examples, or helping translate the documentation into your language.

Please read [CONTRIBUTING.md](./CONTRIBUTING.md) for the full guide. In short:

- **Documentation fixes** → open a Pull Request against
  `content/commons/docs/en-us/` (the canonical English source).
- **Translations** → join our Crowdin project at
  <https://crwd.in/transitcore/a602f6b7f433442aba9156c216d3f6062823917>
  and translate online; Crowdin syncs results back into this repository.
- **Mod contributions** (Java, LuaTC, rendering, physics, …) → head over to
  [Fire-Sparks-Studio/transitcore](https://github.com/Fire-Sparks-Studio/transitcore).

By participating in this project, you agree to abide by our
[Code of Conduct](./CODE_OF_CONDUCT.md).

---

## License

The documentation in this repository is licensed under the
[Creative Commons Attribution-ShareAlike 4.0 International](./LICENSE)
license (CC BY-SA 4.0).

In short, you are free to **share** and **adapt** this documentation, including
for commercial purposes, as long as you:

- credit TransitCore / Fire Sparks Studio (attribution), and
- distribute any derivative work — including translations — under the same
  license (ShareAlike).

This license is what makes community translations via Crowdin possible while
keeping the documentation free and open.

---

## Links

- **Documentation website:** <https://firesparks.mceteams.com/transitcore/docs>
- **Mod source code:** [Fire-Sparks-Studio/transitcore](https://github.com/Fire-Sparks-Studio/transitcore)
- **Studio:** [Fire Sparks Studio](https://github.com/Fire-Sparks-Studio)
- **Crowdin project:** <https://crwd.in/transitcore/a602f6b7f433442aba9156c216d3f6062823917>
- **Issues (docs):** [open an issue](https://github.com/Fire-Sparks-Studio/transitecoredocs/issues)
- **Issues (mod):** [open an issue on transitcore](https://github.com/Fire-Sparks-Studio/transitcore/issues)