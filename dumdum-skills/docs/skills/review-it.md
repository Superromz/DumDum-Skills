# Review It - `/dumdum:review-it`

**Phase:** Check

## What It Does and Why

Testing checks whether features work. Reviewing checks whether the project is ready for real users. Review It performs a thorough inspection of your entire project, looking for bugs, missing pieces, security issues, performance concerns, and opportunities for improvement. It is the difference between test-driving a car and having a mechanic inspect it before a road trip.

The review covers several categories that most people would not think to check on their own. Security is a big one. Claude looks for places where someone could misuse your project, and it explains these concerns using concrete "someone could..." examples instead of abstract warnings. "Someone could type JavaScript into your search bar and make it run" is more useful than "XSS vulnerability detected."

The review also checks for missing pieces. Maybe your order form does not handle the case where someone submits it without filling in their name. Maybe your menu does not look right on a phone screen. Maybe there is no way to go back to the main page from the order confirmation. These are the small gaps that users find quickly and that make a project feel unfinished.

Everything found in the review gets organized by severity into three buckets. "Must Fix" items are problems that would cause real trouble for users or create security risks. "Should Fix" items are things that work but are not ideal and will annoy users over time. "Nice to Fix" items are improvements that would make the project better but are not urgent.

The review is honest but not harsh. If your project is solid, Claude says so. It does not invent problems just to have something to report. And it always highlights what is done well, because knowing your strengths is just as valuable as knowing your weaknesses. A review should leave you feeling informed and motivated, not defeated.

## Example Conversation

**You:** `/dumdum:review-it`

**Claude:** Let me do a thorough inspection of your bakery website. I will check for bugs, security issues, missing pieces, and areas for improvement. This will take a moment.

I have gone through every file in your project. Here is the full review.

**You:** Let me hear it.

**Claude:** Starting with the good news. Here is what is working well:

- Your menu display is clean and consistent. Every item has a name, price, description, and ingredients. No missing data anywhere.
- The search feature is solid. It handles empty searches, partial matches, and clears correctly.
- The order confirmation flow is smooth. Users get clear feedback after placing an order.
- Your code is well-organized. Files are separated logically and functions are named clearly.

Now for the findings, organized by priority:

**Must Fix (2 items)**

1. **No input sanitization on the order form.** Someone could type code into the "name" field and it would be displayed as-is on the admin page. This means someone could inject scripts that run when you open the admin page. Think of it like someone slipping a note into an order that, when read, makes your cash register do something unexpected.

2. **Orders are stored in the browser only.** If you clear your browser data or switch computers, all orders disappear. For a real bakery taking real orders, this means you could lose customer orders without knowing it.

**Should Fix (3 items)**

1. **No mobile-friendly layout.** The site looks good on a laptop but on a phone, menu cards are too wide and text overflows. About 60% of web traffic comes from phones, so most of your customers would see a broken layout.

2. **No "back to menu" link on the order page.** If a customer navigates to the order form and changes their mind, there is no obvious way to get back to the menu. They would need to use the browser's back button or edit the URL.

3. **The admin page has no access protection.** Anyone who knows the URL can see all orders. There is no password or login. If someone guesses "admin.html," they see everything.

**Nice to Fix (2 items)**

1. **No loading indicators.** When the menu first loads, there is a brief flash of empty space before items appear. A simple "Loading..." message would make this feel smoother.

2. **Order timestamps do not show the date.** Orders on the admin page show the pickup time but not when the order was placed. Adding an "ordered at" timestamp would help you manage the queue.

That is the full review. Overall, your project is in good shape functionally. The two "Must Fix" items are important to address before sharing this with real customers. Want to tackle any of these?

**You:** The security one sounds scary. Can you explain it more?

**Claude:** Sure. Here is what could happen. Let us say someone goes to your order form and in the "Your Name" field, instead of typing "John," they type a snippet of code. When you open the admin page and it displays that order, the browser sees the code and runs it. This could do things like redirect your admin page to a different website, or display fake information.

In practice, for a small bakery site, the risk is low because most customers are just trying to order pastries. But it is a good habit to fix because the solution is simple: before displaying any user-entered text, clean it so the browser treats it as plain text, never as code. Think of it like checking IDs at the door. You just verify that what comes in is what you expect.

**You:** Fix that one for me.

**Claude:** I would recommend running `/dumdum:fix-problem` and telling it about this issue. It will fix it and give you a proper explanation of the change. Or I can make the fix directly. Your call.

**You:** Just fix it now.

**Claude:** Done. I added a text sanitization function in `app.js` that cleans all user input before it gets displayed on the admin page. Names, special requests, and any other text fields now get treated as plain text only. The browser will never try to run them as code. I verified that normal names with special characters (like "O'Brien" or "Mary-Jane") still display correctly.

## What It Produces

- **A severity-organized checklist.** Every finding is categorized as "Must Fix," "Should Fix," or "Nice to Fix" so you know what to prioritize.
- **Concrete security assessments.** Security concerns are explained with "someone could..." examples that make the risk tangible, not abstract.
- **Highlights of what is done well.** The review acknowledges strengths, not just weaknesses. Knowing what works helps you make good decisions about what to keep.
- **An overall assessment.** A summary judgment on whether the project is ready for users, needs a few fixes, or needs significant work.
- **Actionable recommendations.** Each finding comes with a suggestion for how to address it, so the review is a to-do list, not just a list of complaints.

## Tips and Common Questions

1. **Security concerns use "someone could..." examples.** Instead of technical jargon like "XSS vulnerability," the review explains what a real person could actually do to misuse your project. This makes risks concrete and understandable.

2. **Celebrates what is done well.** A good review is balanced. If your project is solid in most areas, the review says so clearly. It does not invent problems to seem thorough.

3. **Does not invent problems.** If your project is well-built and secure, the review will have a short findings list and a positive overall assessment. A clean report is a good thing, not a sign that Claude missed something.

4. **Run it before sharing your project.** The best time for a review is right before you show your project to other people. It catches the things that are easy to fix now but embarrassing to discover later.

5. **Findings are not demands.** "Nice to Fix" items might never get fixed, and that is completely fine. The review gives you information to make decisions. It does not make the decisions for you.

## Related Skills

- `/dumdum:fix-problem` - Address any "Must Fix" or "Should Fix" items from the review.
- `/dumdum:test-it` - Run functional tests to verify that features work correctly. Complements the broader inspection that Review It provides.
- `/dumdum:explain-it` - Understand specific parts of your project that came up in the review.
