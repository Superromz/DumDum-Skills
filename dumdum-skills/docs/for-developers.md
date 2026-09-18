# DumDum Skills -- For Developers

How to contribute new skills to the DumDum Skills plugin.


## How skills are organized

Skills live in the `skills/` directory, organized by phase:

```
dumdum-skills/
  .claude-plugin/
    plugin.json
  skills/
    think/
      idea/
        SKILL.md
      who-is-it-for/
        SKILL.md
      break-it-down/
        SKILL.md
    plan/
      sketch-it/
        SKILL.md
      pick-tools/
        SKILL.md
      steps/
        SKILL.md
    build/
      start-project/
        SKILL.md
      add-feature/
        SKILL.md
      fix-problem/
        SKILL.md
      make-it-look-good/
        SKILL.md
    check/
      test-it/
        SKILL.md
      explain-it/
        SKILL.md
      review-it/
        SKILL.md
    ship/
      save-progress/
        SKILL.md
      put-it-online/
        SKILL.md
      tell-people/
        SKILL.md
    learn/
      whats-happening/
        SKILL.md
      teach-me/
        SKILL.md
      glossary/
        SKILL.md
    manage/
      whats-left/
        SKILL.md
      clean-up/
        SKILL.md
      take-notes/
        SKILL.md
  docs/
    README.md
    philosophy.md
    all-skills.md
    for-developers.md
```

Each skill is a single folder containing a `SKILL.md` file. The folder name is the skill name (the part after `dumdum:` in the slash command). The parent folder is the phase.


## Naming conventions

Skill names follow these rules:

1. **Use verb phrases.** Every skill name starts with (or implies) an action. "fix-problem" not "debugger." "save-progress" not "checkpoint."

2. **Use words a non-programmer would say.** If you have to explain the name, the name is wrong. "put-it-online" not "deploy." "whats-left" not "backlog."

3. **Use hyphens to separate words.** All lowercase, hyphens between words. No underscores, no camelCase.

4. **Keep it short.** Two to three words is ideal. Four is the maximum.

Examples of good names: `fix-problem`, `add-feature`, `teach-me`, `pick-tools`

Examples of bad names: `debug-application-errors`, `scaffold`, `init`, `ci-cd-pipeline`


## SKILL.md file structure

A `SKILL.md` file is the complete definition of a skill. It tells Claude Code how to behave when the skill is invoked. Here are the required sections:

```markdown
# Skill Name

One-line description of what this skill does.

## When to use this

A sentence or two about when someone would reach for this skill.

## How it works

Step-by-step instructions for Claude Code to follow when this skill is invoked.
This is the core of the skill. Be specific about:
- What questions to ask the user
- What to look at in the project
- What actions to take
- What to explain along the way
- What to produce at the end

## Tone

Reminders about communication style:
- Use plain English
- Explain every technical term in-line
- One question at a time
- Confirm before making changes

## Output

What the user should walk away with after the skill completes.
Be specific: a file, a list, a summary, a set of changes, etc.
```

### Tips for writing good SKILL.md content

- **Write instructions, not code.** SKILL.md tells Claude Code how to behave. It's a behavioral guide, not a template.
- **Be specific about the interview.** If the skill needs to ask questions, spell out what to ask and in what order. Don't say "ask the user about their project" -- say "ask what the project does, then who it's for, then what makes it different from similar things."
- **Include guardrails.** Tell Claude Code what NOT to do. "Don't use technical terms without explaining them." "Don't make changes without asking first." "Don't assume any other skill has been run."
- **Describe the output concretely.** "Produce a numbered list of features" is better than "help the user understand their features."


## Registering a skill in plugin.json

After creating the `SKILL.md` file, you need to register the skill in `.claude-plugin/plugin.json`. Add an entry to the `skills` array:

```json
{
  "name": "dumdum:your-skill-name",
  "description": "One sentence describing what this skill does, in plain English.",
  "path": "skills/phase/your-skill-name/SKILL.md"
}
```

The fields:

- **name**: Must start with `dumdum:` followed by the folder name. This becomes the slash command (`/dumdum:your-skill-name`).
- **description**: One sentence, plain English, no jargon. This shows up in the skills list so the user knows what it does before running it.
- **path**: Relative path from the plugin root to the SKILL.md file.


## Design principles to follow

Before writing a skill, read the [Design Philosophy](philosophy.md). The short version:

1. **Plain English always.** No jargon without immediate explanation.
2. **Verb phrases humans would say.** Name things naturally.
3. **Explain before doing.** Tell the user what's about to happen.
4. **Translate jargon on the spot.** Define terms where they appear.
5. **Ask questions, don't expect answers.** Interview the user with context.
6. **Teach as you go.** After the work is done, explain what happened.
7. **No assumptions.** Don't assume other skills were run first.
8. **Real tools, real results.** Build real things, not demos.


## Testing a new skill

To test your skill:

1. Make sure the `dumdum-skills` plugin is installed (symlinked or copied to `~/.claude/plugins/dumdum-skills`).

2. Make sure your skill is registered in `plugin.json`.

3. Restart Claude Code to pick up the changes.

4. Run your skill:
   ```
   /dumdum:your-skill-name
   ```

5. Walk through the full conversation. Check these things:
   - Does it explain itself before doing anything?
   - Does it ask questions one at a time?
   - Does it translate technical terms when they come up?
   - Does it confirm before making changes to files?
   - Does it explain what it did afterward?
   - Would someone with zero programming knowledge be able to follow along?

6. Try it on a fresh project with no prior context. The skill should work without any other skill having been run first.

7. Try giving vague or confused answers to its questions. It should handle that gracefully -- asking follow-up questions or offering options, not crashing or producing garbage.

If your skill passes all of these checks, it's ready.


## Adding a new phase

If the existing phases (Think, Plan, Build, Check, Ship, Learn, Manage) don't cover what your skill does, you can create a new phase:

1. Create a new folder under `skills/` with the phase name (lowercase, single word if possible).
2. Add your skill folder inside it.
3. Update the documentation to include the new phase.

Be conservative about adding phases. Most skills fit into one of the existing seven. Only add a new phase if the skill genuinely doesn't belong anywhere else and you expect more skills to join that phase over time.
