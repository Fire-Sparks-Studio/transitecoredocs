# Contributing to TransitCore Documentation

First of all, thank you for taking the time to contribute to TransitCore's
documentation. This document describes the different ways you can help and the
conventions to follow so that your contribution can be merged quickly.

This repository (`transitcoredocs`) only contains **documentation**. The mod
source code lives in a separate repository:
[Le-noirrateur/transitcore](https://github.com/Le-noirrateur/transitcore).

By contributing to this repository, you agree that your contributions are
licensed under the [Creative Commons Attribution-ShareAlike 4.0 International
license](./LICENSE) (CC BY-SA 4.0). See [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md)
for the standards expected within our community.

---

## Table of contents

- [Ways to contribute](#ways-to-contribute)
- [Reporting issues](#reporting-issues)
- [Improving the documentation](#improving-the-documentation)
- [Helping with translations](#helping-with-translations)
- [Helping with the mod](#helping-with-the-mod)
- [Markdown conventions](#markdown-conventions)
- [Pull request workflow](#pull-request-workflow)
- [License](#license)

---

## Ways to contribute

You can help the project in three complementary ways:

1. **Improving the documentation** — fixing typos, clarifying explanations,
   adding missing pages, keeping screenshots up to date.
2. **Translating** — helping translate the documentation into your language
   via our Crowdin project.
3. **Developing the mod** — contributing Java code, LuaTC APIs or 3D models to
   the mod itself.

---

## Reporting issues

Please open GitHub issues on the **right** repository:

| Subject | Repository |
|--------|-----------|
| Documentation typos, inaccuracies, missing or outdated pages, broken links | Not avaliable for now |
| Bugs, crashes or feature requests related to the mod, LuaTC or Addons | [`transitcore/issues`](https://github.com/Le-noirrateur/transitcore/issues) |

When opening an issue, please include:

- A clear, descriptive title.
- The impacted page (full path, e.g. `content/commons/docs/en-us/getting-started/installation.md`).
- The version of TransitCore you are using (if applicable).
- Any relevant log excerpt (use code blocks — see [Markdown conventions](#markdown-conventions)).

---

## Improving the documentation

### Canonical source language

The **canonical source** of the documentation is written in **English** and
lives under:

```
content/commons/docs/en-us/
```

This is also what Crowdin uses as its source (see `crowdin.yml`). All
non-trivial changes to content (wording, structure, new pages) must be made
**against the English source first**.

> The `content/commons/docs/fr-fr/` folder is a manually maintained French
> reference translation. It is kept in sync by the maintainers and should not
> be edited through Pull Requests unless you are also updating the English
> source. For any other language, please use Crowdin (next section). See the
> README for the full list of supported locales.

### What you can help with

- Fix typos, grammar and broken links.
- Make explanations clearer or more accurate.
- Add examples, diagrams or screenshots.
- Document newly released features.
- Keep the API reference up to date when the mod's public API changes.

### Structure

Each section sits in its own folder (for example `getting-started/`). A typical
documentation page looks like:

```markdown
---
title: Page title
description: One-line summary used by search and SEO.
---

# Page title

Introduction paragraph.

## A section
...

## Next step
Continue with **Page Name** to ...
```

The trailing **Next step** section pointing to the next logical page is a
convention used across the documentation — please keep it when adding new pages
to an existing section.

---

## Helping with translations

Translations are **not** managed through Pull Requests on the language folders.
They go through our official Crowdin project:

> <https://crwd.in/transitcore/a602f6b7f433442aba9156c216d3f6062823917>

To contribute a translation:

1. Join the project on Crowdin using the link above.
2. Choose your language (or request it if it is not listed yet).
3. Translate or vote on strings online; Crowdin will push the result back to
   this repository under `content/commons/docs/<locale>/` and
   `content/commons/navigation/<locale>/` (see `crowdin.yml`).

Crowdin is the single source of truth for every locale **other than `en-us`**
and `fr-fr`. Please do not open Pull Requests that modify translated files
directly under `content/commons/docs/<locale>/` or
`content/commons/navigation/<locale>/` — they will be overwritten by the next
Crowdin sync.

If you spot a mistake in the **English source** (a typo or a sentence that is
hard to translate), open a PR against `content/commons/docs/en-us/` as described
above — fixing the source benefits every language at once.

---

## Helping with the mod

The mod itself (Java code, LuaTC runtime, rendering, physics, networking, etc.)
is developed in a separate repository:

> <https://github.com/Le-noirrateur/transitcore/issues>

Please:

- Read that repository's own `CONTRIBUTING.md` if present.
- Open mod-related Pull Requests **there**, not in this documentation
  repository.
- Keep Pull Requests focused: one feature or one bug fix per PR.

This documentation repository only reflects the **publicly documented** part of
the mod's API and Addon system. If you add a new public LuaTC API to the mod,
please also open a documentation PR here describing it.

---

## Markdown conventions

To keep the docs consistent, please follow these conventions:

- **Front matter** — every page must start with a YAML front matter block
  containing `title` and `description`:
  ```yaml
  ---
  title: Page title
  description: Short summary of the page.
  ---
  ```

- **Headings** — use a single `#` for the page title (matching `title`),
  `##` for top-level sections, `###` for subsections. Avoid jumping heading
  levels.

- **Code blocks** — always set a language tag, and use a `title` attribute
  when relevant:
  ```text title="Example structure"
  MyAddon/
  └── addon.yaml
  ```
  Supported language tags used in this project: `text`, `yaml`, `luatc`.

- **Alerts** — callouts use the custom `<Alert>` component:
  ```markdown
  <Alert severity="info">
  Informational message.
  </Alert>
  ```
  Recognized severities: `info`, `success`, `warning`. An optional `title`
  attribute can be added: `<Alert severity="warning" title="...">`.

- **Links** — prefer relative links between documentation pages. Always link
  the next logical page through the **Next step** section at the end of the
  page.

- **Line endings** — this repository normalizes line endings to LF (see
  `.gitattributes`). Configure your editor to use LF and avoid committing CRLF
  reformatting of unrelated files.

---

## Pull request workflow

1. **Fork** the repository and clone your fork.
2. Create a focused branch:
   ```
   git checkout -b docs/installation-fix
   ```
3. Make your changes **against the English source** under
   `content/commons/docs/en-us/` (or under `content/commons/navigation/en-us/`
   for navigation files).
4. Commit with a clear message, e.g.:
   ```
   docs(installation): clarify NeoForge version requirement
   ```
5. Push to your fork and open a Pull Request against the `main` branch of
   `Fire-Sparks-Studio/transitcoredocs`.
6. Link any related issue in the PR description (`Closes #123`).

Please keep Pull Requests small and focused. Large refactors affecting many
pages at once are harder to review — consider splitting them into several PRs.
If you are planning a large change (new section, reorganization, new component
type), open an issue first so we can discuss it before you start writing.

---

## License

By submitting a contribution to this repository, you agree that your
contribution is licensed under the [Creative Commons Attribution-ShareAlike 4.0
International](./LICENSE) license (CC BY-SA 4.0), the same license that covers
the rest of this documentation.

If your contribution contains pre-existing work authored by someone else,
make sure it is compatible with CC BY-SA 4.0 and that you are allowed to
redistribute it under this license. When in doubt, ask in an issue before
opening the PR.

By participating in this project, you also agree to abide by our
[Code of Conduct](./CODE_OF_CONDUCT.md).