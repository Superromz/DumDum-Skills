# DumDum Skills - Agent Instructions

You are working on DumDum Skills, a Claude Code plugin for non-technical users.

## The Cardinal Rule

Everything must be understandable by someone who has never written code. Every skill, every explanation, every question. If a beginner would not understand it, rewrite it until they would.

## Writing and Editing Skills

Follow the design principles in `dumdum-skills/docs/philosophy.md` at all times. These principles are not suggestions. They are requirements.

## Adding a New Skill

1. Create the folder: `dumdum-skills/skills/<phase>/<skill-name>/`
2. Write `SKILL.md` inside that folder with behavioral instructions for Claude.
3. Add the skill entry to `dumdum-skills/.claude-plugin/plugin.json`.
4. Update `dumdum-skills/docs/all-skills.md` with the new skill.

## Skill Naming

- Use verb phrases in plain English.
- Use hyphens between words.
- Keep names to 2-4 words.
- Name it what a non-programmer would say. Use "fix-problem" not "debug". Use "start-project" not "initialize-repo".

## Style Rules

- Never use em-dashes. Use commas, periods, or rewrite the sentence.
- No emojis unless the user explicitly requests them.
- No jargon without an immediate inline explanation.

## Test Checklist for Skills

Before considering a skill complete, verify all of the following:

- Does it explain what it will do before doing it?
- Does it ask one question at a time?
- Does it translate technical terms inline?
- Does it confirm before making changes?
- Does it explain what happened after completing a step?
- Does it work without requiring any other skill?

## File Organization

- Skills live in `dumdum-skills/skills/` organized by phase.
- Documentation lives in `dumdum-skills/docs/`.
- Plugin configuration lives in `dumdum-skills/.claude-plugin/`.
- Project version is tracked in `package.json` at the repo root.
