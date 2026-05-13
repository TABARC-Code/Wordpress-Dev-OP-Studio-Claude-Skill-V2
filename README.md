# Wordpress-Dev-OP-Studio-Claude-Skill-V2
**WordPress Studio** is a specialist development skill for production-grade WordPress work: themes, plugins, Gutenberg blocks, WooCommerce features, REST API endpoints, Full Site Editing, deployment workflows, accessibility, and the usual pile of hooks, filters, nonces, escaping, and mildly suspicious legacy decisions.

---

# WordPress Studio

**WordPress Studio** is a specialist development skill for production-grade WordPress work: themes, plugins, Gutenberg blocks, WooCommerce features, REST API endpoints, Full Site Editing, deployment workflows, accessibility, and the usual pile of hooks, filters, nonces, escaping, and mildly suspicious legacy decisions.

It is written for a senior developer workflow. Not a tutorial. Not a theme framework. Not another magic box promising to make WordPress behave like a fresh greenfield app. It is a practical operating manual for generating, reviewing, and explaining WordPress code without forgetting the boring bits that keep sites alive.

**Author:** TABARC-Code  
**Status:** Audited draft, suitable for repository publication after the structural fixes below.

---

## What This Skill Does

WordPress Studio gives an assistant a working model for full-stack WordPress development. It favours WordPress-native APIs, explicit security checks, accessible front-end output, clean plugin architecture, and deployable code rather than pretty snippets that fall apart the moment a client installs twelve plugins and a page builder from 2017.

Use it for:

- custom plugins and plugin audits;
- classic and block theme work;
- Gutenberg block architecture;
- WooCommerce development, including HPOS-aware order handling;
- REST API endpoints and data modelling;
- ACF and Gravity Forms integration;
- WP-CLI, Git, staging, deployment, and migration workflows;
- accessibility reviews against WCAG expectations;
- front-end patterns for responsive WordPress builds.

The skill’s main bias is simple: **use the platform properly before inventing a clever replacement**. WordPress has enough ghosts already.

---

## Repository Contents

Current archive contents:

```text
WP-Developer-CSv2/
├── SKILL.md
├── accessibility.md
├── frontend.md
├── git-workflow.md
└── plugin-architecture.md
```

The files are Markdown-based and readable without any special tooling. `SKILL.md` is the core instruction file. The others are supporting references that should be loaded only when relevant.

---

## Audit Summary

### Overall Verdict

The skill is strong in intent and better than the usual “just add a nonce somewhere, probably” WordPress guidance. It has a good security posture, a sensible implementation workflow, useful architectural patterns, and clear separation between core skill behaviour and reference material.

It is not quite ready to publish untouched. The main issue is not quality of advice; it is repository shape. The skill says one thing about its file paths, while the zip does another. Computers, tragically, are literal.

### What Works Well

| Area | Assessment |
|---|---|
| Security | Strong baseline: sanitisation, escaping, nonce checks, capability checks, prepared SQL, upload handling, and direct-access blocking are all covered. |
| WordPress architecture | Good preference for hooks, loaders, activation/deactivation routines, `dbDelta()`, custom post types, and enqueue discipline. |
| Accessibility | Useful practical coverage of semantic HTML, labels, keyboard access, skip links, ARIA restraint, and contrast checks. |
| Deployment thinking | Sensible Git exclusions, environment separation, WP-CLI migration notes, staging-to-production workflow, and debugging constants. |
| Tone of implementation | Opinionated enough to prevent sloppy output, but not so rigid that it becomes unusable. Mostly. |

### Issues to Fix Before Release

| Priority | Issue | Why It Matters | Recommended Fix |
|---|---|---|---|
| High | `SKILL.md` refers to `references/*.md`, but the actual archive stores reference files at root. | Any loader, contributor, or tired developer following the declared paths will hit missing files. | Move reference files into a `references/` directory, or update every reference path in `SKILL.md`. Prefer moving the files. |
| High | Several referenced files are missing entirely. | `SKILL.md` lists references that are not present, including security, WooCommerce, REST API, performance, hooks, Gutenberg, theme development, documentation standards, and skill network docs. | Add the missing files or remove those entries until they exist. Placeholders are acceptable only if clearly labelled. |
| Medium | Trigger list is broad and contains duplication. | Terms like `Git`, `deployment`, and `responsive design` may trigger the skill for work that is not actually WordPress-specific. `ACF` also appears twice. | Remove duplicates and narrow generic triggers with WordPress context. |
| Medium | Database guidance is slightly over-absolute. | “Prepare every database query” conflicts with schema creation and static queries. The checklist later says static queries with no user input do not require preparation. | Change the hard rule to: prepare every query containing variable data. |
| Medium | Knowledge baseline needs a maintenance note. | The skill currently targets WordPress 6.4+ and PHP 8.1+. That may be deliberate, but it should be marked as a supported baseline rather than current-state truth. | Add an “audited against” date and a small version maintenance policy. |
| Low | Author metadata varies. | Files mention `TABARC-Code / Blackwood Studio`, while this repo request specifies `TABARC-Code`. | Pick one public author identity and use it consistently. This README uses `TABARC-Code`. |
| Low | No declared licence. | GitHub readers need to know whether they can use, fork, or adapt the skill. Silence is not a licence; it is a future argument. | Add a `LICENCE` file or a clear “all rights reserved” note. |
| Low | No contribution or changelog files. | Not fatal, but useful once this leaves a private folder and enters the swamp. | Add `CONTRIBUTING.md` and `CHANGELOG.md` when the repo becomes collaborative. |

---

## Recommended Repository Structure

A cleaner structure would be:

```text
wordpress-studio/
├── README.md
├── Description.md
├── SKILL.md
├── LICENCE
├── CHANGELOG.md
└── references/
    ├── accessibility.md
    ├── frontend.md
    ├── git-workflow.md
    ├── plugin-architecture.md
    ├── documentation-standards.md
    ├── gutenberg-blocks.md
    ├── hooks-filters.md
    ├── performance.md
    ├── rest-api.md
    ├── security.md
    ├── skill-network.md
    ├── theme-development.md
    └── woocommerce.md
```

If the missing reference files are not ready, do not pretend they are. Either remove them from `SKILL.md` for now, or add short stub files with a clear `TODO` heading and no fake authority. Future-you will appreciate the honesty, probably through gritted teeth.

---

## Installation / Use

1. Clone or download the repository.
2. Keep `SKILL.md` at the root unless your loader expects another location.
3. Place all supporting documents in `references/`, or update the paths inside `SKILL.md` to match the real layout.
4. Load `SKILL.md` as the primary instruction file.
5. Load reference files only when a task needs them.

The skill is designed to avoid loading every reference at once. That is a good instinct. Massive context dumps are where nuance goes to die.

---

## Maintenance Notes

Review the skill when any of these change:

- major WordPress releases;
- WooCommerce storage or checkout behaviour;
- Gutenberg block APIs;
- PHP version support expectations;
- WordPress Coding Standards updates;
- WCAG guidance;
- common deployment patterns for DDEV, WP-CLI, GitHub Actions, and managed hosts.

Keep a visible audit date in `SKILL.md`. Version baselines are useful. Stale baselines pretending to be eternal law are less charming.

Suggested version policy:

```text
MAJOR: structural rewrite or major scope change
MINOR: new reference file, new WordPress/WooCommerce capability, major pattern update
PATCH: typo, phrasing, small example correction, broken-link fix
```

---

## Development Standards Encoded by the Skill

The skill expects generated WordPress work to include:

- WordPress Coding Standards rather than generic PSR-only style;
- namespaced or prefixed functions and classes;
- explicit hook priorities and accepted argument counts;
- sanitisation at input boundaries;
- escaping at output boundaries;
- nonce checks for form and AJAX actions;
- capability checks for admin actions;
- `WP_Error` or WordPress-native error handling where suitable;
- semantic, keyboard-accessible front-end markup;
- mobile-first CSS;
- deployment-safe Git habits.

That is the point of the skill: not to produce more code, but to produce fewer little disasters.

---

## Known Gaps

This package currently lacks full reference coverage for several domains listed in `SKILL.md`:

- security deep dive;
- WooCommerce-specific hooks and HPOS examples;
- REST API endpoint architecture;
- Gutenberg block examples;
- performance and caching patterns;
- theme development and FSE details;
- hook/filter reference patterns;
- documentation standards;
- skill network contracts.

These are not tiny extras. They are named parts of the advertised surface area. Ship them, stub them, or remove the claims.

---

## Release Checklist

Before making this public:

- [ ] Move reference files into `references/`, or rewrite all paths.
- [ ] Add missing referenced documents or remove references to them.
- [ ] Remove duplicate triggers.
- [ ] Decide whether author metadata is `TABARC-Code` only.
- [ ] Add a `LICENCE` file.
- [ ] Add a changelog.
- [ ] Add an audit date and version baseline note.
- [ ] Re-read all examples for WPCS, escaping, and capability checks.
- [ ] Test the skill on at least one plugin build, one code review, one migration query, and one accessibility task.

---

## Author

**TABARC-Code**

