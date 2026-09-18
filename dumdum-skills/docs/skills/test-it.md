# Test It - `/dumdum:test-it`

**Phase:** Check

## What It Does and Why

Building features is exciting. Testing them is how you make sure they actually work. Test It runs through your entire project, checks every feature one by one, and gives you a clear health report. It uses plain language instead of technical jargon: "working well" instead of "PASS," "needs attention" instead of "FAIL."

Most people skip testing because it feels tedious or because they do not know how to do it properly. This skill removes both obstacles. You run it, and Claude does the tedious part for you. It opens your project, tries every feature, checks edge cases (what happens with empty inputs? what happens if you click a button twice?), and reports back with findings organized by importance.

The health report is designed to be readable by anyone. Each item gets a status, a description of what was checked, and a note about what happened. If something is not working, the report explains the problem in plain English and suggests whether to fix it now or later. If everything is working, it says so. There is no manufactured drama about minor issues.

Beyond manual checking, Test It can also write automated tests if you want them. Automated tests are like hiring a quality inspector who checks your project every time you make a change. Claude explains what each test does and why it matters, so you understand the safety net being built for you. You can skip automated tests entirely if you prefer. The manual health report is valuable on its own.

Testing after every few features is a habit that prevents small problems from becoming big ones. Think of it like checking your rearview mirror while driving. Each individual check takes almost no effort, but skipping them consistently leads to trouble.

## Example Conversation

**You:** `/dumdum:test-it`

**Claude:** Let me look through your project and check everything. I will go feature by feature. One moment.

I have identified five features to check in your bakery website:

1. Menu display
2. Search functionality
3. Order placement
4. Order confirmation
5. Admin order view

Let me run through each one now.

**You:** Go ahead.

**Claude:** Here is your health report:

**Menu Display** - Working well. All six menu items load correctly. Images display at the right size. Prices are formatted properly. Item descriptions are showing in full.

**Search** - Working well. Searching by name, description, and ingredient all return correct results. The "no results" message appears when searching for something that does not exist. The clear button resets the view. Highlighting works on matched ingredients.

**Order Placement** - Needs attention. The order form accepts a pickup time in the past. Someone could schedule a pickup for 3 AM yesterday. The order still goes through, which would be confusing for both you and the customer.

**Order Confirmation** - Working well. After placing an order, the confirmation message shows the correct items, total, and pickup time. The "place another order" button returns to a clean form.

**Admin Order View** - Working well. Orders appear in the admin page within a second of being placed. Each order shows the customer name, items, and pickup time. Orders are sorted with the newest first.

Overall: 4 out of 5 features are solid. The pickup time validation is the one issue worth fixing now.

**You:** Can you fix that pickup time thing?

**Claude:** That is a fix, so I would suggest running `/dumdum:fix-problem` for that. But since it is a simple one, I can describe the issue: the time input field does not have a minimum value set, so it accepts any time including ones that have already passed. Want me to go ahead and fix it, or would you prefer to use the fix-problem skill for the full investigation and explanation?

**You:** Just fix it now.

**Claude:** Done. The pickup time field now only accepts times that are at least one hour from now. If someone tries to select an earlier time, they see a message: "Please choose a pickup time at least one hour from now." I re-tested the order flow and everything still works correctly with valid times.

**You:** Should I set up automated tests too?

**Claude:** That depends on how often you plan to change the project. If you are going to keep adding features, automated tests are worth it. They catch breakage automatically so you do not have to manually check everything after each change. If the project is mostly done, the manual health report is probably enough.

Want me to set up automated tests for the features I just checked? I will explain each one as I write it.

**You:** Let us do it. Just the most important ones.

**Claude:** I will write tests for the three most important flows: menu loading, order placement with time validation, and order confirmation. Each test is like a checklist item that runs automatically.

Done. I created `tests.js` with three automated tests:
- "Menu items load correctly" checks that all items appear with names, prices, and images
- "Order rejects past pickup times" checks that the time validation works
- "Order confirmation shows correct details" checks the full order flow

You can run these anytime by opening `tests.html` in your browser. Green means working, red means something broke. Each test has a plain-English description so you know what it is checking.

## What It Produces

- **A health report.** A feature-by-feature assessment using plain language. Each item gets a status ("working well," "needs attention," or "not working"), a description of what was checked, and notes about any problems found.
- **Prioritized findings.** Issues are ranked by importance so you know what to fix first and what can wait.
- **Automated tests (optional).** If you want them, Claude writes tests with plain-English descriptions and explains what each one checks. These run automatically and catch breakage early.
- **An overall assessment.** A summary of your project's health that tells you whether it is ready for users or needs more work.

## Tips and Common Questions

1. **Can also write automated tests if you want them.** Automated tests run your checks automatically every time you make a change. Claude explains each test in plain English so you know what is being checked and why.

2. **Uses plain language, not technical jargon.** You will see "working well" instead of "PASS" and "needs attention" instead of "FAIL." The goal is clarity, not formality.

3. **Run it after adding a few features.** Testing after every single change is overkill. Testing after every two or three new features is a good rhythm. It catches problems while they are still easy to fix.

4. **Edge cases get checked too.** Claude does not just check the happy path. It tries empty inputs, duplicate clicks, missing data, and other scenarios that real users will inevitably trigger.

5. **The health report is a snapshot.** It tells you the state of your project right now. If you make changes after testing, run it again to get an updated report.

## Related Skills

- `/dumdum:fix-problem` - Fix any issues the health report identifies.
- `/dumdum:review-it` - Get a deeper inspection that goes beyond functional testing to check security, code quality, and missing pieces.
- `/dumdum:explain-it` - Understand what a specific feature does before or after testing it.
