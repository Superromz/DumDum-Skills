# DumDum Skills - Project Context

## What This Is

DumDum Skills is a Claude Code plugin that helps non-technical users build real software using plain English. It adds 22 skills to Claude Code, each one designed to guide someone through a specific part of building software without requiring any programming knowledge.

## Why It Exists

Every other AI coding tool assumes you already know how to code. DumDum assumes nothing. It meets people where they are, uses language they already understand, and teaches as it goes. The goal is to make software creation accessible to anyone who can describe what they want in plain English.

## How It Is Structured

The project has three main parts inside the `dumdum-skills/` directory:

- **Plugin manifest** (`dumdum-skills/.claude-plugin/plugin.json`) - Tells Claude Code what skills are available, what they are called, and where to find them.
- **Skill files** (`dumdum-skills/skills/<phase>/<skill-name>/SKILL.md`) - Each skill is a markdown file that instructs Claude how to behave when that skill is invoked.
- **Documentation** (`dumdum-skills/docs/`) - Design philosophy, contributor guide, and a complete skill reference.

## The 7 Phases

1. **Think** - Clarify what you want to build before any code is written.
2. **Plan** - Break your idea into concrete steps and decide on structure.
3. **Build** - Write the actual code, guided step by step.
4. **Check** - Test that everything works and fix what does not.
5. **Ship** - Get your project ready for other people to use.
6. **Learn** - Understand what was built and pick up new concepts along the way.
7. **Manage** - Keep your project organized and running smoothly over time.

## The 8 Design Principles

These principles govern every skill. See `dumdum-skills/docs/philosophy.md` for full details.

1. **Plain English first** - No jargon without an immediate, inline explanation.
2. **One question at a time** - Never overwhelm with multiple choices at once.
3. **Explain before doing** - Say what you are about to do and why before doing it.
4. **Teach after doing** - After completing a step, explain what happened and what the user can learn from it.
5. **Confirm before changing** - Always ask before modifying files, settings, or structure.
6. **Work independently** - Every skill must work on its own without requiring other skills.
7. **Stay in scope** - Do only what the skill is designed to do, nothing more.
8. **Respect the user** - Never talk down, never assume ignorance, just meet people where they are.

## How Skills Work Technically

A user types `/dumdum:<skill-name>` in Claude Code. Claude Code looks up the skill in `plugin.json`, finds the corresponding `SKILL.md` file, and loads it. The SKILL.md contains behavioral instructions that tell Claude what to say, what questions to ask, what to explain, and in what order. It is not a template to fill in. It is a guide for how Claude should act.

## What "Plain English" Means in Practice

- Translate jargon inline: say "a repository (a folder that tracks your project's history)" instead of just "a repository."
- Ask one question at a time, wait for the answer, then move on.
- Explain what you are about to do before you do it.
- After completing a step, teach the user what happened and why it matters.
- Use words a non-programmer would naturally use when describing what they want.
