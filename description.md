# Description

**WordPress Studio** is a senior WordPress development skill by **TABARC-Code**. It is built for production-minded work across custom plugins, themes, Gutenberg blocks, WooCommerce, REST API endpoints, Full Site Editing, accessibility, deployment, migration, and front-end implementation.

It is not a cheerful snippet machine. It is closer to an old developer leaning over the desk saying, “Yes, that works locally, but what happens when staging has object cache, WooCommerce HPOS, and a client with admin access?” Annoying, perhaps. Useful, definitely.

The skill favours WordPress-native APIs, explicit security checks, clear hook architecture, accessible markup, mobile-first CSS, and deployment-safe habits. It pushes generated work towards sanitised inputs, escaped outputs, nonce-protected actions, capability checks, prepared SQL where variable data is involved, and documentation that a human can read without needing a second coffee and a grudge.

## Scope

WordPress Studio covers:

- plugin architecture and activation/deactivation routines;
- theme and front-end implementation patterns;
- Gutenberg block structure;
- WooCommerce-aware development, including HPOS concerns;
- REST API endpoint planning;
- ACF and Gravity Forms integration;
- Git, local development, staging, deployment, and migration workflows;
- accessibility guidance for WCAG-minded WordPress builds;
- WP-CLI and debugging practices.

## Audit Note

The current package has a strong core, but the repository structure needs tidying before release. `SKILL.md` refers to reference files under `references/`, while the supplied archive stores the available reference files at the root. Several reference files named in `SKILL.md` are also missing. That is not a philosophical problem. It is a path problem, and path problems tend to win.

Recommended fix: create a `references/` directory, move the existing reference files into it, and add or remove the missing references so the skill only advertises files that exist.

## Intended Use

Use this skill when the task involves WordPress implementation, WordPress code review, WooCommerce behaviour, Gutenberg blocks, plugin structure, theme architecture, deployment, migration, accessibility, or front-end integration in a WordPress environment.

Avoid using it for generic PHP, generic JavaScript, or generic Git questions unless WordPress is actually part of the problem. Otherwise it may arrive wearing a hard hat at a picnic.

## Author

**TABARC-Code**
