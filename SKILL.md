---
name: "skill-bundler"
description: "Use when creating, reviewing, or maintaining a Skill Bundle: one visible top-level skill that routes to multiple copied hidden SUB_SKILL.md sub-skills using a root skill_bundle_template.md template and progressive-disclosure loading."
---

# Skill Bundler

Create or review Skill Bundles. A Skill Bundle does not provide domain capabilities itself; only the bundled Sub-Skills do the real work.

## Core Rules

- Use `skill_bundle_template.md` as the authoritative template for the generated bundle `SKILL.md`.
- Keep the generated bundle `SKILL.md` short: runtime rule, dispatch map, and essential bundle-specific notes only.
- Do not copy Sub-Skill content into the generated bundle `SKILL.md`.
- Copy source skill folders whole, then rename only each copied `SKILL.md` to `SUB_SKILL.md`.
- Preserve copied files, assets, scripts, references, notices, and licenses unless the user explicitly asks for cleanup.

## Workflow

1. Confirm the bundle name, folder slug, and source skills.
2. Inspect each source skill just enough to understand its trigger, purpose, resources, and license/source notes.
3. Create the bundle folder with `SKILL.md`, `agents/openai.yaml`, and `references/bundled-skills/`.
4. Copy each source skill into `references/bundled-skills/<subskill-slug>/`.
5. Rename each copied top-level `SKILL.md` to `SUB_SKILL.md`; do not leave discoverable `SKILL.md` files below `references/bundled-skills/`.
6. Fill `skill_bundle_template.md` to write the generated bundle `SKILL.md`.
7. Add a compact `references/bundled-skills/index.json` for runtime routing when the dispatch map is not enough.
8. Add a `references/bundled-skills/manifest.json` only for review, audit, source, license, and update context.
9. Validate the bundle before handing it back.

## Generated Bundle Shape

```text
<bundle-slug>/
  SKILL.md
  agents/openai.yaml
  references/
    bundled-skills/
      index.json
      manifest.json
      <subskill-slug>/
        SUB_SKILL.md
        ...
```

## Template Use

Open `skill_bundle_template.md` before writing a generated bundle `SKILL.md`. Replace placeholders, remove unused optional notes, and keep the result shorter than the source skills it routes to.

The generated dispatch map should help choose likely Sub-Skills without opening every copied folder. Put detailed capability metadata in `index.json`, not in the top-level bundle `SKILL.md`.

## Validation

- `find references/bundled-skills -name SKILL.md` returns no files.
- Every Sub-Skill path named by the generated bundle exists.
- `index.json` is valid JSON and points to existing `SUB_SKILL.md` files.
- `manifest.json`, if present, is valid JSON and is not required for normal runtime use.
- `agents/openai.yaml` exists and describes the generated bundle, not this Skill Bundler.
- The generated bundle `SKILL.md` says to load only relevant Sub-Skills after the task need is clear.
- The generated bundle `SKILL.md` stays compact and does not duplicate Sub-Skill instructions.
