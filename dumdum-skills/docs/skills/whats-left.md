# What's Left (`/dumdum:whats-left`)

**Phase:** Manage

## What It Does

What's Left finds every plan, checklist, and TODO in your project, checks each item against the actual code to see if it has been done, and builds a prioritized list of what still needs to happen. It organizes tasks into three buckets: "Do these first" (critical or blocking items), "Do these next" (important but not urgent), and "Do these whenever" (nice-to-have improvements). It also calculates a progress percentage so you can see how far along you are.

When you are in the middle of building something, it is easy to lose track of what you planned to do versus what you have actually finished. You might have written a checklist at the start, sprinkled TODO comments throughout your code, or made mental notes that you have since forgotten. This skill gathers all of those scattered plans into one place and cross-references them with reality.

The skill looks in several places for plans and tasks. It checks for `build-checklist.md` or similar planning documents. It scans every file for TODO, FIXME, HACK, and XXX comments. It looks at your project structure for stub files or placeholder content. It even checks for partially implemented features, like a route that exists but returns "not implemented." Everything gets consolidated into a single prioritized view.

Prioritization is based on what would have the most impact or what is blocking other work. If your app crashes because of a missing database table, that goes in "Do these first." If you have a working feature that just needs better styling, that goes in "Do these whenever." The skill explains its reasoning for each prioritization so you can rearrange if you disagree.

This skill is read-only. It does not create, modify, or delete any files. It reports on the state of things and lets you decide what to do next. After reviewing the list, you might use `/dumdum:add-feature` to tackle the top item or `/dumdum:clean-up` to handle some of the lower-priority tasks.

## Example Conversation

**User:** `/dumdum:whats-left`

**Claude:** Let me look through your project for plans, TODOs, and unfinished work. I will check your planning documents, scan for TODO comments, and look at the code to see what has actually been completed.

**Claude:** I found your `build-checklist.md` file with 12 items, plus 8 TODO comments scattered across 5 files. After checking each one against the actual code, here is where things stand:

**Overall progress: 58% complete** (11 of 19 items done)

---

**Do these first** (3 items):

1. **Connect the favorites API to the database.** Your `/api/favorites` routes exist but return placeholder responses. The favorites page on the frontend tries to call these routes and gets empty data back. This is blocking the favorites feature from working at all.
   *Source: build-checklist.md item 8, also TODO in server/routes/favorites.js line 14*

2. **Fix the filter panel syntax error.** There is a missing closing parenthesis in `FilterPanel.jsx` line 42 that will crash the filter feature. This is a quick fix but it blocks anyone from using filters.
   *Source: detected by code scan*

3. **Create the favorites database table.** The migration file `003-favorites.sql` exists but has not been run. Without this table, the favorites API has nowhere to store data.
   *Source: TODO in server/db/migrations/003-favorites.sql line 1*

---

**Do these next** (4 items):

4. **Add error handling to API calls.** Several `fetch()` calls in the frontend do not handle failure cases. If the server is down or returns an error, the user sees a blank page instead of a helpful message.
   *Source: TODO in src/services/api.js lines 8, 15, 22*

5. **Add loading spinners.** Three pages (search results, recipe detail, favorites) show no indication while data is being fetched. Users might think the page is broken during slow connections.
   *Source: build-checklist.md item 10*

6. **Write the "about" page content.** The about page exists but still has placeholder text ("Lorem ipsum").
   *Source: build-checklist.md item 11*

7. **Add recipe images.** Recipe cards show a gray placeholder instead of actual food photos. The database has an `image_url` column but it is empty for most recipes.
   *Source: build-checklist.md item 7*

---

**Do these whenever** (2 items):

8. **Improve mobile styling.** The app works on mobile but some elements overlap on small screens. Not broken, just not polished.
   *Source: build-checklist.md item 12*

9. **Refactor duplicate API call logic.** Three different files have nearly identical fetch code that could be consolidated into a shared function. This does not affect functionality but would make future changes easier.
   *Source: TODO in src/pages/SearchResults.jsx line 3*

---

**Already done** (11 items): Homepage, search functionality, recipe detail page, navigation, database setup, recipe seeding, search API, recipe API, basic styling, footer, and responsive header.

**User:** Can I knock out that syntax error right now? That seems quick.

**Claude:** Absolutely. The fix is just adding a closing `)` to line 42 of `FilterPanel.jsx`. You can use `/dumdum:fix-problem` to handle it, or just open the file and add the parenthesis yourself. After that, your progress jumps to 63%.

**User:** And what should I focus on after that?

**Claude:** The favorites feature is your biggest unfinished piece. Items 1 and 3 from the list are both about favorites, and together they represent the core of that feature. I would suggest running the database migration first (item 3), then connecting the API routes to the database (item 1). After that, the favorites feature should work end to end.

**User:** That makes sense. Thanks.

**Claude:** You are welcome. Run `/dumdum:whats-left` again after you finish those tasks and I will update the progress tracker. Nice work getting to 58% so far.

## What It Produces

- **A progress percentage** showing how many planned items are complete versus remaining, giving you an at-a-glance sense of how far along the project is.
- **A prioritized checklist** organized into three sections:
  - **Do these first:** Critical items that are blocking other work or causing errors.
  - **Do these next:** Important items that will add real value but are not blocking anything.
  - **Do these whenever:** Nice-to-have improvements that can wait.
- **Source citations** for each item, showing where the task was originally defined (planning document, TODO comment, or detected by code scan).
- **A "done" summary** listing everything that has been completed, so you can appreciate the progress you have already made.

## Tips and Common Questions

1. **It is completely read-only.** This skill does not create, edit, or delete any files. It only reads your project and reports on what it finds. You decide what to act on.

2. **It checks planning documents and code comments.** The skill looks for files like `build-checklist.md`, `TODO.md`, and `ROADMAP.md`. It also scans every source file for TODO, FIXME, HACK, and XXX comments. Everything gets consolidated into one list.

3. **Celebrate your progress.** The skill intentionally highlights what you have already finished, not just what remains. Building software is hard, and seeing "11 of 19 items done" is motivating.

4. **You can disagree with the prioritization.** The skill explains why it ranked each item where it did, but you know your project best. If something in "Do these whenever" is actually important to you, go ahead and tackle it first.

5. **Run it regularly.** As you complete tasks, run this skill again to see your progress percentage climb and your "Do these first" list shrink. It is a satisfying feedback loop.

## Related Skills

- `/dumdum:add-feature` - Once you have identified the top priority from the checklist, use this skill to build it out step by step.
- `/dumdum:clean-up` - Items in the "Do these whenever" section are often cleanup tasks. Use this skill to handle them efficiently when you are ready.
