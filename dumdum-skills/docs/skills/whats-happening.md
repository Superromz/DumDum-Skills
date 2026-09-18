# What's Happening (`/dumdum:whats-happening`)

**Phase:** Learn

## What It Does

What's Happening explores your entire project and delivers a conversational status report. It tells you what has been built, what is currently in progress, what is broken, what technologies are being used, and what changed recently. Think of it as asking a knowledgeable friend to look through your project and give you the full picture.

This skill is especially useful when you are returning to a project after a break. Maybe you stepped away for a few days, a few weeks, or even a few months. You know you were building something, but the details are fuzzy. Instead of clicking through files and trying to piece together where you left off, you run this skill and get a clear summary in plain English.

The skill does not make any changes to your project. It is completely read-only. It looks at your files, your code, your configuration, and your git history (if available) to build a comprehensive picture. It checks for error indicators like failing tests, missing dependencies, or syntax errors, and flags those in the report. But it never modifies, fixes, or deletes anything on its own.

The report is organized into clear sections so you can scan it quickly or read it in detail. Each section covers a different aspect of your project's current state. If something needs attention, the skill will say so and suggest which other skills can help.

Beyond returning from a break, this skill is also useful when you are about to start a new feature or when someone else asks about the project. It gives you the confidence to know exactly where things stand before making decisions about what to do next.

## Example Conversation

**User:** `/dumdum:whats-happening`

**Claude:** Let me explore your project. I will look at every file, check for any issues, and review your recent history. This might take a moment.

**Claude:** Here is your project status report:

**Project:** Recipe Finder App
**Tech stack:** React (frontend), Express.js (backend), SQLite (database)
**Total files:** 34 files across 8 folders

**What is built and working:**
- Homepage with search bar and featured recipes
- Recipe detail page with ingredients and instructions
- Backend API with endpoints for searching and filtering
- Database with 150 sample recipes loaded

**What is in progress:**
- A "favorites" feature appears to be partially built. There is a `Favorites.jsx` component with some placeholder text, and the backend has a `/api/favorites` route that is stubbed out but not connected to the database yet.

**What is broken:**
- The file `src/components/FilterPanel.jsx` has a syntax error on line 42. It looks like a missing closing parenthesis. This might cause the filter feature to crash when used.

**Recent changes (from git history):**
- 3 days ago: "added favorites page skeleton"
- 4 days ago: "recipe detail page done"
- 5 days ago: "search API working"

**User:** Oh right, I was working on favorites. What exactly did I get done on that?

**Claude:** I looked at the favorites feature in more detail. Here is what exists so far:

The frontend component `Favorites.jsx` has the page layout with a heading that says "My Favorites" and an empty list container. It imports a `useFavorites` hook from `hooks/useFavorites.js`, but that hook file does not exist yet, which would cause an error if you navigated to this page.

On the backend, the route `/api/favorites` exists in `routes/favorites.js` with three endpoints defined: GET (list all), POST (add one), and DELETE (remove one). The GET endpoint returns an empty array as a placeholder. The POST and DELETE endpoints return "not implemented" responses.

The database does not have a favorites table yet.

**User:** Got it. And what about that syntax error you mentioned?

**Claude:** In `src/components/FilterPanel.jsx` on line 42, there is a `.filter(` call that is missing its closing `)`. It looks like you were writing a filter function and might have gotten interrupted. The line currently reads:

`const filtered = recipes.filter(r => r.cuisine === selectedCuisine`

It is missing the closing `)` and `;` at the end. That is a quick fix whenever you are ready.

**User:** Thanks. I will fix that first.

**Claude:** Good plan. You can use `/dumdum:fix-problem` if you want help with that, or just add the missing `)` yourself. After that, `/dumdum:add-feature` can help you finish the favorites feature where you left off.

## What It Produces

- **A project status report** written in plain English, covering the following sections:
  - **Project identity:** Name, type, and technology stack.
  - **What is built:** Features and pages that are complete and functional.
  - **What is in progress:** Partially built features, stubbed-out code, and placeholder content.
  - **What is broken:** Syntax errors, missing files, failing imports, or other issues that would cause problems.
  - **Tech inventory:** Languages, frameworks, libraries, and tools the project uses.
  - **Recent changes:** A summary of the last several git commits (if git history is available), showing what was worked on and when.

## Tips and Common Questions

1. **Great for returning after a break.** If you have not touched your project in a while, this is the first skill to run. It catches you up on everything without you having to dig through files yourself.

2. **It is completely read-only.** This skill never changes, fixes, or deletes anything. It only looks and reports. You are always in control of what happens next.

3. **Git history makes it better.** If your project has git saves (from `/dumdum:save-progress` or manual git usage), the report includes a timeline of recent changes. Without git, it still works but cannot show the history section.

4. **Use it before making decisions.** Before starting a new feature or deciding what to work on next, run this skill to make sure you understand the current state. It might reveal something you forgot about.

## Related Skills

- `/dumdum:whats-left` - After learning what is happening, use this skill to see a prioritized checklist of what still needs to be done.
- `/dumdum:add-feature` - Once you know the project's state, use this skill to start building the next feature.
- `/dumdum:fix-problem` - If the status report reveals something broken, use this skill to fix it.
