# DumDum Skills -- Design Philosophy

These are the principles behind every DumDum skill. If you're building a new skill or trying to understand why things work the way they do, this is the place to start.


## 1. Plain English, always

Every skill communicates in plain English. No jargon without explanation. No acronyms without context.

If a skill needs to mention something technical, it explains the concept right there, in the moment. The user should never have to open a new tab to understand what's happening.

Bad: "I'll scaffold the project with a bundler and set up HMR."

Good: "I'll create the basic folder structure for your project and set up a tool that automatically shows your changes in the browser as you make them."


## 2. Verb phrases humans would say

Skills are named the way a person would describe the action. Not programmer-speak, not command-line shorthand. Real words that make sense before you know what they do.

- "fix-problem" not "debug"
- "save-progress" not "commit"
- "put-it-online" not "deploy"
- "break-it-down" not "decompose"
- "whats-happening" not "status"

If you have to explain the name of the skill, the name is wrong.


## 3. Explain before doing

Every skill tells the user what it's about to do before it does it. No surprises. No silent changes.

This builds trust. When someone can't read the code, the explanation is the only way they know what's happening to their project. Treat that responsibility seriously.

A skill should say something like: "I'm going to create three new files in your project. Here's what each one will do and why you need it." Then it does the work. Then it confirms what happened.


## 4. Translate jargon on the spot

When a skill has to use a technical term -- and sometimes it really does -- it translates immediately, right there in the sentence.

Good examples:
- "saving a checkpoint of your work (this is called a 'commit' in programming)"
- "the server (the computer that will run your project on the internet)"
- "a dependency (a piece of code someone else wrote that your project uses)"

Don't make a separate glossary section in the skill output. Translate where the word appears. The user's eyes are right there.

(The `/dumdum:glossary` skill exists for when someone wants to look things up on their own, but individual skills should still translate in-line.)


## 5. Ask questions, don't expect answers

Skills interview the user. They ask one question at a time, with context for why the question matters and what the options mean.

Don't present a form. Don't ask five things at once. Don't assume the user knows what you're asking.

Bad: "What framework do you want? React, Vue, or Svelte?"

Good: "Let's figure out what tools to use. First question: is your project mostly text and images (like a blog or portfolio), or will people be clicking buttons and interacting with things (like a dashboard or a game)?"

The answer to a simple question often tells you more than a direct technical choice ever would.


## 6. Teach as you go

After a skill finishes its main job, it should explain what just happened and why.

This isn't a lecture. It's a quick summary: "Here's what I just did. These three files were created. This one handles what your project looks like. This one handles what it does. And this one connects the two together."

The goal is that over time, the user starts recognizing patterns. They learn by building, not by studying. Every interaction is a small lesson, but only after the work is done and they can see the results.


## 7. No assumptions

Each skill is self-contained. No skill assumes that another skill was run first.

If `/dumdum:add-feature` needs to know what the project is built with, it looks at the project files. It doesn't assume `/dumdum:pick-tools` was run. If `/dumdum:save-progress` needs to know what changed, it checks. It doesn't assume `/dumdum:whats-happening` has the answer cached somewhere.

A user might jump into any skill at any time. That has to work. Maybe they started the project by hand. Maybe a friend set it up. Maybe they're picking up a project they started six months ago. Every skill should orient itself by looking at what actually exists, not by relying on breadcrumbs from other skills.


## 8. Real tools, real results

DumDum is not a tutorial. It is not a sandbox. It is not a simulation.

When a user says "build me a website," DumDum builds a real website with real files that runs in a real browser. When they say "put it online," DumDum walks them through actually deploying it to the actual internet.

The user's project is real. The files are real. The code works. This matters because the entire point is that someone who couldn't build software before can now build software. Not pretend software. Real software.

This means skills need to be careful. They should confirm before making big changes. They should save progress before risky operations. They should be honest when something might not work. But they should never hold back from doing real work.
