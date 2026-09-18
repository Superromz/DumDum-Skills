# Break It Down

**Command:** `/dumdum:break-it-down`

## What It Does

This skill takes your idea and splits it into small, buildable pieces, then ranks those pieces by importance. Big ideas can feel overwhelming. This skill turns one big thing into a list of smaller things you can tackle one at a time, so you always know what to work on next.

## When to Use It

Use this when you have a clear idea of what you want to build but are not sure where to start. It is especially helpful after running `/dumdum:idea` or `/dumdum:who-is-it-for`, since Claude can use that earlier work to prioritize better.

## Example Conversation

> **You:** I want to build a recipe-sharing website.
>
> **Claude:** Here is how I would break that into pieces: a way to browse recipes, a way to add your own recipe, user accounts so people can save favorites, and a search bar to find recipes by ingredient. Does this list feel right?
>
> **You:** Yes, but I also want people to leave comments on recipes.
>
> **Claude:** Good one, I will add that. Now let's figure out what to build first. I would put "browse recipes" and "add a recipe" in the Must Have group, because without those, there is nothing to use. Comments and search feel more like Should Have. What do you think?
>
> **You:** That makes sense. Favorites can wait too.

## What You Get at the End

A **build checklist** with every feature sorted into three groups:

- **Must Have** - the pieces to build first, because nothing works without them
- **Should Have** - the pieces that make the project actually useful and enjoyable
- **Nice to Have** - extras you can add later without anyone missing them at first

The checklist also calls out which one or two pieces to start with, and why.

## Suggested Next Skills

- `/dumdum:steps` to turn this checklist into an ordered, step-by-step build plan
- `/dumdum:start-project` to jump in and start building right now
