# Pick Tools

**Command:** `/dumdum:pick-tools`

## What It Does

This skill helps you choose the right technology for your project, with everything explained in plain English. Claude asks a few questions about what you are building, then recommends a specific set of tools: a programming language, a framework (a starter kit that saves you time), a database (if your project needs to remember things), and hosting (if your project needs to be on the internet). Every recommendation comes with a clear explanation of what it is and why it is the right fit.

## When to Use It

Use this when you know what you want to build but are not sure what technology to use. You do not need any prior knowledge. Claude will explain everything using everyday analogies, not technical terms.

## Example Conversation

> **You:** I want to build a website where people can sign up and track their workouts.
>
> **Claude:** Got it. Will it just be you using it, or will other people sign up too?
>
> **You:** Other people. Maybe a few hundred eventually.
>
> **Claude:** Since you need user accounts and saved data, I would recommend Next.js as your framework (a starter kit for building modern websites), Supabase for your database (it handles storing data and user sign-ups), and Vercel for hosting (it puts your site on the internet). Here is why this combination works well for your project.
>
> **You:** I have heard of React. Is that the same thing?

## What You Get at the End

A **tool choices summary** that includes:

- The recommended programming language, framework, database, and hosting
- Each one explained in plain English with a short reason for why it was chosen
- A note on why these tools work well together for your specific project

## Suggested Next Skills

- `/dumdum:start-project` to set up your project using these tools
- `/dumdum:steps` to plan the build order before jumping in
