# Make It Look Good - `/dumdum:make-it-look-good`

**Phase:** Build

## What It Does and Why

Functionality gets a project working. Design is what makes people want to use it. Make It Look Good takes a working project and improves its visual appearance based on your style preferences. You do not need to know anything about design, CSS, or color theory. You just describe the vibe you want, and Claude handles the rest.

The skill works by asking you to choose a general style direction: clean, colorful, professional, bold, or warm. Each direction comes with a set of design decisions (colors, spacing, fonts, layout adjustments) that Claude applies thoughtfully across your project. "Clean" means lots of white space and minimal decoration. "Bold" means strong colors and large typography. "Warm" means soft colors and rounded edges that feel inviting. You pick the direction, and Claude makes the choices within that direction.

Every design change comes with an explanation. When Claude picks a color, you will know why. When spacing gets adjusted, you will understand the reasoning. This is not about teaching you graphic design. It is about making sure you feel in control of your project's appearance, even when Claude is making the detailed decisions. If something does not look right to you, say so. "I do not like that shade of blue" or "the buttons feel too small" are exactly the kind of feedback Claude needs.

Make It Look Good is careful never to break functionality. Changing how something looks should never change how it works. Claude treats styling as a layer that sits on top of your working project, not something that gets tangled into the logic. Before finishing, it verifies that all features still work correctly with the new design applied.

The skill works within whatever styling setup your project already has. If you are using plain CSS, it modifies that. If your project uses a framework or component library, it works within those constraints. It does not rip out your existing approach and replace it with something different.

## Example Conversation

**You:** `/dumdum:make-it-look-good`

**Claude:** Let me take a look at your project's current design. One moment.

Okay, I see your bakery website. Right now it is using default browser styling, which means plain fonts, no color scheme, and basic layout. I can take it in several directions. Which of these sounds closest to what you want?

- **Clean** - Minimal, lots of white space, modern feel
- **Colorful** - Vibrant palette, playful energy
- **Professional** - Polished, trustworthy, corporate feel
- **Bold** - Strong colors, large text, high contrast
- **Warm** - Soft colors, rounded shapes, cozy and inviting

**You:** Warm sounds perfect for a bakery.

**Claude:** Great choice. Warm styling fits a bakery really well. Here is what I am planning:

- A soft cream background instead of plain white
- Warm brown and golden accent colors (think fresh bread tones)
- Rounded corners on buttons and cards
- A friendly, readable font for body text
- Slightly larger spacing between sections so the page feels relaxed
- Subtle shadows on menu item cards to give them a gentle lift

I will keep your existing layout structure. Just the visual layer changes. Sound good?

**You:** I like all of that. But can the accent color be more of a burgundy instead of golden?

**Claude:** Absolutely. Burgundy with cream is a classic bakery palette. I will use burgundy for buttons, headings, and accents, with golden only as a subtle highlight on hover effects. Let me apply that now.

Done. Here is what changed:

- `styles.css` - Complete style overhaul with warm palette, rounded corners, and updated typography
- `index.html` - Added a class to the menu section for better card styling
- `order.html` - Updated the form layout to match the new rounded, warm aesthetic

Refresh your browser to see the changes. The menu items now appear as soft cards with gentle shadows. Buttons are burgundy with cream text. The overall feel should be warm and inviting. What do you think?

**You:** It looks great. But the order form feels a little cramped.

**Claude:** I see what you mean. The form fields are close together and the labels are small. Let me add more vertical spacing between form fields and bump up the label size slightly.

Done. Each form field now has more breathing room, and the labels are slightly larger and use the same warm brown as the body text. The submit button also got a bit more padding so it does not feel squeezed. Refresh and take another look.

**You:** Much better. One more thing: the admin page still looks plain.

**Claude:** Good catch. I applied the warm styling to the customer-facing pages but the admin page kept its default look. Let me extend the same design system to `admin.html` now.

Done. The admin page now uses the same cream background, burgundy accents, and rounded cards. Orders show up in neat cards instead of a plain list. It still looks distinct from the customer pages (slightly more structured layout) so you can tell at a glance that you are on the admin side. Everything still works: I tested the order flow and orders still appear on the admin page correctly.

## What It Produces

- **Updated styling across the project.** All pages and components receive consistent visual improvements based on your chosen direction.
- **Design explanations.** Every choice (color, spacing, typography, layout) comes with a plain-English reason for why it was made.
- **Preserved functionality.** All features continue to work exactly as they did before the design changes. Claude verifies this before finishing.
- **A consistent design system.** Colors, fonts, spacing, and other visual elements follow a coherent pattern rather than being applied randomly.

## Tips and Common Questions

1. **Works within your existing styling setup.** If your project uses plain CSS, Claude modifies that. If it uses a framework, Claude works within its conventions. No approach is ripped out and replaced.

2. **Does not break functionality.** Design changes are applied as a visual layer. Claude verifies that all features still work after styling updates. If something breaks, it gets fixed before the skill finishes.

3. **"Try something different" is valid feedback.** If you do not like the result, just say so. Claude can adjust individual elements ("make the buttons bigger") or shift the overall direction ("actually, try professional instead of warm").

4. **You can run this skill multiple times.** Design is iterative. Run it once for the initial look, then again later when your taste evolves or you add new features that need styling.

5. **Specific feedback beats vague feedback.** "I do not like it" is okay, but "the text is hard to read against that background" helps Claude make better changes faster.

## Related Skills

- `/dumdum:test-it` - Verify that everything still works after design changes.
- `/dumdum:add-feature` - Add new functionality that will automatically inherit the current design.
- `/dumdum:start-project` - Set up a new project that you can then style with this skill.
