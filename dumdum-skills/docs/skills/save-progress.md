# Save Progress (`/dumdum:save-progress`)

**Phase:** Ship

## What It Does

Save Progress creates a checkpoint of your work, similar to a save point in a video game. Behind the scenes, it uses git to take a snapshot of every file in your project at that moment. If anything goes wrong later, you can always go back to a previous save.

You do not need to know what git is or how it works. The skill handles all of that for you. When you run `/dumdum:save-progress`, it asks you to describe what you just finished in plain English. Something like "added the login page" or "fixed the broken button." That description becomes the label on your save point, so you can look back later and remember what each save contains.

If your project has never been saved before, the skill quietly sets up everything git needs in the background. You will not see any technical output or confusing messages. It also checks for sensitive files, like passwords or API keys, and warns you before including them. Your saves stay on your computer unless you explicitly ask to push them somewhere else.

Every time you save, the skill also shows you a short history of your recent save points. This gives you a sense of progress and helps you remember what you have already finished. Think of it as a timeline of your project's life.

The skill never pushes your code to GitHub, GitLab, or any other remote service without your permission. It only creates local save points on your machine. If you want to share your code online, use the `/dumdum:put-it-online` skill instead.

## Example Conversation

**User:** `/dumdum:save-progress`

**Claude:** I will save a checkpoint of your project. First, let me look at what has changed since your last save.

**Claude:** I can see you have made changes to 3 files: `index.html`, `styles.css`, and `app.js`. You also added a new file called `about.html`. Can you describe what you worked on in a sentence or two?

**User:** I built the about page and styled it to match the homepage.

**Claude:** Got it. I will save this checkpoint with the description "Built the about page and styled it to match the homepage." One moment.

**Claude:** I noticed a file called `.env` in your project. This file sometimes contains passwords or secret keys. I will leave it out of the save to keep your secrets safe. If you are sure it does not contain anything sensitive, let me know and I will include it.

**User:** Yeah, leave it out. That's fine.

**Claude:** Done. Your progress is saved. Here is your recent save history:

- **Save 3** (just now): Built the about page and styled it to match the homepage
- **Save 2** (yesterday): Added navigation bar and footer
- **Save 1** (2 days ago): Initial project setup with homepage

You now have 3 save points. You can come back to any of them if you ever need to undo something.

**User:** What if I mess something up later?

**Claude:** Just run `/dumdum:save-progress` again and tell me you want to go back to a previous save. I will show you the list and let you pick which one to restore. Nothing is ever truly lost once it has been saved.

## What It Produces

- **A saved checkpoint** containing every file in your project at that moment, labeled with your plain-English description and a timestamp.
- **A history of recent saves** showing the last several checkpoints with their descriptions, so you can track your progress over time.
- **Warnings about sensitive files** if any are detected, giving you the chance to exclude them before saving.

## Tips and Common Questions

1. **You do not need to install git first.** If git is not set up in your project, the skill handles the initial setup automatically. You will not see any technical configuration steps.

2. **Save often.** There is no limit to how many checkpoints you can create. A good habit is to save every time you finish something that works, even if it is small. That way you always have a recent working version to fall back on.

3. **Sensitive files are flagged automatically.** Files like `.env`, `credentials.json`, and anything that looks like it might contain secrets will trigger a warning. The skill never includes them without your explicit permission.

4. **Saves stay on your computer.** Nothing is uploaded or shared online. Your save points live entirely on your local machine unless you choose to push them using another tool.

5. **You can undo mistakes.** If you break something after a save, you can restore a previous checkpoint. Just run the skill again and ask to go back.

## Related Skills

- `/dumdum:put-it-online` - After saving your progress locally, use this skill to deploy your project to the web so other people can see it.
- `/dumdum:add-feature` - Build something new, then save your progress once it is working. These two skills work well together as a build-then-save cycle.
