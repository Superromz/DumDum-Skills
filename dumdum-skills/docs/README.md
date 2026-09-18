# DumDum Skills

**AI building for humans.**

DumDum Skills is a plugin for Claude Code that helps anyone build real software using plain English. You don't need to know how to code. You don't need to know what a "framework" is or what "deploying" means. You just need an idea.

Tell DumDum what you want to build, and it will walk you through every step -- from shaping your idea to putting a finished project on the internet. Everything is explained in plain language, every decision is yours, and you end up with real, working software.


## Who is this for?

Literally anyone.

- A kid who wants to build a game
- A CEO who has an idea for an internal tool
- A teacher who wants a classroom app
- A hobbyist who wants a personal website
- A retired engineer who wants to try something new
- Someone who has never touched code in their life

If you can describe what you want in words, DumDum can help you build it.


## How to install

DumDum Skills is a Claude Code plugin. To install it:

1. Make sure you have Claude Code installed and working.
2. Copy or symlink the `dumdum-skills/` folder into your Claude Code plugins directory:

```bash
# Option A: Copy it
cp -r dumdum-skills/ ~/.claude/plugins/dumdum-skills

# Option B: Symlink it (recommended — updates automatically)
ln -s /path/to/dumdum-skills ~/.claude/plugins/dumdum-skills
```

3. Restart Claude Code. The skills will be available immediately.


## Quick start

Open Claude Code and type:

```
/dumdum:idea
```

That's it. DumDum will ask you about your idea and help you shape it into something buildable. From there, it will guide you through planning, building, checking, and shipping your project.


## All skills

DumDum Skills are organized into seven phases. You can use them in order or jump to whichever one you need.

### Think -- Shape your idea

| Command | What it does |
|---|---|
| `/dumdum:idea` | Tell DumDum your idea and it helps you shape it into something clear and buildable. |
| `/dumdum:who-is-it-for` | Figure out who will actually use your project and what they need from it. |
| `/dumdum:break-it-down` | Split your idea into small, buildable pieces ranked by importance. |

### Plan -- Get ready to build

| Command | What it does |
|---|---|
| `/dumdum:sketch-it` | Describe what each screen or page looks like in plain language. |
| `/dumdum:pick-tools` | Choose the right technology for your project, explained without jargon. |
| `/dumdum:steps` | Turn your feature list into an ordered build plan. |

### Build -- Make it real

| Command | What it does |
|---|---|
| `/dumdum:start-project` | Set up a new project from scratch and get something running. |
| `/dumdum:add-feature` | Add one new feature to your project, step by step. |
| `/dumdum:fix-problem` | Find and fix what's going wrong, explained in plain English. |
| `/dumdum:make-it-look-good` | Improve the visual design of your project. |

### Check -- Make sure it works

| Command | What it does |
|---|---|
| `/dumdum:test-it` | Check if your project works and report results in plain language. |
| `/dumdum:explain-it` | Point at any file and get a plain English explanation of what it does. |
| `/dumdum:review-it` | Look at your whole project for problems or missing pieces. |

### Ship -- Put it out there

| Command | What it does |
|---|---|
| `/dumdum:save-progress` | Save a checkpoint of your work with a clear description. |
| `/dumdum:put-it-online` | Walk through putting your project on the internet, step by step. |
| `/dumdum:tell-people` | Generate a README, description, and social post for sharing your project. |

### Learn -- Understand what's going on

| Command | What it does |
|---|---|
| `/dumdum:whats-happening` | Get a plain English summary of your project's current state. |
| `/dumdum:teach-me` | Learn any concept from your project using analogies and examples. |
| `/dumdum:glossary` | Get a jargon-free dictionary of every technical term in your project. |

### Manage -- Keep things tidy

| Command | What it does |
|---|---|
| `/dumdum:whats-left` | See remaining work as a simple checklist with priorities. |
| `/dumdum:clean-up` | Remove unused code and organize files, with explanations. |
| `/dumdum:take-notes` | Save a note about a decision, idea, or reminder into a project journal. |


## Learn more

- [Design Philosophy](philosophy.md) -- Why DumDum works the way it does.
- [All Skills Reference](all-skills.md) -- Detailed guide to every skill.
- [For Developers](for-developers.md) -- How to contribute new skills.
