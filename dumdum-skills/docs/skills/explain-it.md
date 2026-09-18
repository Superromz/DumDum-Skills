# Explain It - `/dumdum:explain-it`

**Phase:** Check

## What It Does and Why

Software projects are full of files, functions, and connections that can feel overwhelming. Explain It is your personal tour guide. Point it at any file, feature, or even the entire project, and it breaks everything down into plain English using analogies from everyday life.

The core philosophy is that you should never feel lost in your own project. Even if you did not write the code yourself, you should be able to understand what every piece does and how it connects to the others. Explain It makes that possible by translating technical concepts into things you already understand: buildings, restaurants, mail systems, assembly lines, and other familiar structures.

Each explanation is structured in sections, not dumped as a wall of text. If you ask about a file, Claude walks through it section by section, explaining what each part does and why it exists. If you ask about a feature, Claude traces the path from start to finish: what happens when a user clicks a button, where that information goes, and what produces the result they see. If you ask about the entire project, you get a guided tour of every file and how they all fit together.

The explanations are calibrated for people who do not write code. Technical terms are used only when necessary, and every term gets an immediate plain-English definition. "API" becomes "a way for two programs to talk to each other, like a waiter carrying orders between you and the kitchen." "Variable" becomes "a labeled box that holds a piece of information."

If an explanation does not click, say so. Claude will try a different analogy or break the concept into smaller pieces. Understanding is the goal, not just coverage. There is no such thing as a stupid question, and there is no penalty for asking "what does that mean?" as many times as you need.

## Example Conversation

**You:** `/dumdum:explain-it`

**Claude:** What would you like me to explain? You can point me at a specific file, a feature, or say "everything" for a full project tour.

**You:** Explain the `app.js` file.

**Claude:** Let me read through `app.js` and break it down for you.

This file is the brain of your website. If your website were a restaurant, `app.js` would be the kitchen staff, the people who take orders, prepare food, and send it out to the dining room. The HTML files are the dining room (what customers see), and `app.js` is everything happening behind the scenes.

Let me walk through it section by section.

**Section 1: Menu Data (lines 1-45)**
This is like the recipe book. It contains a list of all your menu items with their names, prices, descriptions, and ingredients. Each item is stored as a bundle of information. When the website loads, this section is what gets read to display the menu. If you want to change a menu item, this is where you would do it.

**Section 2: Display Functions (lines 47-82)**
These are the servers. They take items from the recipe book and arrange them nicely on the page. One function creates the menu card layout. Another formats prices so they always show two decimal places. A third handles the images. They do not decide what to show. They just decide how to show it.

**Section 3: Search (lines 84-120)**
This is like a dining room host who helps guests find what they want. When someone types in the search bar, this section filters the menu to show only matching items. It checks names, descriptions, and ingredients. If nothing matches, it puts up a polite "nothing found" sign.

**Section 4: Order Handling (lines 122-175)**
This is the order-taking process. When a customer fills out the order form and clicks submit, this section collects all the information (what they ordered, when they want to pick it up, their name), packages it up, saves it, and shows a confirmation. It also checks that the pickup time is valid.

Want me to go deeper into any of these sections?

**You:** What does "saves it" mean in the order handling section? Where does the order go?

**Claude:** Good question. Right now, orders are saved in something called "localStorage." Think of it like a notebook that lives inside the customer's browser. The order gets written into this notebook, and then the admin page reads from the same notebook to show you the orders.

The important thing to know: this notebook only exists on one computer. If a customer places an order on their phone, you will not see it on your laptop. The notebook is not shared between devices. For a real bakery with customers on different devices, you would eventually want a central storage system, like a filing cabinet at the restaurant that everyone can access. That would be a future feature to add.

**You:** That makes sense. What about the `styles.css` file? Just a quick overview.

**Claude:** `styles.css` is the interior decorator. It decides how everything looks but has no say in how anything works. It controls colors, fonts, spacing, button shapes, shadows, and layout.

Think of it this way: `index.html` says "put a menu card here." `styles.css` says "make that card cream-colored with rounded corners and a gentle shadow." `app.js` says "fill that card with the chocolate cake information."

The file is organized by page section: general styles at the top (things that apply everywhere), then menu-specific styles, then order form styles, then admin page styles. If you ever want to change a color or font size, this is the only file you need to touch.

**You:** Can you explain what would happen if I deleted the styles.css file?

**Claude:** Your website would still work perfectly. Every button would still click, every order would still go through, every search would still filter. But it would look like a plain text document from 1995. No colors, no rounded corners, no spacing, no card layouts. Just raw text and default browser styling stacked vertically down the page.

It is like removing all the paint, furniture, and decorations from a restaurant. The kitchen still works. The food is still good. But nobody wants to eat there because it looks like an empty warehouse.

## What It Produces

- **Section-by-section explanations.** Every file or feature is broken into logical sections, each explained independently so you can follow along without getting overwhelmed.
- **Everyday analogies.** Technical concepts are mapped to familiar things: restaurants, buildings, mail systems, recipe books. Each analogy is chosen to match the concept as closely as possible.
- **Plain-English definitions.** Every technical term used in an explanation gets an immediate, jargon-free definition. Nothing is assumed.
- **Connection maps.** When explaining a feature or the full project, Claude shows how pieces connect to each other, like how the menu data flows from `app.js` to the display on `index.html`.

## Tips and Common Questions

1. **You can say "everything" for a full project tour.** Claude will walk through every file and explain how they all connect, like a guided tour of a building where you visit every room.

2. **Ask about specific files or features.** "Explain the search feature" or "explain order.html" both work. You can be as specific or as broad as you want.

3. **If an analogy does not work, say so.** Claude will try a different comparison. Not every analogy clicks with every person, and that is fine. The goal is understanding, not a one-size-fits-all script.

4. **Explanations can go as deep as you want.** Start with an overview, then ask follow-up questions about anything that interests you. "What does that part do exactly?" is always a valid question.

5. **This skill does not change any files.** It is purely informational. Your project stays exactly as it is. There is no risk of breaking anything by asking questions.

## Related Skills

- `/dumdum:teach-me` - Go beyond understanding your project to learning general programming concepts.
- `/dumdum:review-it` - Get an expert assessment of your project's quality, not just an explanation of what it does.
- `/dumdum:glossary` - Look up specific technical terms without needing a full explanation of a file or feature.
