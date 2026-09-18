# DumDum Skills -- Complete Reference

Every DumDum skill, organized by phase. Each entry covers what the skill does, what a typical conversation looks like, and what you walk away with.


---

## Think Phase

These skills help you go from a vague idea to something clear enough to build.


### /dumdum:idea

**What it does:**
Tell DumDum your idea -- however rough or half-formed -- and it will ask you questions to help shape it into something concrete and buildable. It doesn't judge your idea. It helps you find the core of it, figure out what it actually needs to do, and write a short summary you can build from.

**Example conversation:**

> You: /dumdum:idea
>
> DumDum: What do you want to build? Don't worry about being precise -- just tell me what's in your head.
>
> You: I want a website where people can trade books with each other.
>
> DumDum: That's a great starting point. Let me ask a few questions to help us get specific. When you say "trade," do you mean people physically mail books to each other, or is this more about swapping digital recommendations?

**What it produces:**
A clear, one-paragraph summary of your project idea, including what it does, who it's for, and what makes it different. This summary becomes the foundation for everything that follows.


### /dumdum:who-is-it-for

**What it does:**
Helps you think through who will actually use your project. It asks questions about your audience -- their age, their comfort with technology, what problem they're trying to solve -- and produces a simple profile of your typical user.

**Example conversation:**

> You: /dumdum:who-is-it-for
>
> DumDum: Let's figure out who will use what you're building. Can you describe one person you imagine using this? They can be real or made up.
>
> You: My neighbor Karen. She's 55, loves reading, has too many books, and wants to find people nearby to swap with.

**What it produces:**
A short user profile describing who your project is for, what they care about, and what they need the project to do for them.


### /dumdum:break-it-down

**What it does:**
Takes your idea and splits it into small, buildable pieces. Each piece is something you could build in one sitting. It ranks them by importance so you know what to build first and what can wait.

**Example conversation:**

> You: /dumdum:break-it-down
>
> DumDum: Let me look at what you're building and suggest a way to split it into smaller pieces. I'll put the most important ones first... Here's what I came up with:
> 1. A page where people can list a book they want to trade (this is the core -- nothing works without it)
> 2. A page where people can browse available books
> 3. A way to send a trade request to someone

**What it produces:**
A prioritized list of features, each described in plain English, ranked from "build this first" to "nice to have later."


---

## Plan Phase

These skills help you figure out what your project looks like and what tools you need before you start building.


### /dumdum:sketch-it

**What it does:**
Walks you through describing what each screen or page of your project looks like. No drawing tools needed -- you describe it in words, and DumDum helps you think through the layout, what goes where, and how people will move between screens.

**Example conversation:**

> You: /dumdum:sketch-it
>
> DumDum: Let's describe what your project looks like, screen by screen. Starting with the first thing someone sees when they open it -- what should be on that page?
>
> You: A big search bar and a list of recently added books.
>
> DumDum: Good. So the main page has two parts: a search area at the top and a list of books below it. For each book in the list, what info should people see? The title? A picture of the cover? The condition?

**What it produces:**
A plain-language description of every screen in your project, including what's on each screen, what people can do there, and how they get to other screens.


### /dumdum:pick-tools

**What it does:**
Recommends the right technology for your project based on what you're building, who it's for, and how complex it is. Everything is explained in plain English -- no assumed knowledge about programming languages or frameworks.

**Example conversation:**

> You: /dumdum:pick-tools
>
> DumDum: Let me look at your project and suggest the best tools for it. A few questions first: Does this need to work on phones, computers, or both?
>
> You: Both, but mostly phones.
>
> DumDum: Got it. For a project like this, I'd suggest building it as a web app. That means it runs in a web browser, which works on both phones and computers without needing to build two separate apps.

**What it produces:**
A recommended set of tools for your project with plain-English explanations of what each tool is, why it was chosen, and what it does.


### /dumdum:steps

**What it does:**
Takes your feature list (from `/dumdum:break-it-down` or wherever you have one) and turns it into an ordered build plan. Each step says what you'll build, roughly how long it takes, and what you'll have at the end of that step.

**Example conversation:**

> You: /dumdum:steps
>
> DumDum: Let me turn your feature list into a step-by-step build plan... Here's the order I'd suggest:
> Step 1: Set up the project and get a blank page running (10 minutes)
> Step 2: Build the "add a book" page (30 minutes)
> Step 3: Build the book listing page (20 minutes)
> After step 3, you'll have a working app where people can add books and browse them.

**What it produces:**
A numbered build plan with clear milestones, so you always know what to work on next and what "done" looks like for each step.


---

## Build Phase

These skills do the actual construction. They write code, create files, and make your project work.


### /dumdum:start-project

**What it does:**
Creates a brand-new project from scratch. It sets up the folder structure, installs the necessary tools, and gets something visible running -- usually a basic page you can see in your browser. Every file it creates is explained.

**Example conversation:**

> You: /dumdum:start-project
>
> DumDum: Let's get your project started. I'll create the basic structure and get something running so you can see it in your browser. This will take about a minute...
>
> DumDum: Done. I created 4 files. Here's what each one does:
> - index.html -- This is the main page of your project. Right now it just says "Hello World" but we'll change that.
> - styles.css -- This controls what your project looks like (colors, fonts, spacing).
> ...

**What it produces:**
A working project you can open and see. All files explained.


### /dumdum:add-feature

**What it does:**
Adds one new feature to your existing project. It asks what you want to add, explains what changes are needed, makes the changes, and then walks you through what it did. One feature at a time -- no overwhelming batches.

**Example conversation:**

> You: /dumdum:add-feature
>
> DumDum: What feature do you want to add?
>
> You: I want people to be able to search for books by title.
>
> DumDum: Got it. To add search, I'll need to do three things: add a search box to the main page, write the code that filters the book list when someone types, and make sure it works even if someone types in all caps. Let me do that now...

**What it produces:**
A working new feature in your project, with an explanation of every change that was made and why.


### /dumdum:fix-problem

**What it does:**
Helps you find and fix something that's broken. You describe the problem in your own words -- "the page is blank," "clicking the button does nothing," "it shows the wrong number" -- and DumDum investigates, finds the cause, and fixes it. The whole process is explained in plain English.

**Example conversation:**

> You: /dumdum:fix-problem
>
> DumDum: What's going wrong?
>
> You: When I click "add book" nothing happens.
>
> DumDum: Let me look into that... I found the issue. The button is there, but it isn't connected to anything yet. It's like a doorbell with no wires. I'll connect it to the code that handles adding books.

**What it produces:**
A fix for the problem, with a plain-English explanation of what was wrong and how it was resolved.


### /dumdum:make-it-look-good

**What it does:**
Improves the visual design of your project. It looks at what you have and suggests improvements to colors, spacing, fonts, and layout. You can also describe what you want it to look like ("make it feel modern and clean," "use blue and white") and it will apply those changes.

**Example conversation:**

> You: /dumdum:make-it-look-good
>
> DumDum: Let me look at your project's current design... Right now it's using default browser styling, which means everything looks a bit plain. I can improve this. Do you have a vibe in mind? Something modern and minimal? Colorful and playful? Professional and corporate?
>
> You: Modern and minimal, dark background.

**What it produces:**
Updated visual design with better colors, spacing, typography, and layout. All changes explained.


---

## Check Phase

These skills help you verify your work and understand what's in your project.


### /dumdum:test-it

**What it does:**
Runs your project and checks if everything is working. It tries the main features, looks for errors, and reports back in plain language. It tells you what works, what doesn't, and what you might want to fix.

**Example conversation:**

> You: /dumdum:test-it
>
> DumDum: Let me check your project... I tested 4 things:
> - Opening the main page: Works.
> - Adding a book: Works.
> - Searching for a book: Works, but searching with no results shows a blank page instead of a "no results" message.
> - Sending a trade request: Not built yet.

**What it produces:**
A plain-language test report showing what works, what's broken, and what still needs to be built.


### /dumdum:explain-it

**What it does:**
Point it at any file in your project and it will explain what that file does, line by line if needed, in plain English. Great for understanding code you didn't write, or code DumDum wrote that you want to learn from.

**Example conversation:**

> You: /dumdum:explain-it
>
> DumDum: Which file do you want me to explain?
>
> You: The main JavaScript file.
>
> DumDum: That's app.js. Here's what it does, section by section:
> The first part sets up the book list. It creates an empty list in the computer's memory that will hold all the books people add...

**What it produces:**
A plain-English explanation of what a file does, how it works, and why it's set up the way it is.


### /dumdum:review-it

**What it does:**
Looks at your whole project and checks for problems, missing pieces, and things that could be improved. It's like having a second pair of eyes look over your work. It checks for common issues, incomplete features, and things you might have forgotten.

**Example conversation:**

> You: /dumdum:review-it
>
> DumDum: Let me look through your whole project... Here's what I found:
> - The "add book" page doesn't check if someone forgot to type a title. It should show a message if they try to add a book without a title.
> - The search works, but it's case-sensitive. Searching for "harry" won't find "Harry Potter."
> - Overall structure looks good. Files are organized well.

**What it produces:**
A list of issues, suggestions, and compliments about your project's current state.


---

## Ship Phase

These skills help you save your work, put it online, and share it with others.


### /dumdum:save-progress

**What it does:**
Saves a checkpoint of your work so you can always come back to this point if something goes wrong later. It's like a save point in a video game. You describe what you just finished, and DumDum saves it with that description.

**Example conversation:**

> You: /dumdum:save-progress
>
> DumDum: What did you just finish working on?
>
> You: Added the search feature.
>
> DumDum: I'll save a checkpoint called "Added the search feature." This means if anything breaks later, you can go back to this moment when everything was working. Saving now... Done. Your progress is saved.

**What it produces:**
A saved checkpoint of your project (using git behind the scenes) that you can return to if needed.


### /dumdum:put-it-online

**What it does:**
Walks you through putting your project on the internet so other people can use it. It picks the simplest hosting option for your project type and guides you through every step, including creating accounts if needed.

**Example conversation:**

> You: /dumdum:put-it-online
>
> DumDum: Let's get your project on the internet. Based on what you've built, the simplest option is a free hosting service. I'll walk you through it step by step. First, do you have a GitHub account? (GitHub is a website where your project's files will be stored.)

**What it produces:**
Your project, live on the internet, with a URL you can share.


### /dumdum:tell-people

**What it does:**
Generates everything you need to share your project with the world: a project description, a README file (the first thing people see when they find your project), and a social media post you can copy and paste.

**Example conversation:**

> You: /dumdum:tell-people
>
> DumDum: Let me create some materials for sharing your project. I'll make three things: a README for your project page, a short description you can use anywhere, and a social media post... Here's the social media post:
>
> "I just built a book trading app where you can swap books with people near you. Check it out: [link]"

**What it produces:**
A README file, a short project description, and a ready-to-post social media blurb.


---

## Learn Phase

These skills help you understand your project and the concepts behind it.


### /dumdum:whats-happening

**What it does:**
Gives you a plain English summary of your project's current state. What files exist, what features are working, what's been changed recently, and what's left to do. Useful when you come back to a project after a break.

**Example conversation:**

> You: /dumdum:whats-happening
>
> DumDum: Here's where your project stands:
> - You have a book trading app with 6 files.
> - Working features: adding books, browsing books, searching by title.
> - Last thing you worked on: the search feature.
> - Not built yet: trade requests, user accounts.

**What it produces:**
A clear snapshot of your project -- what's done, what's in progress, and what's still ahead.


### /dumdum:teach-me

**What it does:**
Pick any concept from your project -- or anything related to building software -- and DumDum will explain it using analogies, examples, and plain language. It adapts to your level and checks if the explanation made sense.

**Example conversation:**

> You: /dumdum:teach-me
>
> DumDum: What do you want to learn about?
>
> You: What is an API?
>
> DumDum: An API is like a waiter at a restaurant. You (the customer) don't go into the kitchen and cook your own food. Instead, you tell the waiter what you want, the waiter goes to the kitchen, and the waiter brings back your food. An API works the same way -- your project asks another computer for something, and the API handles the back-and-forth.

**What it produces:**
A clear, memorable explanation of any concept, tailored to your level of experience.


### /dumdum:glossary

**What it does:**
Scans your project and builds a jargon-free dictionary of every technical term that appears in it. Each term gets a plain-English definition with an analogy or example.

**Example conversation:**

> You: /dumdum:glossary
>
> DumDum: Here's a glossary for your project:
> - **HTML** -- The skeleton of a web page. It defines what's on the page (headings, paragraphs, buttons) but not how it looks.
> - **CSS** -- The clothing of a web page. It controls colors, fonts, spacing, and layout.
> - **JavaScript** -- The brain of a web page. It makes things interactive -- what happens when you click a button, type in a search box, etc.

**What it produces:**
A complete, plain-English glossary of technical terms found in your project.


---

## Manage Phase

These skills help you keep your project organized and on track.


### /dumdum:whats-left

**What it does:**
Shows you a simple checklist of everything that still needs to be done, ranked by priority. It looks at your project, compares it to any plans you've made, and identifies what's finished and what's still ahead.

**Example conversation:**

> You: /dumdum:whats-left
>
> DumDum: Here's what's left to do:
> - [High priority] Trade request feature -- people can't actually trade yet
> - [Medium priority] "No results" message for empty searches
> - [Low priority] Add a footer with contact info
> - [Done] Book listing, search, add book

**What it produces:**
A prioritized to-do list showing exactly what's left to build.


### /dumdum:clean-up

**What it does:**
Looks through your project for unused code, disorganized files, and things that could be tidied up. It explains what it wants to clean and why before making any changes. Nothing is deleted without your approval.

**Example conversation:**

> You: /dumdum:clean-up
>
> DumDum: Let me scan your project for things to tidy up... I found a few things:
> - There's a file called "test.html" that isn't used by anything. Want me to remove it?
> - The CSS file has some styles that aren't used anymore (from when we changed the layout). Want me to remove those?
> - The JavaScript file has some notes I left while building. Want me to clean those up?

**What it produces:**
A cleaner, more organized project with explanations of everything that was changed or removed.


### /dumdum:take-notes

**What it does:**
Saves a note into your project's journal. Use it to record decisions ("we chose blue because the client likes blue"), ideas for later ("maybe add a dark mode someday"), or reminders ("ask Maria about the logo"). Notes are saved to a file in your project so you can always look back.

**Example conversation:**

> You: /dumdum:take-notes
>
> DumDum: What do you want to note down?
>
> You: We decided not to add user accounts for now because it makes things too complicated.
>
> DumDum: Got it. I saved this note: "Decision: No user accounts for now -- keeps things simple." It's saved in your project journal so you can look back later if you forget why that choice was made.

**What it produces:**
A timestamped note saved to your project's journal file.
