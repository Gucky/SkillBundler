---
name: "<bundle-slug>"
description: "Use when working with <domain or task area>: <specific tasks, technologies, files, APIs, errors, workflows, outcomes, and terms covered by the bundled Sub-Skills>."
---

<!--
Template for a generated Skill Bundle SKILL.md.
Replace placeholders and remove this comment before finalizing the bundle.
-->

# <Bundle Display Name>

This is a Skill Bundle for <domain or suite>. The bundle itself only routes work; the bundled Sub-Skills provide the actual capabilities.

## Runtime Rule

Read this file first. Do not load bundled Sub-Skills during discovery.

When the task and project context show which capabilities are needed, load only the relevant `SUB_SKILL.md` files and whatever those selected Sub-Skills require.

If routing is unclear, read `bundled-skills/index.json`. Do not read `bundled-skills/manifest.json` unless reviewing, auditing, updating, or checking source/license details.

## Dispatch Map

<!-- Repeat one bullet per bundled Sub-Skill. Do not group multiple Sub-Skills into one entry. -->

- `<subskill-slug>`: Use for <specific tasks or problems>. Signals: <user phrases, files, frameworks, APIs, errors, or terms>. Avoid for <near misses>.
- `<subskill-slug>`: Use for <specific tasks or problems>. Signals: <user phrases, files, frameworks, APIs, errors, or terms>. Related: `<other-subskill-slug>` when <short reason>.

## Bundle Notes

- <Only keep bundle-specific defaults, safety notes, source constraints, or license notes that affect runtime use. Delete this section if there are none.>
