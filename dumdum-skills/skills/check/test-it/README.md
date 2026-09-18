# Test It

**Command:** `/dumdum:test-it`

## What it does

Checks whether your project works correctly and gives you a clear health report in plain language. It looks for broken features, missing pieces, and common mistakes, then tells you exactly what passed, what failed, and what was not tested.

## When to use it

You just finished building something or making changes and want to make sure everything actually works before moving on.

## Example conversation

> **You:** /dumdum:test-it
>
> **Claude:** I will check your project for problems. Do you want me to test everything, or focus on a specific part?
>
> **You:** Test everything.
>
> **Claude:** Here is your health report. The homepage loads correctly, the form submits data, but the filter dropdown is not updating the list. I also found one broken link in the footer.

## What you get at the end

A health report organized into three sections: what works, what has problems, and what was not tested. Each problem includes a plain-English description.

## Suggested next skills

- `/dumdum:fix-problem` to fix any issues the test found
- `/dumdum:review-it` to get a deeper look at code quality and missing pieces
