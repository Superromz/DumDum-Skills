# Break It Down: Split Your Idea Into Buildable Pieces

**Command:** `/dumdum:break-it-down`
**Phase:** Think

## What It Does and Why

Big ideas are exciting, but they are also paralyzing. When your project feels like one massive thing, it is hard to know where to start. The break-it-down skill takes your idea and splits it into small, concrete pieces, then ranks them so you know what to build first, what to build later, and what to skip for now.

When you run `/dumdum:break-it-down`, Claude looks at your idea (from `idea-summary.md` if it exists, or by asking you directly) and starts identifying the individual pieces that make it work. Each piece is something specific and buildable: "user login," "item search," "notification when someone borrows your stuff." These are not vague categories. They are things you could point to and say "that is done" or "that is not done yet."

Once the pieces are listed, Claude helps you sort them into three buckets. Must Have pieces are the ones without which your product does not work at all. Should Have pieces make it noticeably better but are not required for launch. Nice to Have pieces are the extras, the polish, the "wouldn't it be cool if" features. This sorting is critical because it protects you from the most common trap in building software: trying to do everything at once and finishing nothing.

The skill does not write any code. It does not set up files or projects. It is a thinking tool that produces a checklist you can carry into the building phase. That checklist becomes your source of truth when you are tempted to add just one more thing before launching.

If you have already run the idea skill or the who-is-it-for skill, Claude will use that context automatically. But it works perfectly fine on its own too. You can describe your idea from scratch and Claude will walk you through the breakdown.

## Example Conversation

**You:** `/dumdum:break-it-down`

**Claude:** I found your idea summary for "Building Lending Library." Let me help you break this into pieces. Looking at your core features, I see item listing, browse and request, availability calendar, and trust ratings. Let me start by asking: if someone opened this app for the first time, what is the absolute minimum they would need to do something useful?

**You:** They would need to see what is available to borrow and be able to ask for it.

**Claude:** Good. So browsing items and requesting to borrow are at the core. For browsing to work, someone else needs to have listed items first. So we have three connected pieces: listing an item, browsing items, and requesting a borrow. Anything else that is absolutely essential?

**You:** They need to know who they are. Like, some kind of login so people know it is their neighbor and not a stranger.

**Claude:** Right, identity. A simple sign-up and login so each person is a known resident. That makes four Must Have pieces so far. Now, what about the availability calendar you mentioned? Is the app useless without it, or could people manage with a simpler approach at first?

**You:** I guess at first they could just message each other about timing. The calendar would be nice but is not critical on day one.

**Claude:** That is a great call. The calendar moves to Should Have. What about the trust ratings?

**You:** Same thing. Nice to have but people in the building already know each other, so trust is less of an issue at first.

**Claude:** Smart. Let me also ask about a few pieces you might not have thought of. What about notifications? Like, telling Dave that someone wants his drill.

**You:** Oh yeah, that is important. Without notifications Dave would never know someone asked.

**Claude:** Agreed, notifications go in Must Have. What about a way for the lender to say "yes, you can have it" or "sorry, it is already out"?

**You:** Definitely needed. Approve or decline a request.

**Claude:** Good. I have a solid picture now. Let me put the checklist together.

**Claude:** Done. I saved the build checklist to `build-checklist.md`. Here is the summary: Must Have (6 pieces): sign-up and login, list an item, browse items, request to borrow, approve or decline requests, notifications. Should Have (3 pieces): availability calendar, return tracking, search and filter. Nice to Have (3 pieces): trust ratings, item photos, building-wide announcements.

## What It Produces

The skill creates a file called `build-checklist.md` in your project directory. The file contains:

- **Must Have:** The pieces without which the product does not function. These form your first version. Each piece has a short name, a one-sentence description of what it does, and a note about why it is essential.
- **Should Have:** The pieces that make the product significantly better. These are your second round of work after the first version is live. Each piece includes what it adds and why it is not in Must Have.
- **Nice to Have:** The pieces that add polish, delight, or advanced functionality. These are saved for later and might not get built at all, and that is fine. Each piece includes what it would add and why it can wait.

The checklist is intentionally short. Each piece is described in one or two sentences, not paragraphs. The goal is a scannable list you can check off as you build, not a detailed specification.

## Tips and Common Questions

- **Aim for 5-10 pieces in Must Have.** Fewer than 5 and your first version might not do enough to be useful. More than 10 and you are probably including things that could wait.
- **It works with or without prior context files.** If you ran the idea or who-is-it-for skills first, Claude reads those files and uses them. If you did not, Claude will ask about your idea before breaking it down.
- **This skill does not write code.** It is purely a planning exercise. The checklist it produces is a text file, not a project setup.
- **When in doubt, push it to Should Have.** It is much easier to promote a feature from Should Have to Must Have later than to cut a feature after you have already built it.
- **You can rerun it anytime.** As your understanding of the project evolves, run break-it-down again to re-sort your priorities.

## Related Skills

- `/dumdum:steps` : Take your prioritized pieces and turn them into an ordered build plan with milestones.
- `/dumdum:start-project` : Once you know what to build first, create the actual project files and folder structure.
- `/dumdum:idea` : If you have not clarified your idea yet, start here before breaking it down.
