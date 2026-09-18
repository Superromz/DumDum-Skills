# Tell People (`/dumdum:tell-people`)

**Phase:** Ship

## What It Does

Tell People helps you announce your project to the world by creating three shareable items: a README file for your project, a short description you can paste anywhere, and a social media post ready to publish. Each piece is tailored to the audience you want to reach, whether that is developers, friends, potential users, or hiring managers.

The skill starts by exploring your project to understand what it does, what technologies it uses, and what makes it interesting. Then it asks who you want to tell and adjusts the tone accordingly. A post aimed at developer friends on Twitter will sound very different from a README aimed at open-source contributors. The skill matches the way you naturally talk so the result does not feel like it was written by a robot.

Many people build something great and then struggle to explain it. They either undersell it ("it's just a little thing I made") or drown the reader in technical details that only make sense to other programmers. This skill finds the middle ground. It highlights what makes your project useful or interesting in terms that your target audience will appreciate.

The README it produces is not a generic template. It is a custom document that explains your specific project, with real descriptions of what it does, how to use it, and why someone might care. The short description works for GitHub project descriptions, portfolio entries, or anywhere you need one or two sentences. The social media post includes a hook, a brief explanation, and a call to action.

All three outputs are shown to you for review before anything is saved or published. You can ask for revisions, adjust the tone, or swap out details until it feels right.

## Example Conversation

**User:** `/dumdum:tell-people`

**Claude:** Let me look through your project so I can understand what you have built.

**Claude:** Your project is a meal planning app that suggests recipes based on what ingredients you already have at home. It is built with React and uses a Node.js backend with a recipe database. That is a really practical idea. Who do you want to tell about it?

**User:** I want to share it on Twitter and also make a good README for GitHub.

**Claude:** Great. For Twitter, do you want a casual tone or something more polished? And for the GitHub README, are you hoping other developers will contribute, or is it more of a showcase for your portfolio?

**User:** Casual for Twitter. The README is mostly for my portfolio, like if a hiring manager looks at my GitHub.

**Claude:** Got it. Here is the Twitter post:

"I built an app that looks at what is already in your fridge and tells you what you can make for dinner. No more staring at random ingredients wondering what to cook. Check it out: [link]"

And here is the README. It starts with a one-line description, then has sections for what it does, a screenshot placeholder, how to run it locally, and the tech stack. I wrote the tech stack section to be impressive but not intimidating, since hiring managers may not be deeply technical. Want me to read it to you?

**User:** Yeah, show me the README.

**Claude:** Here it is:

[Shows full README with project title, description, features list, screenshot section, setup instructions, tech stack, and a brief "Why I Built This" section]

**User:** That looks good but can you make the "Why I Built This" section more personal? I built it because I kept wasting groceries.

**Claude:** Absolutely. Here is the updated version:

"I kept buying groceries with good intentions, then watching them go bad because I could not figure out what to make. This app solves that. You tell it what you have, and it tells you what to cook."

**User:** Perfect. Can you also make a short description for the GitHub repo?

**Claude:** Here you go: "A meal planning app that suggests recipes based on ingredients you already have at home. Built with React and Node.js."

That is short enough for GitHub's description field. Want me to save the README to your project now?

**User:** Yes, save it.

**Claude:** Done. The README is saved as `README.md` in your project root. The Twitter post and short description are not saved as files since you will just copy and paste them, but I can save those too if you want.

## What It Produces

- **A README file** customized for your project and audience. Includes a project title, description, features, setup instructions, tech stack, and any additional sections that make sense (like "Why I Built This" or "Contributing"). Not a generic template, but a real document that describes your actual project.
- **A short description** of one or two sentences, suitable for GitHub repo descriptions, portfolio entries, LinkedIn project sections, or anywhere you need a brief summary.
- **A social media post** with a hook, a plain-English explanation of what the project does, and a call to action. Tailored to the platform and audience you specify.

## Tips and Common Questions

1. **Tone adjusts to your audience.** Tell the skill who you are writing for. A post for developer friends will emphasize the technical challenges. A post for potential users will emphasize the problem it solves. A README for hiring managers will highlight your skills.

2. **It matches your voice.** The skill pays attention to how you describe your project in conversation and uses similar language in the outputs. If you are casual and funny, the results will reflect that. If you are straightforward and professional, the tone will match.

3. **You can revise as many times as you want.** Nothing is saved or published until you approve it. Ask for a different tone, more detail, less detail, or a complete rewrite.

4. **Screenshots and images are prompted but not created.** The skill will remind you to add screenshots and suggest where to place them, but it cannot take screenshots for you. It will leave placeholder spots in the README.

5. **Works even without a live URL.** You do not need to have deployed your project first. The skill can create a README and description for a project that only runs locally.

## Related Skills

- `/dumdum:put-it-online` - Deploy your project first so you have a live link to include in your README and social posts.
- `/dumdum:save-progress` - Save your progress after the README is added to your project, so the documentation is included in your checkpoint.
