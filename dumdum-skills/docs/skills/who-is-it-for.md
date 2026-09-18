# Who Is It For: Identify Your Users and What They Need

**Command:** `/dumdum:who-is-it-for`
**Phase:** Think

## What It Does and Why

Building something without knowing who will use it is like cooking a meal without knowing who is coming to dinner. You might make something great, but you might also serve steak to a vegetarian. The who-is-it-for skill helps you figure out exactly who your users are, what they need, what they want, and what would make them walk away.

When you run `/dumdum:who-is-it-for`, Claude walks you through a conversation about the people who will use your product. It starts simple: "Who do you picture using this?" From there, it digs into the details. What does a typical day look like for that person? What are they trying to accomplish? What would frustrate them? What would delight them? These are not abstract exercises. They directly shape what you build and how you build it.

Most projects have more than one type of user, and each type cares about different things. A teacher and a student both use a classroom app, but they need completely different features. This skill helps you see those differences clearly. It creates a profile for each user type that captures their goals, frustrations, comfort with technology, and the one thing that would make them love your product.

If you ran the idea skill first, Claude will read your `idea-summary.md` file automatically. You will not need to re-explain your project. If you did not run the idea skill, that is fine too. Claude will ask about your idea before jumping into user questions.

The result is a user guide that keeps you focused on real people instead of abstract features. When you are deep in building and wondering "should I add this button?", you can check your user guide and ask, "would any of my users actually want this?"

## Example Conversation

**You:** `/dumdum:who-is-it-for`

**Claude:** I found your idea summary for "Building Lending Library," a sharing tool for your apartment building. Let me ask about the people who would use this. Who is the first person you picture opening this app?

**You:** Probably someone like my neighbor Maria. She is always looking for a ladder or a big pot for parties.

**Claude:** Maria sounds like a borrower. She needs things she does not own and does not want to buy for occasional use. How comfortable is she with technology? Does she use apps easily, or does she prefer simpler tools?

**You:** She uses WhatsApp and Facebook but nothing too complicated. She would not want to create a long profile or anything.

**Claude:** Got it. Low friction is important for Maria. Now, who is on the other side? Who is the person listing their stuff to lend?

**You:** Probably someone like Dave down the hall. He has a garage full of tools and he is always happy to lend them. He just forgets who has what.

**Claude:** So Dave is a lender. His problem is not willingness, it is tracking. He wants to help but loses track of what is out and with whom. Is Dave more or less tech-savvy than Maria?

**You:** About the same. He can use apps but does not want to spend a lot of time on setup.

**Claude:** Makes sense. Is there anyone else? Maybe someone who manages the building, or someone who would be skeptical of the whole idea?

**You:** The building manager, Susan. She would want to make sure people are not fighting over stuff or damaging things.

**Claude:** Susan is an overseer. She does not borrow or lend much herself, but she cares about keeping the peace. She would want to see if there are disputes or problems. What would make Susan say "no, shut this down"?

**You:** If people started arguing about damaged items or if someone kept borrowing and never returning.

**Claude:** That is really helpful. Now I have three clear user types. Let me write up the user guide.

**Claude:** Done. I saved the user guide to `user-guide.md`. It covers three user types: the Borrower (Maria), the Lender (Dave), and the Building Manager (Susan). Each profile includes their goals, frustrations, tech comfort, and dealbreakers.

## What It Produces

The skill creates a file called `user-guide.md` in your project directory. The file contains a profile for each user type you identified. Each profile includes:

- **User type name:** A short, memorable label (like "The Borrower" or "The Building Manager").
- **Description:** A one-paragraph summary of who this person is and why they would use the product.
- **Goals:** What this user is trying to accomplish when they open the app. Typically 2-4 items.
- **Frustrations:** What annoys this user type about existing solutions or the current situation.
- **Tech comfort:** A plain-language description of how comfortable they are with technology.
- **Dealbreakers:** The specific things that would make this user stop using the product entirely.
- **Delight factor:** The one thing that would make this user tell a friend about the product.

The profiles are written in everyday language, not marketing jargon. They read like descriptions of real people, because they are based on real people you know.

## Tips and Common Questions

- **"Just me" is a valid answer.** If you are building something only for yourself, you are still a user with needs, preferences, and dealbreakers. The skill works just as well with one user type.
- **It reads idea-summary.md if it exists.** If you ran the idea skill first, you will not have to re-explain your project. If the file does not exist, Claude will ask about your idea before diving into users.
- **Think about people you actually know.** Abstract personas ("tech-savvy millennial") are less useful than real people ("my sister who texts me for help with her phone"). Ground each user type in someone real.
- **Three to five user types is the sweet spot.** Fewer than three and you might miss a perspective. More than five and the profiles become hard to keep track of.

## Related Skills

- `/dumdum:break-it-down` : Once you know your users, split features into priorities based on what matters most to them.
- `/dumdum:sketch-it` : Design screens that match what each user type needs to see and do.
- `/dumdum:idea` : If you have not clarified your idea yet, start here before identifying users.
