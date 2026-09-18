# Start Project - `/dumdum:start-project`

**Phase:** Build

## What It Does and Why

Starting a new project is the single most intimidating moment in software development. You have an idea, maybe some notes, but the gap between "I want to build X" and "I have a working project" feels enormous. Start Project exists to close that gap as fast as possible.

When you run `/dumdum:start-project`, Claude walks you through describing what you want to build in plain English. There is no need for technical specifications. You say things like "I want a website where people can sign up for my pottery classes" or "I need an app that tracks my running distances." Claude takes that description and turns it into a real, working project with actual files you can run.

Every file Claude creates comes with an explanation. You will never open a file and wonder "what is this for?" The project includes a project map, a plain-English guide that lists every file and explains its purpose using everyday language. Think of it like a table of contents for your project, but instead of page numbers, it tells you what each piece does and how it connects to the others.

Start Project is designed to get something running immediately. It does not try to build your entire vision in one shot. Instead, it creates the simplest version that actually works, then you can layer on features using `/dumdum:add-feature`. This approach means you see results in minutes, not hours, and you always have a working project to show for your effort.

If you have already run `/dumdum:pick-tools` to choose your technology stack, Start Project will use those choices. If you have not, it will pick sensible defaults based on what you described and explain why it chose them.

## Example Conversation

**You:** `/dumdum:start-project`

**Claude:** What would you like to build? Describe it however you want. A sentence, a paragraph, or just a few words are all fine.

**You:** I want a website for my small bakery. People should be able to see our menu and place orders for pickup.

**Claude:** Great, a bakery website with a menu and pickup ordering. Let me ask a few quick questions so I build the right thing. First, do you already have a list of menu items, or should I create some example items you can replace later?

**You:** Just use example items for now. I will add the real ones later.

**Claude:** Perfect. Second question: when someone places an order, how should you find out about it? Some options: you get an email notification, or you check a simple admin page on the website. Which sounds better?

**You:** An admin page sounds cool.

**Claude:** Got it. Here is what I am going to build for you: a bakery website with three main parts. The public menu page where customers browse items. An order form where they pick items and a pickup time. And a simple admin page where you can see incoming orders. I will use HTML, CSS, and JavaScript to keep things simple. Sound good?

**You:** Yes, go for it.

**Claude:** Done. I have created your project with these files:

- `index.html` - The main page customers see, with your bakery name and menu
- `order.html` - The order form where customers pick items and a pickup time
- `admin.html` - Your private page to view orders
- `styles.css` - The visual design for the whole site
- `app.js` - The code that makes ordering and the admin page work
- `PROJECT-MAP.md` - A guide explaining every file and how they connect

To see your site, open `index.html` in your browser. Try placing a test order, then check `admin.html` to see it appear. Want me to walk you through anything, or are you ready to start customizing?

**You:** This is awesome. Can I add real photos later?

**Claude:** Absolutely. When you are ready, just run `/dumdum:add-feature` and say "add photos to the menu items." I will walk you through it step by step.

## What It Produces

- **A complete, runnable project.** Every file needed to open and use the project is created and ready to go.
- **A project map.** A markdown file called `PROJECT-MAP.md` that lists every file with a plain-English explanation of what it does and how it connects to other files.
- **Sensible defaults.** Technology choices are made for you based on your description, with explanations of why each was chosen.
- **Example content.** Placeholder data that makes the project feel real and shows you where to put your own content later.

## Tips and Common Questions

1. **You do not need to plan everything first.** Start Project works best when you describe the core idea. You can always add more features later with `/dumdum:add-feature`. Getting something running quickly is more valuable than getting everything perfect upfront.

2. **Works with or without prior tool choices.** If you ran `/dumdum:pick-tools` first, Start Project respects those choices. If you did not, it picks tools for you and explains why. Either path works fine.

3. **"I do not know what I want" is okay.** You can describe your project vaguely. Claude will ask clarifying questions to figure out the details together. You do not need a clear vision before starting.

4. **The project map is your best friend.** Whenever you feel lost, open `PROJECT-MAP.md`. It tells you what every file does and which files work together. Think of it as a building directory that tells you what is on each floor.

5. **You can start over.** If the project goes in a direction you do not like, just run `/dumdum:start-project` again. There is no penalty for restarting.

## Related Skills

- `/dumdum:add-feature` - Once your project is running, use this to add new capabilities one at a time.
- `/dumdum:make-it-look-good` - Improve the visual design after the basic project is working.
- `/dumdum:pick-tools` - Choose your technology stack before starting, if you want more control over the tools used.
