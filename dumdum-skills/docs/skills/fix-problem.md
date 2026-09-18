# Fix Problem - `/dumdum:fix-problem`

**Phase:** Build

## What It Does and Why

Bugs are inevitable. Every project, no matter how carefully built, will eventually do something unexpected. Fix Problem exists because debugging is one of the most frustrating parts of software development, especially if you do not know how to read error messages or understand what went wrong. This skill turns Claude into a detective who investigates the issue, explains the cause in plain English, and fixes it for you.

You do not need to understand the bug to report it. "The page is blank" is a perfectly valid description. So is "it was working yesterday and now it is not." If you have an error message, even if it looks like complete nonsense, paste it in. Those messages are like medical symptoms. They do not make sense to you, but they tell Claude exactly where to look.

Claude investigates by examining your project files, looking for common patterns that cause the type of problem you described. It works like a mechanic diagnosing a car: it checks the most likely causes first, then works through less obvious possibilities until it finds the issue. Once found, Claude explains the problem using analogies. Instead of "there is a null reference exception on line 47," you might hear "the code is trying to open a door that does not exist yet, because the door gets built later in the process."

After fixing the bug, Claude verifies the fix actually works and checks that nothing else broke in the process. You also get a mini-lesson about the type of bug, so you start recognizing patterns over time. This is not about making you into a programmer. It is about building your intuition so you can describe problems more precisely in the future.

The fix always comes with a clear explanation of what was wrong, what was changed, and why the change solves the problem. You should never feel like magic happened. You should feel like you understand what went wrong, even if you could not have fixed it yourself.

## Example Conversation

**You:** `/dumdum:fix-problem`

**Claude:** What is going wrong? You can describe it however you want. An error message, a screenshot description, or just "it is broken" all work.

**You:** When I click the "Place Order" button nothing happens. It used to work.

**Claude:** Got it, the order button stopped responding. Let me look at your project to figure out what changed. One moment.

I found the issue. In `app.js`, the function that handles the order button is trying to read the pickup time from a field called `pickup-time`, but in your last update the field ID in `order.html` was changed to `pickupTime`. The code is looking for a door labeled "pickup-time" but someone renamed the door to "pickupTime," so it cannot find it and silently gives up.

**You:** Oh, that must have happened when I was editing the form. Can you fix it?

**Claude:** Already done. I updated the reference in `app.js` to use `pickupTime` to match the current HTML. I also added a small safety check: if the pickup time field is ever missing in the future, the code will now show you a helpful error message instead of silently doing nothing.

**You:** How can I avoid this kind of thing?

**Claude:** This is called a "name mismatch" bug, and it is one of the most common problems in all of software development. It happens when two files refer to the same thing by different names. Think of it like two people trying to meet at a restaurant, but one has the old name and the other has the new name. They are both in the right place, but they cannot find each other.

The best prevention is to change names in one place at a time and immediately check if anything else references the old name. When you use `/dumdum:add-feature`, Claude handles this automatically. If you edit files by hand, just remember to search for the old name across all your files before you consider the rename done.

**You:** Makes sense. Is everything else still working?

**Claude:** I checked the rest of the order flow. The menu loading, item selection, and order confirmation are all working correctly. The admin page still shows new orders. Everything looks good.

**You:** Thanks. One more thing. I am also seeing a weird message in the browser console that says "404 Not Found" for something called favicon.ico.

**Claude:** That one is harmless. The browser is looking for a small icon to display in the browser tab (the tiny image you see next to the page title). Your project does not have one, so the browser complains about it. It does not affect anything your users see or do. If you want to add one later, you can run `/dumdum:add-feature` and ask for a browser tab icon.

## What It Produces

- **A working fix.** The bug is resolved and the project functions correctly again.
- **A root cause explanation.** A plain-English description of what went wrong, using analogies to make the concept clear. No jargon without an immediate explanation.
- **A mini-lesson.** A brief explanation of the type of bug, so you can start recognizing similar patterns. This builds your intuition over time without requiring you to learn programming.
- **Verification.** Claude checks that the fix works and that nothing else broke as a side effect.
- **Prevention tips.** When applicable, advice on how to avoid this type of problem in the future.

## Tips and Common Questions

1. **"It is just broken" is a valid description.** You do not need to diagnose the problem before reporting it. That is Claude's job. Just describe what you see (or do not see) and let the investigation begin.

2. **Paste error messages, even if they look like gibberish.** Error messages are full of clues. Even a partial error message or a screenshot description helps Claude narrow down the problem much faster.

3. **Claude always verifies the fix works.** After making a change, Claude checks that the problem is actually resolved and that the rest of the project still functions. You do not have to take it on faith.

4. **Some "bugs" are not bugs.** Sometimes the code is working correctly but doing something you did not expect. Claude will tell you when this is the case and help you decide whether to change the behavior or leave it as is.

5. **You can ask "why" as many times as you need.** If the explanation does not make sense, say so. Claude will try a different analogy or break it down further. Understanding the problem is part of the fix.

## Related Skills

- `/dumdum:test-it` - Run a full check on your project to find problems before your users do.
- `/dumdum:review-it` - Get a thorough inspection that catches potential issues, not just current bugs.
- `/dumdum:explain-it` - If you want to understand a specific part of your project better after a fix.
