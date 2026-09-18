# Add Feature - `/dumdum:add-feature`

**Phase:** Build

## What It Does and Why

Once you have a working project, the next step is making it do more. Add Feature is your tool for building one new capability at a time. The key word is "one." Trying to add five things at once is how projects break. This skill enforces a disciplined approach: describe what you want, get a plan, watch it get built, and verify it works before moving on.

You describe the feature however makes sense to you. "I want users to be able to leave reviews" is just as valid as "add a dark mode toggle." Claude takes your plain-English description, figures out which files need to change, and creates a step-by-step plan before writing any code. You approve the plan first, so there are no surprises.

If your request is too big for a single feature, Claude will tell you and break it down into smaller pieces. For example, "add a full shopping cart with payments and order tracking" might become three separate features: a cart, a payment system, and an order tracker. Each one gets built and verified independently. This way, if something goes wrong, you know exactly where the problem is.

After the feature is built, Claude runs through a quick check to make sure everything still works. New features sometimes break existing ones, like adding a new room to a house and accidentally blocking a hallway. Claude catches these issues before you even notice them.

Every change comes with a summary explaining what was added, which files were modified, and why each change was necessary. You never have to wonder "what just happened to my project."

## Example Conversation

**You:** `/dumdum:add-feature`

**Claude:** What feature would you like to add? Describe it in whatever way feels natural.

**You:** I want people to be able to search for items on the menu.

**Claude:** A search feature for the menu. Let me look at your current project to understand how the menu is set up. One moment.

Okay, I see your menu is displayed on `index.html` with items stored in `app.js`. Here is my plan for adding search:

1. Add a search bar at the top of the menu page
2. As the user types, filter the menu items to show only matches
3. Search will check both item names and descriptions
4. Show a "no results found" message when nothing matches
5. A small "clear search" button to reset the view

This will change two files: `index.html` (for the search bar) and `app.js` (for the filtering logic). Nothing else needs to change. Does this plan look good?

**You:** Yes, but can it also search by ingredient? Like if I type "chocolate" it shows everything with chocolate.

**Claude:** Great idea. I will add ingredient matching too. That means each menu item will need an ingredients list. I will add that to your existing items and you can fill in the real ingredients later. Updated plan:

1. Add an ingredients field to each menu item in `app.js`
2. Add a search bar at the top of the menu page
3. Search checks item names, descriptions, and ingredients
4. Results filter in real time as the user types
5. Matching ingredients get highlighted so users can see why an item appeared
6. "No results" message and "clear search" button included

Still just two files changing. Sound good?

**You:** Perfect, do it.

**Claude:** Done. Here is what I changed:

- `index.html` - Added a search bar with placeholder text "Search by name, description, or ingredient..."
- `app.js` - Added ingredient arrays to each menu item. Added search filtering that checks all three fields. Added highlight logic for matching ingredients.

Try it out: open your site, type "chocolate" in the search bar, and you should see only items that mention chocolate. The word "chocolate" will be highlighted in the ingredients list. Try clearing the search to see all items again. Everything working?

**You:** It works. But the search bar looks kind of plain.

**Claude:** That is a styling issue. You can run `/dumdum:make-it-look-good` and tell it to focus on the search bar, or I can do a quick style pass right now. Your call.

**You:** Do a quick pass now.

**Claude:** Done. I gave the search bar rounded corners, a subtle shadow, and a small magnifying glass icon. It now matches the style of the rest of your site. Refresh the page to see the changes.

## What It Produces

- **A working feature.** The new capability is fully functional and integrated with the existing project.
- **A change summary.** A clear list of every file that was modified or created, with explanations of what changed and why.
- **Verification.** Claude checks that existing features still work after the new one is added, catching any unintended side effects.
- **Updated project context.** The new feature is accounted for in future skill invocations, so Claude always knows the current state of your project.

## Tips and Common Questions

1. **Describe features however you want.** "Make it so people can log in" works just as well as a detailed specification. Claude will ask follow-up questions if it needs more detail.

2. **Big requests get broken down automatically.** If you ask for something complex, Claude will split it into manageable pieces and build them one at a time. This keeps your project stable and makes problems easier to find.

3. **One feature at a time is the rule.** It might feel slow, but building incrementally means you always have a working project. Adding three features at once and having all of them break is much slower than doing them one by one.

4. **You can be vague about the details.** Saying "add a way for users to save their favorites" is enough. Claude will figure out the implementation details and explain them to you before writing any code.

5. **Check before you move on.** After each feature, take a moment to test it. If something is not right, it is much easier to fix now than after three more features have been added on top of it.

## Related Skills

- `/dumdum:test-it` - Run a thorough check on your project after adding new features.
- `/dumdum:make-it-look-good` - Improve the visual design of your new feature.
- `/dumdum:fix-problem` - If the new feature introduces a bug, use this to investigate and fix it.
