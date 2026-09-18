# Idea: Shape a Raw Idea Into Something Buildable

**Command:** `/dumdum:idea`
**Phase:** Think

## What It Does and Why

Everyone starts with a spark. Maybe it is a frustration you have every day, a tool you wish existed, or something you scribbled on a napkin at lunch. The problem is that sparks are messy. They live in your head as feelings and fragments, not as something you could actually hand to someone and say "build this." That is where the idea skill comes in.

When you run `/dumdum:idea`, Claude becomes a curious friend who asks you simple questions about what you are imagining. It does not judge your answers or demand technical details. It just keeps asking until the fog clears and the shape of your idea starts to show. Think of it like talking to a friend who keeps saying "tell me more about that part" until you both understand what you mean.

The conversation is designed to move from the vague ("I want an app for dog owners") to the specific ("a neighborhood dog-walking scheduler where owners can post walks and join each other"). Claude will ask about the problem you are solving, who has that problem, what a finished version looks like, and what the simplest useful version could be. You do not need to have answers ready. Saying "I'm not sure" is completely fine, and Claude will help you figure it out.

This skill never writes code. It never opens a terminal. It never creates project files. Its only job is to help you think clearly. By the end, you will have a short, written summary of your idea that you can carry forward into every other skill.

The summary it produces becomes the foundation for everything else in DumDum. Other skills like who-is-it-for and break-it-down will read it automatically so you do not have to repeat yourself.

## Example Conversation

**You:** `/dumdum:idea`

**Claude:** Hey! You have an idea for something you want to build. Tell me about it in whatever way feels natural. A sentence, a paragraph, a ramble. There are no wrong answers here.

**You:** I want to make something that helps people in my apartment building share stuff. Like tools and kitchen things.

**Claude:** That is a cool idea. So people in your building have things they rarely use, and other people need those same things. Instead of everyone buying their own, they share. A few quick questions. Is this just your building, or could it work for any building?

**You:** Just mine for now. Maybe others later.

**Claude:** Makes sense. Start small and prove it works. When someone wants to borrow something, how does that happen today? Do people knock on doors, post in a group chat, something else?

**You:** We have a group chat but things get lost in the messages. Nobody can find anything.

**Claude:** So the main pain is that the group chat buries requests. You need a way to see what is available without scrolling through hundreds of messages. What would the dream version look like if you could wave a magic wand?

**You:** People list what they are willing to lend. Others browse and request to borrow. Maybe a simple calendar so two people do not need the same drill on the same weekend.

**Claude:** That is really clear now. Let me play it back. You want a simple lending library for your apartment building. Residents list items they will lend, others browse and request them, and there is some kind of calendar to avoid conflicts. The first version is just for your building. Does that sound right?

**You:** Yeah, exactly. Maybe also a way to say thanks or rate people so everyone stays honest.

**Claude:** Good addition. A trust layer. I have a clear picture now. Let me write up your idea summary.

**Claude:** Done. I saved your idea summary to `idea-summary.md`. It includes the name, a one-paragraph description, the core features (item listing, browse and request, availability calendar, trust ratings), and the scope (single building first, expand later). You can open that file anytime to review or edit it.

## What It Produces

The skill creates a file called `idea-summary.md` in your project directory. The file contains:

- **Name:** A short, descriptive name for your project (2-5 words).
- **One-line description:** A single sentence explaining what it does and for whom.
- **Problem statement:** What pain or gap this idea addresses, written in plain language.
- **Core features:** A bulleted list of the main things the product does, typically 3-7 items.
- **Scope:** What is included in the first version and what is explicitly saved for later.
- **Open questions:** Anything that came up during the conversation that still needs an answer.

This file is plain text. You can edit it by hand, share it with friends for feedback, or just leave it for the next skill to pick up automatically.

## Tips and Common Questions

- **You can be as vague as you want.** Saying "I want to make something with recipes" is a perfectly fine starting point. Claude will ask questions to fill in the gaps.
- **This works best at the very start.** If you already have a detailed plan, you might want to skip ahead to break-it-down or steps. But if you are still fuzzy, start here.
- **It does not write any code.** The idea skill is purely a thinking exercise. No files are created except the idea summary.
- **You can run it more than once.** If your idea changes after a few days, just run it again. The new summary will replace the old one.
- **Short conversations are fine.** If your idea is already pretty clear, the conversation might only take 3-4 exchanges. There is no minimum length.

## Related Skills

- `/dumdum:who-is-it-for` : After you know what you are building, figure out who will use it and what they care about.
- `/dumdum:break-it-down` : Take your idea and split it into buildable pieces ranked by importance.
- `/dumdum:pick-tools` : Choose the right technologies for your project with plain-English explanations.
