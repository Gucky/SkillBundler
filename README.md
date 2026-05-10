<p align="center">
  <img src="skill-bundler/assets/skill-bundler-circle.png" alt="Skill Bundler" width="140">
</p>

<h1 align="center">Skill Bundler</h1>

<p align="center">
  <img alt="AI Agents - Meta-Skill" src="https://img.shields.io/badge/AI--Agents-Meta--Skill-EF9035?style=flat">
  <a href="LICENSE"><img alt="MIT License" src="https://img.shields.io/badge/License-MIT-blue?style=flat"></a>
  <a href="https://www.linkedin.com/in/wolfgang-muhsal-12408194/"><img alt="LinkedIn" src="https://img.shields.io/badge/Contact-LinkedIn-95a5a6.svg?style=flat"></a>
</p>

Skill Bundler helps create, review, and maintain compact Skill Bundles: one visible top-level skill that routes to multiple hidden `SUB_SKILL.md` Sub-Skills. It is useful when related skills should be packaged together without loading every detailed instruction file during discovery.

## Installing Skill Bundler

Install the skill with `npx`:

```bash
npx skills add https://github.com/Gucky/SkillBundler --skill skill-bundler
```

To install it globally for Codex:

```bash
npx skills add https://github.com/Gucky/SkillBundler --skill skill-bundler --agent codex --global
```

For a specific agent:

```bash
npx skills add https://github.com/Gucky/SkillBundler --skill skill-bundler --agent claude-code
```

For all supported agents:

```bash
npx skills add https://github.com/Gucky/SkillBundler --skill skill-bundler --agent '*'
```

If `npx` is not available, install Node.js first. On macOS with Homebrew:

```bash
brew install node
```

## Using Skill Bundler

In Codex, trigger the skill directly:

```text
$skill-bundler
```

You can also ask naturally:

```text
Use the Skill Bundler skill to create a bundle from these skills.
```

The skill helps with:

- Creating a Skill Bundle folder with `SKILL.md`, `agents/openai.yaml`, and `bundled-skills/`
- Copying source skills into bundled Sub-Skill folders
- Renaming bundled `SKILL.md` files to `SUB_SKILL.md`
- Keeping the generated bundle compact with progressive-disclosure routing
- Validating that bundled Sub-Skills are discoverable only through the bundle

## Safety Model

The skill is structural: it creates and reviews skill bundle layouts. It preserves copied skill content, assets, scripts, references, notices, and licenses unless you explicitly ask for cleanup.

When creating Skill Bundles, always review, respect, and preserve the licenses of the bundled source skills. Only bundle and redistribute skills in ways that are permitted by their original licenses.

## Requirements

- Node.js and `npx` for installation through the Skills CLI
- Source skill folders available on disk when creating bundles
- An AI coding assistant that supports agent skills

## License

Skill Bundler was created by [Wolfgang Muhsal](https://github.com/Gucky). It is available under the [MIT License](LICENSE), which permits commercial use, modification, distribution, and private use.
