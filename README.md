# DumDum Skills

**Build real software. No experience needed.**

DumDum Skills is a Claude Code plugin that turns plain English into working software. You describe what you want, and DumDum walks you through building it — explaining everything along the way.

No coding knowledge required. No jargon. No assumptions about what you already know.

---

## The problem

Every AI coding tool assumes you're already a developer. They talk about "scaffolding" and "CI/CD pipelines" and "containerization." They expect you to know git, know what a framework is, know how to read an error message.

That locks out most people. The CEO with an idea for a tool. The teacher who wants a classroom app. The kid who wants to make a game. The retiree who wants to finally build that thing they've been thinking about for years.

DumDum Skills fixes that.

## How it works

DumDum gives you 22 skills — plain English commands that guide you through every part of building software:

**Think** — Shape your idea
```
/dumdum:idea              Tell me your idea, I'll help you shape it
/dumdum:who-is-it-for     Figure out who will use it
/dumdum:break-it-down     Split it into buildable pieces
```

**Plan** — Figure out the how
```
/dumdum:sketch-it         Describe what each screen looks like
/dumdum:pick-tools        Choose the right technology (explained simply)
/dumdum:steps             Make an ordered build plan
```

**Build** — Make it real
```
/dumdum:start-project     Set up a new project from scratch
/dumdum:add-feature       Add one feature at a time
/dumdum:fix-problem       Find and fix what's broken
/dumdum:make-it-look-good Improve the visual design
```

**Check** — Make sure it works
```
/dumdum:test-it           Run checks and report results
/dumdum:explain-it        Explain any file in plain English
/dumdum:review-it         Inspect the whole project for issues
```

**Ship** — Put it out there
```
/dumdum:save-progress     Save a checkpoint of your work
/dumdum:put-it-online     Deploy to the internet, step by step
/dumdum:tell-people       Generate a README and social post
```

**Learn** — Understand what's happening
```
/dumdum:whats-happening   Get a status report in plain English
/dumdum:teach-me          Learn any concept with analogies
/dumdum:glossary          Get a jargon-free dictionary for your project
```

**Manage** — Keep things organized
```
/dumdum:whats-left        See what's remaining as a checklist
/dumdum:clean-up          Remove unused code, organize files
/dumdum:take-notes        Save decisions and ideas to a journal
```

## What makes DumDum different

Most AI coding plugins are built by developers, for developers. DumDum is built for everyone else.

- **Plain English only.** If a technical term comes up, it gets explained right there, in the moment. You never need to Google something to keep up.
- **One question at a time.** DumDum doesn't dump a form on you. It asks simple questions, one at a time, and uses your answers to make smart decisions.
- **Teaches while it builds.** After every action, DumDum explains what it did and why. You learn by building, not by studying.
- **No prerequisites.** Each skill works on its own. You can start anywhere. You don't need to run them in order. Jump in wherever makes sense.
- **Real results.** This isn't a tutorial or a sandbox. DumDum builds real software that actually runs. Real files, real code, real websites.

## Install

You need [Claude Code](https://claude.ai/code) installed first.

```bash
# Clone this repo
git clone https://github.com/Superromz/DumDum-Skills.git

# Link it to Claude Code's plugin directory
ln -s "$(pwd)/DumDum-Skills/dumdum-skills" ~/.claude/plugins/dumdum-skills

# Restart Claude Code
```

## Get started

Open Claude Code in any directory and type:

```
/dumdum:idea
```

DumDum will ask you what you want to build. Go from there.

## Docs

Detailed documentation lives in [`dumdum-skills/docs/`](dumdum-skills/docs/):

- [**All Skills Reference**](dumdum-skills/docs/all-skills.md) — Every skill explained with example conversations
- [**Design Philosophy**](dumdum-skills/docs/philosophy.md) — The 8 principles behind DumDum
- [**Contributing**](dumdum-skills/docs/for-developers.md) — How to add new skills

## License

MIT
