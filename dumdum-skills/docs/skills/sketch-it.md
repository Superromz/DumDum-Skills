# Sketch It: Walk Through Your Screens and Map the Flow

**Command:** `/dumdum:sketch-it`
**Phase:** Plan

## What It Does and Why

Before you build a single screen, you should know what every screen looks like and how users move between them. The sketch-it skill helps you do exactly that. It walks through your app screen by screen, drawing simple ASCII layouts so you can see the structure, then connects all the screens into a navigation map.

When you run `/dumdum:sketch-it`, Claude starts with the most important screen: the first thing your users see when they open the app. Using plain-text boxes and lines, Claude draws a rough layout showing where the main elements go. Headers, buttons, lists, input fields. These are not pixel-perfect designs. They are quick sketches meant to answer the question "what is on this screen and where does it go?"

After each screen, Claude asks what happens next. When someone taps that button, where do they go? When they finish filling out that form, what do they see? This is how the screen map takes shape. Each screen connects to the next through the actions a user takes. By the end, you have a complete picture of every screen in your first version and the paths users take through them.

This skill is valuable because it catches problems early. You might realize that a critical flow takes six screens when it should take two. You might notice that there is no way to get back to the home screen from a certain page. You might discover that you forgot an entire screen, like a confirmation page after a purchase. These are much cheaper to fix in a text sketch than in working code.

The sketches Claude produces are intentionally rough. They use characters like dashes, pipes, and brackets to represent interface elements. The point is structure and flow, not beauty. If you want high-fidelity designs, that comes later. Right now, you just need to know what goes where.

## Example Conversation

**You:** `/dumdum:sketch-it`

**Claude:** I found your idea summary and build checklist for "Building Lending Library." Let me start with the first screen a user would see. Since login is in your Must Have list, the first screen is probably a login page. Does the app open to a login screen, or to a browse screen with a login prompt?

**You:** Login screen first. Just email and password, nothing fancy.

**Claude:** Here is a simple login screen:

```
+----------------------------------+
|        Building Lending          |
|            Library               |
|                                  |
|   [  Email address           ]   |
|   [  Password                ]   |
|                                  |
|   [ -------- Log In -------- ]   |
|                                  |
|   Don't have an account?         |
|   Sign up here                   |
+----------------------------------+
```

After someone logs in, where do they land?

**You:** A list of items available to borrow.

**Claude:** Good. Here is the browse screen. I am assuming a simple list with item names and who owns them:

```
+----------------------------------+
|  Available Items          [+Add] |
+----------------------------------+
|  > Power Drill                   |
|    Dave, Apt 4B                  |
|  -  -  -  -  -  -  -  -  -  -   |
|  > Large Stockpot                |
|    Maria, Apt 2A                 |
|  -  -  -  -  -  -  -  -  -  -   |
|  > Folding Table                 |
|    Susan, Apt 1C                 |
|  -  -  -  -  -  -  -  -  -  -   |
|  > Carpet Cleaner                |
|    Dave, Apt 4B                  |
+----------------------------------+
|  [Browse]   [My Items]   [Inbox] |
+----------------------------------+
```

I added a bottom navigation bar with three tabs: Browse, My Items, and Inbox. Does that feel right, or would you organize it differently?

**You:** That looks good. What happens when they tap on an item?

**Claude:** Tapping an item opens the detail screen:

```
+----------------------------------+
|  < Back          Power Drill     |
+----------------------------------+
|                                  |
|  Owner: Dave, Apt 4B             |
|  Condition: Good                 |
|  Notes: "DeWalt 20V, comes      |
|   with two batteries"            |
|                                  |
|  [ --- Request to Borrow --- ]   |
|                                  |
+----------------------------------+
```

When someone taps "Request to Borrow," should they type a message, or just send a quick request?

**You:** Let them add a short message, like "Need it Saturday for a shelf project."

**Claude:** Got it. After they tap the button, a small message field appears and then they confirm. Let me also sketch the My Items tab and the Inbox tab, then I will map how all these screens connect.

**You:** Sounds good, go ahead.

**Claude:** Here is the My Items screen and the Inbox screen. [Claude draws both.] Now here is the full screen map showing how users move between screens:

```
Login --> Browse (items list)
            |
            +--> Item Detail --> Request Form --> Confirmation
            |
            +--> My Items --> Add Item Form
            |
            +--> Inbox --> Request Detail --> Approve / Decline
```

I saved everything to your project. You have ASCII sketches for all six screens plus this navigation map.

## What It Produces

The skill creates ASCII sketches and a screen map, typically saved to a screens directory or a single document. The output includes:

- **Individual screen sketches:** One ASCII drawing per screen showing the layout of headers, buttons, text fields, lists, and other interface elements. Each sketch includes a short note about what the screen does and what actions are available.
- **Screen map:** A text-based diagram showing every screen and the connections between them. Arrows indicate how users navigate from one screen to another, labeled with the action that triggers the transition (like "tap item" or "submit form").
- **Screen inventory:** A numbered list of all screens with one-line descriptions, useful as a quick reference when you start building.

The sketches use only plain text characters. They are meant to be read in any text editor or terminal, with no special software required.

## Tips and Common Questions

- **Start with the first screen users see.** Whether that is a login page, a landing page, or a dashboard, begin where the user begins. Claude will guide you forward from there.
- **This works best after break-it-down.** If Claude knows your Must Have features, it can make sure every feature has a screen and every screen supports a feature. Without that context, you might miss screens.
- **Focus on structure, not beauty.** These sketches are about what goes on each screen and how screens connect. Colors, fonts, and exact spacing come later. Do not worry about making the ASCII art look polished.
- **You can skip screens you are unsure about.** If you do not know what a settings page should look like, just tell Claude to skip it. You can come back to it later.
- **Count your screens.** A good first version usually has 5-10 screens. If you are above 15, you might be including too much for a first release.

## Related Skills

- `/dumdum:steps` : Turn your screens and features into an ordered build plan with milestones.
- `/dumdum:start-project` : Create the actual project files based on your screen map and chosen tools.
- `/dumdum:pick-tools` : Choose the technologies that will bring these screen sketches to life.
