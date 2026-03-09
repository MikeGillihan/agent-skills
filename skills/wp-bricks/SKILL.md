---
name: wp-bricks
description: "Use when working with Bricks Builder themes/sites: layout and templates, elements, dynamic data, conditions, and customizations via PHP hooks/filters."
compatibility: "Targets WordPress 6.x+ with Bricks Builder. Requires Bricks license for full features."
---

# Bricks Builder

## When to use

Use this skill for Bricks Builder work such as:

- layout and template design (sections, containers, elements)
- dynamic data tags and conditions
- customizations via PHP (hooks, filters)
- query loops and custom field integration (ACF, Meta Box, JetEngine, etc.)
- Bricks-specific elements and controls

## Inputs required

- Repo root; whether this is a Bricks theme or a theme-agnostic site using Bricks.
- Target WordPress and PHP versions.
- Which custom field plugin (if any) the site uses (ACF, Meta Box, etc.).

## Procedure

### 0) Triage first

1. Run triage: `node skills/wp-project-triage/scripts/detect_wp_project.mjs`
2. Confirm project kind (wp-site, wp-theme) and tooling.

### 1) Reference Bricks structure and conventions

- Prefer Bricks filters and actions over modifying core Bricks files.
- Use the dynamic data picker (lightning bolt icon) patterns when describing UI changes.
- For programmatic changes, consult the reference files and [Bricks Academy](https://academy.bricksbuilder.io/).

Read:
- `references/structure.md`
- `references/hooks-and-filters.md`
- `references/dynamic-data.md`

### 2) Common patterns

- **Elements:** Register or modify via `bricks/builder/elements`, `bricks/elements/{element_name}/controls`.
- **Query loops:** Use `bricks/posts/query_vars` to manipulate query variables.
- **Dynamic data:** Use tag filters (e.g. `bricks/dynamic_data/post_terms_separator`) to transform output.
- **Settings panels:** Use `builder/settings/{type}/controls_data` for Page or Template Settings.

## Verification

- Changes should work in the Bricks editor and on the frontend.
- Test with the correct template conditions (single, archive, etc.).
- If using custom fields, ensure the field plugin is active and the field keys/names match.

## Failure modes / debugging

- Dynamic data not rendering: check tag syntax, field name/key, and that the data source exists.
- Template not applying: verify template type and conditions in Bricks.
- Custom PHP in dynamic data: use `{echo:functionName}` or `{do_action:hook}`; ensure the function/hook is defined and safe.

## Escalation

For canonical documentation, consult [Bricks Academy](https://academy.bricksbuilder.io/) and [Bricks dynamic data docs](https://bricksbuilder.io/dynamic-data).
