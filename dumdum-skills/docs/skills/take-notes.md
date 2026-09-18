# Take Notes (`/dumdum:take-notes`)

**Phase:** Manage

## What It Does

Take Notes captures decisions, ideas, reminders, and learnings into a project journal file called `NOTES.md`. Every entry is timestamped and categorized so you can look back later and understand not just what you built, but why you built it that way. It is your project's memory, written in your own words.

When you are building something, you make dozens of small decisions every day. "I used SQLite instead of PostgreSQL because it is simpler to set up." "I decided to put all API routes in one file for now." "I learned that React re-renders every time state changes." These decisions and learnings feel obvious in the moment, but they fade quickly. A week later, you might look at your code and wonder why you did it that way. A month later, you might not remember the decision at all.

This skill solves that problem by making it effortless to write things down. You can pass the note directly with the command, like `/dumdum:take-notes I decided to use Tailwind instead of plain CSS because the utility classes are faster to write`. The skill formats the note, adds a date, assigns a category, and appends it to your journal. It takes about five seconds, and your future self will thank you.

The journal file is append-only. The skill never edits or deletes existing notes. Each entry is preserved exactly as you wrote it, creating a chronological record of your project's evolution. If you make a decision that contradicts an earlier one, both are kept. That history of changing your mind is valuable, because it shows your thinking process.

Once your journal reaches ten or more notes, the skill offers to organize them by category. This creates a table of contents at the top of the file so you can quickly find all your decisions, all your ideas, or all your reminders without scrolling through everything.

## Example Conversation

**User:** `/dumdum:take-notes` I chose to store recipes in SQLite because I do not want to set up a separate database server.

**Claude:** Got it. I will save that as a Decision. Here is the entry:

---
**2026-09-19 | Decision**
I chose to store recipes in SQLite because I do not want to set up a separate database server.

---

This has been added to `NOTES.md` in your project root. You now have 1 note in your journal.

**User:** `/dumdum:take-notes`

**Claude:** What would you like to capture? It can be a decision you made, an idea you had, something you want to remember, or something you learned.

**User:** I just realized that fetch does not throw an error for 404 responses. You have to check response.ok manually. That tripped me up for an hour.

**Claude:** That is a good one to remember. I will save that as a Learning:

---
**2026-09-19 | Learning**
The `fetch` function does not throw an error for 404 responses. You have to check `response.ok` manually. This caused confusion for about an hour before I figured it out.

---

Added to `NOTES.md`. You now have 2 notes.

**User:** Oh, I also want to remember to add pagination to the search results eventually. Not now, but later.

**Claude:** Saving that as a Reminder:

---
**2026-09-19 | Reminder**
Add pagination to the search results page. Not urgent, but will be needed once the recipe database grows.

---

Added to `NOTES.md`. You now have 3 notes.

**User:** Here is an idea. What if the app could suggest recipes based on what is about to expire in your fridge?

**Claude:** I love that. Saving as an Idea:

---
**2026-09-19 | Idea**
The app could suggest recipes based on ingredients that are about to expire in your fridge. This would help reduce food waste and add a unique feature that most recipe apps do not have.

---

Added to `NOTES.md`. You now have 4 notes.

**User:** Can I see all my notes?

**Claude:** Here is your complete journal so far:

**NOTES.md** (4 entries)

1. **2026-09-19 | Decision** - I chose to store recipes in SQLite because I do not want to set up a separate database server.

2. **2026-09-19 | Learning** - The `fetch` function does not throw an error for 404 responses. You have to check `response.ok` manually. This caused confusion for about an hour before I figured it out.

3. **2026-09-19 | Reminder** - Add pagination to the search results page. Not urgent, but will be needed once the recipe database grows.

4. **2026-09-19 | Idea** - The app could suggest recipes based on ingredients that are about to expire in your fridge. This would help reduce food waste and add a unique feature that most recipe apps do not have.

When you reach 10 notes, I will offer to add a table of contents organized by category so they are easier to browse.

**User:** That is really handy. I wish I had been doing this from the start.

**Claude:** It is never too late to start. You can also go back and add notes about past decisions anytime. Just run the command and write something like "Earlier in the project, I decided to use React instead of plain HTML because I wanted to learn a framework." The date will show today, but the note itself captures the history.

## What It Produces

- **A formatted journal entry** containing:
  - **Date:** The current date in YYYY-MM-DD format.
  - **Category:** One of five types: Decision (a choice you made and why), Idea (something you might want to build or try), Reminder (something to come back to later), Learning (something you figured out or discovered), or Other (anything that does not fit the categories above).
  - **Note text:** Your words, lightly cleaned up for formatting but never rewritten or editorialized.
- **An append to `NOTES.md`** in the project root. The file is created automatically if it does not exist yet.
- **A table of contents** (offered after 10+ notes) that groups entries by category for easier browsing.

## Tips and Common Questions

1. **You can pass the note inline with the command.** Instead of running `/dumdum:take-notes` and waiting for a prompt, type the entire note after the command: `/dumdum:take-notes I decided to use CSS Grid for the layout because it handles two-dimensional layouts better than Flexbox`. The skill will categorize and save it immediately.

2. **Existing notes are never edited or deleted.** The journal is append-only. Even if you change your mind about a past decision, both the original note and the new one are preserved. This gives you a complete history of your thinking.

3. **The skill offers to organize after 10+ notes.** Once your journal reaches ten entries, the skill will suggest adding a table of contents grouped by category (all Decisions together, all Ideas together, etc.). You can accept or decline.

4. **Categories are assigned automatically.** You do not need to specify whether your note is a Decision, Idea, Reminder, or Learning. The skill reads your note and picks the best category. If it gets it wrong, just say so and it will recategorize.

5. **Notes are for you, not for others.** The journal is written in your voice, for your future reference. It does not need to be polished or professional. Quick, honest notes are the most useful kind.

## Related Skills

- `/dumdum:whats-left` - Your Reminders and Ideas in the journal often overlap with your project's TODO list. Use this skill to see a consolidated view of everything that still needs doing.
- `/dumdum:save-progress` - After adding important notes (especially Decisions), save your progress so the journal entries are included in your checkpoint.
