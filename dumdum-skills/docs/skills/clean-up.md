# Clean Up (`/dumdum:clean-up`)

**Phase:** Manage

## What It Does

Clean Up scans your project for unused files, dead code, duplicate logic, debugging leftovers, and messy organization. It produces a numbered list of cleanup opportunities, then walks through each one with you. Nothing is changed until you give explicit approval. After the cleanup is done, it shows a summary of everything that was removed or simplified.

Every project accumulates clutter over time. You try something, it does not work, but you leave the file around "just in case." You copy and paste a function into three different files instead of sharing it. You sprinkle `console.log` statements everywhere while debugging and forget to remove them. You create a component, rename it, but leave the old version sitting in the folder. None of this is harmful on its own, but it adds up. Eventually your project feels heavier and harder to navigate than it needs to be.

This skill finds all of that clutter without you having to look for it manually. It checks for files that are not imported or referenced anywhere, functions that are defined but never called, variables that are assigned but never used, `console.log` and `debugger` statements left over from development, commented-out blocks of code, duplicate logic across multiple files, and empty or placeholder files that were never filled in.

The key principle is safety. The skill never deletes a file, removes a function, or simplifies code without showing you exactly what it plans to do and getting your approval. For code simplification, it shows a before-and-after comparison so you can see the change clearly. If you are not sure about a particular cleanup, you can skip it and move on to the next one.

The skill also never changes how your project works. It only removes things that are not being used or simplifies things that are unnecessarily complex. After a cleanup session, your project should behave exactly the same as before, just with less clutter.

## Example Conversation

**User:** `/dumdum:clean-up`

**Claude:** Let me scan your project for things that can be cleaned up. I will look for unused files, dead code, debugging leftovers, duplicates, and disorganization.

**Claude:** I found 11 cleanup opportunities. Here they are, organized by type:

**Unused files (3):**
1. `src/components/OldHeader.jsx` - This component is not imported anywhere. It looks like a previous version of your header before you created `Header.jsx`.
2. `src/utils/helpers.js` - This file has 4 functions, but none of them are imported by any other file.
3. `server/test-endpoint.js` - This appears to be a one-off test script that is not part of the main application.

**Debugging leftovers (3):**
4. `src/pages/SearchResults.jsx` lines 15, 23, 31 - Three `console.log` statements that print search data to the browser console.
5. `src/components/RecipeCard.jsx` line 8 - A `console.log` that prints "rendering card" every time a recipe card appears.
6. `server/routes/recipes.js` line 22 - A `console.log` that prints every search query to the server terminal.

**Commented-out code (2):**
7. `src/App.jsx` lines 45-62 - A block of commented-out JSX that looks like an old navigation bar.
8. `server/index.js` lines 30-38 - A commented-out middleware function with a note that says "try this later."

**Duplicate logic (2):**
9. Three files (`SearchResults.jsx`, `RecipeDetail.jsx`, `Favorites.jsx`) each have nearly identical error-handling fetch wrappers. These could be consolidated into one shared function.
10. `src/components/RecipeCard.jsx` and `src/components/FeaturedCard.jsx` share about 80% of their code. They could potentially be merged into one component with a `featured` prop.

**Empty file (1):**
11. `src/hooks/useFavorites.js` - This file was created but contains only a comment that says "TODO: implement."

Which items would you like me to clean up? You can pick specific numbers, say "all," or say "skip" for any you want to keep.

**User:** Do items 1 through 6 but skip 2. I might need those helper functions later.

**Claude:** Got it. I will handle items 1, 3, 4, 5, and 6. Skipping item 2 (helpers.js).

Starting with item 1: deleting `src/components/OldHeader.jsx`. This file defines an `OldHeader` component that is not used anywhere in the project. Can I go ahead?

**User:** Yes.

**Claude:** Deleted. Moving to item 3: deleting `server/test-endpoint.js`. This is a standalone script that tests the recipe search endpoint manually. It is not connected to the app. Can I remove it?

**User:** Go ahead.

**Claude:** Done. Now items 4, 5, and 6: removing `console.log` statements. Here is what I will remove:

- `SearchResults.jsx` line 15: `console.log('Search query:', query)`
- `SearchResults.jsx` line 23: `console.log('Results:', data)`
- `SearchResults.jsx` line 31: `console.log('Filtered:', filtered)`
- `RecipeCard.jsx` line 8: `console.log('rendering card', recipe.id)`
- `recipes.js` line 22: `console.log('Searching for:', req.query.q)`

None of these affect how the app works. They only print messages to the console that you were using for debugging. Can I remove all five?

**User:** Yes, remove them all.

**Claude:** All done. Here is your cleanup summary:

**Removed:**
- 2 unused files deleted (OldHeader.jsx, test-endpoint.js)
- 5 console.log statements removed across 3 files

**Skipped:**
- helpers.js (kept at your request)

**Still available to clean up later:**
- 2 blocks of commented-out code (items 7-8)
- 2 duplicate logic opportunities (items 9-10)
- 1 empty file (item 11)

Your project has 2 fewer files and no more debugging noise in the console. Everything still works exactly the same as before.

**User:** Nice. Can you show me what the duplicate fix would look like for item 9?

**Claude:** Sure. Here is the before-and-after for consolidating the fetch wrappers.

**Before (repeated in 3 files):**
```javascript
const response = await fetch(url);
if (!response.ok) {
    console.error('Request failed');
    return null;
}
const data = await response.json();
```

**After (one shared function in `src/services/api.js`):**
```javascript
export async function fetchData(url) {
    const response = await fetch(url);
    if (!response.ok) {
        throw new Error('Request to ' + url + ' failed with status ' + response.status);
    }
    return response.json();
}
```

Then each of the three files would import and call `fetchData(url)` instead of repeating the logic. Want me to make this change?

## What It Produces

- **A numbered list of cleanup opportunities** organized by type (unused files, dead code, debugging leftovers, commented-out code, duplicate logic, empty files, and disorganization).
- **Before-and-after comparisons** for any code simplification, so you can see exactly what will change.
- **Individual approval prompts** for each cleanup action, ensuring nothing is removed without your explicit permission.
- **A cleanup summary** at the end listing everything that was removed, everything that was skipped, and everything still available to clean up later.

## Tips and Common Questions

1. **Nothing is ever deleted without your permission.** Every single cleanup action requires your explicit approval. You can skip any item, and the skill will move on without complaint.

2. **It never changes how your project works.** Cleanup only removes things that are not being used or simplifies things without altering behavior. Your project should work exactly the same after cleanup as it did before.

3. **Before-and-after comparisons are shown for code changes.** When the skill suggests simplifying or consolidating code, it shows you the current version and the proposed version side by side so you can evaluate the change.

4. **You can do partial cleanups.** You do not have to address everything in one session. Pick the items you are comfortable with and leave the rest for later. The skill does not pressure you to clean up everything at once.

5. **Save your progress first.** It is a good idea to run `/dumdum:save-progress` before a cleanup session. That way, if you change your mind about a deletion, you can restore from the save point.

## Related Skills

- `/dumdum:save-progress` - Save a checkpoint before cleaning up, so you can restore if needed. Also save after cleanup to lock in the tidier state.
- `/dumdum:test-it` - After cleanup, run your tests to confirm nothing was accidentally broken. The skill only removes unused code, but verification never hurts.
