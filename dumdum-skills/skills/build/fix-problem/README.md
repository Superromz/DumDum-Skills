# Fix Problem

**Command:** `/dumdum:fix-problem`

## What it does

Finds and fixes what is going wrong in your project. You describe the problem in plain English, or paste an error message, and it tracks down the cause, applies a fix, and explains what happened so you understand it.

## When to use it

Something is broken, showing an error, or not behaving the way you expected. You are not sure what went wrong or where to look.

## Example conversation

> **You:** /dumdum:fix-problem
>
> **Claude:** What is going wrong? You can describe the problem, paste an error message, or both.
>
> **You:** When I click the submit button nothing happens. No error, just nothing.
>
> **Claude:** I found the issue. The form was missing an event handler on the submit button. I have connected it now, and here is what was happening and why.

## What you get at the end

A working fix applied to your project, with a plain-English explanation of what was wrong and how it was resolved.

## Suggested next skills

- `/dumdum:test-it` to verify the fix and check for other issues
- `/dumdum:review-it` to look at the whole project for anything else that needs attention
