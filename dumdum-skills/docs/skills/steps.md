# Steps: Turn Features Into Milestones With a Build Plan

**Command:** `/dumdum:steps`
**Phase:** Plan

## What It Does and Why

You know what you are building and you know the pieces. Now you need to know the order. The steps skill takes your features and organizes them into milestones, each one a meaningful checkpoint where you can stop, look at what you have built, and feel good about your progress. It answers the question every builder asks: "What do I do first?"

When you run `/dumdum:steps`, Claude looks at your features (from `build-checklist.md` if it exists, or by asking you) and groups them into milestones. A milestone is a set of steps that, when finished, gives you something you can actually use or show someone. Not a half-finished screen. Not a database with no interface. A working thing, even if it is small. The first milestone might be as simple as "a page that shows a list of items," but that is a real, working piece of your project.

Each step within a milestone comes with two important pieces of information. The first is "Why Now," a short explanation of why this step belongs here and not earlier or later. The second is "Effort," rated as Quick (under an hour), Medium (a few hours), or Big (a day or more). These are not precise time estimates because precise estimates are almost always wrong. They are rough sizes that help you set expectations and plan your energy.

The skill also builds in checkpoints. After each milestone, Claude describes what you should have and how to verify it works. "Open the app. You should see a list of three items. Click one. You should see its details." These checkpoints prevent the common problem of building for hours without checking whether anything actually works.

The order of milestones is deliberate. Claude puts the foundation first (the parts that other parts depend on), followed by the core experience (the reason people use your product), then the supporting features (the things that make it better). This progression means you always have something functional, even if you stop partway through.

## Example Conversation

**You:** `/dumdum:steps`

**Claude:** I found your build checklist for "Building Lending Library." You have 6 Must Have pieces, 3 Should Have pieces, and 3 Nice to Have pieces. Let me turn the Must Have pieces into milestones. First, a question: when you picture finishing for the day and feeling good about progress, what would you want to see?

**You:** I would want to open the website and see it actually doing something. Even if it is just a list of items.

**Claude:** That matches what I was thinking. Let me build the plan around that. Your first milestone is about getting something visible as fast as possible.

**Milestone 1: See the shelves.** The goal is a working page that shows a list of lendable items.

Step 1: Set up the project. Create the folder, install Next.js, make sure it runs locally.
Why Now: Everything depends on this. Nothing else can happen without a working project.
Effort: Quick.

Step 2: Create a sample data file. A simple list of 3-4 fake items with names, owners, and descriptions.
Why Now: You need data to display before building a real database.
Effort: Quick.

Step 3: Build the browse page. A screen that reads the sample data and shows each item in a list.
Why Now: This is the payoff. You can open the browser and see your app showing items.
Effort: Medium.

Checkpoint: Open your browser to localhost:3000. You should see a page with a list of items. Each item shows its name and owner. Does this plan for Milestone 1 make sense?

**You:** Yes. What is next?

**Claude:** **Milestone 2: Real data, real people.** The goal is to replace fake data with a real database and add user accounts.

Step 4: Set up Supabase. Create a project, define tables for users and items.
Why Now: You have proved the page works with fake data. Now make it real.
Effort: Medium.

Step 5: Connect the browse page to Supabase. Replace the sample data file with live database queries.
Why Now: The page already works. You are just swapping where the data comes from.
Effort: Medium.

Step 6: Add sign-up and login. Use Supabase authentication so each person has an account.
Why Now: You need users before you can track who owns what and who borrows what.
Effort: Medium.

Checkpoint: Create two test accounts. Log in as one, see the items list. Log out, log in as the other, see the same list. Both accounts work independently.

**You:** Good. Keep going.

**Claude:** **Milestone 3: The core loop.** This is where borrowing actually works.

Step 7: Build the "add item" form. A logged-in user can list something they are willing to lend.
Why Now: The browse page needs items. Now real users can create them.
Effort: Medium.

Step 8: Build the item detail page. Tapping an item shows its full information and a "Request to Borrow" button.
Why Now: Users can see items but cannot act on them yet. This adds the action.
Effort: Medium.

Step 9: Build the request flow. Tapping "Request to Borrow" sends a request to the item owner with an optional message.
Why Now: This is the core transaction. Without it, the app is just a catalog.
Effort: Big.

Step 10: Build the inbox. Owners see incoming requests and can approve or decline them.
Why Now: Requests need responses. This closes the loop.
Effort: Big.

Checkpoint: Log in as User A, list a drill. Log in as User B, request the drill with a message. Log back in as User A, see the request in your inbox, approve it. The full borrow cycle works.

**You:** That is really clear. What about notifications?

**Claude:** **Milestone 4: Stay informed.** Simple in-app notifications so nobody misses a request.

Step 11: Add notification badges. A red dot on the Inbox tab when there are unread requests.
Why Now: Without this, people have to keep checking their inbox manually.
Effort: Quick.

Step 12: Add a notification list. A simple page showing recent activity: "Maria requested your drill," "Dave approved your request."
Why Now: Badges tell users something happened. The list tells them what.
Effort: Medium.

Checkpoint: Complete a full borrow cycle. Both users should see notifications about each step.

I saved the complete build plan. Four milestones, twelve steps, with effort estimates and checkpoints for each milestone.

## What It Produces

The skill creates a milestone-based build plan. The document includes:

- **Milestones:** Numbered groups of steps, each with a descriptive name and a one-sentence goal. Milestones are ordered so that each one builds on the last.
- **Steps within each milestone:** Numbered steps with a short name, a description of what to do, a "Why Now" explanation of the ordering, and an "Effort" rating (Quick, Medium, or Big).
- **Checkpoints:** A verification section after each milestone describing exactly what you should see and test to confirm everything works before moving on.
- **Milestone summary:** A quick reference list at the top or bottom showing all milestones, their step counts, and total effort.

The plan covers your Must Have features. Should Have and Nice to Have features are noted as future milestones but not broken into detailed steps yet.

## Tips and Common Questions

- **Quick, Medium, and Big replace time estimates.** Quick means under an hour for someone with guidance. Medium means a few hours. Big means a day or more. These are rough sizes, not promises.
- **The first milestone should be small and satisfying.** You want to see something working as fast as possible. If Milestone 1 has more than 3-4 steps, it is probably too big.
- **You can rearrange milestones.** If Claude puts login in Milestone 1 and you would rather see data on screen first, say so. The order is a recommendation, not a rule.
- **Checkpoints are not optional.** Skipping them is the fastest way to build something that looks right but does not actually work. Take two minutes to test at each checkpoint.
- **This plan will change.** That is expected. As you build, you will learn things that shift priorities. Run steps again when your understanding changes.

## Related Skills

- `/dumdum:start-project` : Begin Milestone 1 by creating the actual project files and folder structure.
- `/dumdum:break-it-down` : If you have not sorted your features into Must Have, Should Have, and Nice to Have yet, do that first.
- `/dumdum:pick-tools` : If you have not chosen your technologies yet, do that before planning steps so the plan can reference specific tools.
