# DumDum Skills - Project Instructions

## Overview

DumDum Skills is a Claude Code plugin that helps non-technical users build real software using plain English. The plugin lives in the `dumdum-skills/` subdirectory. Skills are markdown files located at `skills/<phase>/<skill-name>/SKILL.md`.

## Key Files

- `dumdum-skills/.claude-plugin/plugin.json` - Skill registry. Every skill must be listed here.
- `dumdum-skills/docs/philosophy.md` - Design principles that govern how skills are written.
- `dumdum-skills/docs/all-skills.md` - Complete list of all available skills.
- `package.json` - Version tracking for the project.

## Writing Style Rules

- All user-facing text must be plain English. No jargon without an immediate inline explanation.
- Skill names are verb phrases a non-programmer would say (e.g., "fix-problem" not "debug").
- Never use em-dashes in any file. Use commas, periods, or rewrite the sentence.
- No emojis unless explicitly requested.

## Skill Structure

Each SKILL.md instructs Claude how to behave when the skill is invoked. It is a behavioral guide, not a template. The file tells Claude what to say, what to ask, what to explain, and in what order.

## Adding a New Skill

1. Create the folder: `dumdum-skills/skills/<phase>/<skill-name>/`
2. Write the `SKILL.md` file inside that folder.
3. Register the skill in `dumdum-skills/.claude-plugin/plugin.json`.
4. Update `dumdum-skills/docs/all-skills.md` with the new skill.

## Workflow Rules

- Commit messages: short single sentence, no co-author lines.
- Never deploy, push, or commit without explicit user confirmation.
- Version is tracked in `package.json` at the repo root.
