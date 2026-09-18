# Pick Tools: Choose Your Technologies With Plain-English Guidance

**Command:** `/dumdum:pick-tools`
**Phase:** Plan

## What It Does and Why

Choosing the right technology for a project can feel overwhelming. There are hundreds of programming languages, dozens of frameworks, and countless databases, hosting platforms, and libraries. If you are not a developer, these names are meaningless alphabet soup. The pick-tools skill cuts through the noise by recommending exactly one tool for each category, explaining each choice using everyday language and familiar analogies.

When you run `/dumdum:pick-tools`, Claude looks at what you are building (from your earlier context files if they exist, or by asking you) and recommends a technology stack. A "stack" is just the set of tools your project needs: a programming language to write the code in, a framework to give you a head start, a database to store information, and a hosting platform to put it on the internet. Some projects also need extras, like a tool for sending emails or processing payments.

Claude does not list five options and ask you to pick. That would just move the overwhelm from one place to another. Instead, it recommends one tool per category and explains why in plain language. "React is a way to build web pages. Think of it like a set of building blocks. Instead of writing every button and form from scratch, you snap together pre-made pieces." If you have a preference or constraint ("my friend knows Python" or "I need this to be free"), Claude adjusts the recommendations to fit.

The explanations matter as much as the recommendations. Understanding why a tool was chosen helps you make better decisions later. If Claude recommends a simple database because your project is small, and six months later your project grows, you will understand why it might be time to switch to something more powerful.

This skill also flags what you do not need. Beginners often worry about tools that only matter at massive scale, like load balancers or container orchestration. Claude will tell you when something is overkill for your project size, saving you from unnecessary complexity.

## Example Conversation

**You:** `/dumdum:pick-tools`

**Claude:** I found your idea summary for "Building Lending Library," a sharing tool for apartment residents. Let me figure out the right tools for this. First question: is this going to be a phone app, a website, or something else?

**You:** A website. I want people to use it on their phones too, but I do not want to build a separate phone app.

**Claude:** Perfect. A website that works well on phone screens. That is called a "responsive" website, and almost all modern tools handle that well. Next question: do you or anyone helping you have experience with any programming language?

**You:** No, I have never coded before. My friend knows a little JavaScript.

**Claude:** Good to know. JavaScript is a great starting point because it can handle both the part users see (the screens) and the part that runs behind the scenes (saving data, handling requests). Here is what I would recommend:

**Language: JavaScript.** This is the most widely used language for websites. Think of it as the universal language of the web. Every browser already speaks it. Since your friend knows some JavaScript, you have a built-in resource when you get stuck.

Does that make sense so far, or do you have questions?

**You:** Makes sense. What about the framework thing?

**Claude:** **Framework: Next.js.** A framework is like a starter kit. Instead of building a house from raw lumber, you get pre-framed walls and a foundation. Next.js gives you page routing (so /browse goes to the browse page and /login goes to the login page), works great on phones, and has a huge community posting answers to common questions. Want me to continue with the database?

**You:** Yes, and I want it to be free or very cheap.

**Claude:** **Database: Supabase (free tier).** A database is where your app remembers things: which items exist, who owns them, who requested a borrow. Supabase is like a spreadsheet that your website can read and write to automatically. The free tier gives you plenty of room for a single apartment building. You would not need to pay until you have thousands of users.

**Hosting: Vercel (free tier).** Hosting is what puts your website on the internet so people can visit it. Vercel is made by the same team that makes Next.js, so they work together seamlessly. The free tier handles small projects easily.

**Extras: none needed right now.** You do not need email services, payment processing, or anything else for your first version. Notifications can start as simple in-app messages.

**You:** This all makes sense. What if I want to add email notifications later?

**Claude:** When the time comes, I would recommend Resend. It is a simple email-sending service with a generous free tier. But that is a "later" decision. For now, your stack is JavaScript, Next.js, Supabase, and Vercel. Let me save this.

**Claude:** Done. I saved your tool choices to the project. Each recommendation includes the tool name, what it does in plain language, why it was chosen for your project, and the cost (all free tier for now).

## What It Produces

The skill creates a tool choices summary covering each category your project needs. For each tool, the summary includes:

- **Category:** What role this tool plays (language, framework, database, hosting, extras).
- **Tool name:** The specific tool recommended.
- **Plain-English explanation:** What the tool does, described using everyday analogies. No jargon left unexplained.
- **Why this one:** The specific reasons this tool fits your project, including your constraints (budget, experience level, project size).
- **Cost:** Whether the tool is free, has a free tier, or requires payment, with specifics about limits.
- **What you do not need:** A note about tools or categories you can safely ignore for now.

The summary is written so that someone with zero technical background can read it and understand every recommendation.

## Tips and Common Questions

- **It is fine to say "I don't know" when asked about tech preferences.** That is the most common answer, and Claude will make the decision for you based on your project needs.
- **Claude recommends ONE tool per category.** No lists of five options to research. One recommendation with a clear reason. If you disagree, say so and Claude will suggest an alternative.
- **Your friend's skills matter.** If someone helping you already knows a language or tool, tell Claude. Familiarity often outweighs technical superiority.
- **Free does not mean bad.** For small projects, free tiers of modern tools are genuinely excellent. Claude will tell you honestly when a paid tool is worth it.
- **You can rerun this if your project scope changes.** If your one-building app becomes a multi-city platform, your tool needs might change. Run pick-tools again for updated recommendations.

## Related Skills

- `/dumdum:start-project` : Once you know your tools, create the actual project with the right files and folder structure.
- `/dumdum:steps` : Plan the build order so you know what to code first using your chosen tools.
- `/dumdum:sketch-it` : If you have not designed your screens yet, do that before picking tools so Claude can factor in your UI complexity.
