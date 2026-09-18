# Steps

**Command:** `/dumdum:steps`

## What It Does

This skill takes your feature list and turns it into an ordered build plan. Claude figures out what needs to be built first, second, and third, based on what depends on what. The plan is grouped into milestones, which are checkpoints where you stop, try out what you have built, and make sure everything works before moving on.

## When to Use It

Use this when you have a list of features and want to know the best order to build them. It works especially well after running `/dumdum:break-it-down`, `/dumdum:sketch-it`, or `/dumdum:pick-tools`, since Claude can pull from that earlier work.

## Example Conversation

> **You:** I have my feature list ready. Can you put it in order?
>
> **Claude:** I found your feature list. Here is the plan. Milestone 1 is "Get the basics running," which starts with project setup, then the main page layout, then the product list. After that, you will have a working page you can open in your browser.
>
> **You:** Can we move search earlier? I think that is really important.
>
> **Claude:** Search needs the product list to already exist, because you can not search through something that is not there yet. So it has to come after the product list, but I can put it right after. I will move it to the first step of Milestone 2.
>
> **You:** That works.

## What You Get at the End

A **milestone-based build plan** that includes:

- Ordered steps, each with a short description and a plain English explanation of why it comes at that point
- Milestones that group steps into checkpoints, so you can see and test your progress along the way
- Effort labels (Quick, Medium, or Big piece) for each step, so you know what to expect

## Suggested Next Skills

- `/dumdum:start-project` to begin building and work through the plan step by step
