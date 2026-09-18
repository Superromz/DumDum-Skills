# Review It

**Command:** `/dumdum:review-it`

## What it does

Looks at your whole project and identifies problems, missing pieces, and things that could be improved. It organizes everything by how important it is, so you know what to tackle first and what can wait.

## When to use it

You want a second pair of eyes on your project before sharing it, launching it, or moving on to the next phase. Good to run after finishing a round of features or fixes.

## Example conversation

> **You:** /dumdum:review-it
>
> **Claude:** I will review your entire project. Any areas you are most concerned about?
>
> **You:** I am worried about security and whether I am missing anything obvious.
>
> **Claude:** Here is your review. Must Fix: the API key is visible in your frontend code. Should Fix: there is no error handling on the form submission. Nice to Fix: a few variable names are unclear.

## What you get at the end

A review checklist organized by severity: Must Fix (critical problems), Should Fix (important improvements), and Nice to Fix (minor polish). Each item includes a plain-English explanation.

## Suggested next skills

- `/dumdum:fix-problem` to address issues from the review
- `/dumdum:test-it` to verify your project works after making fixes
- `/dumdum:explain-it` to understand any part of the code the review flagged
