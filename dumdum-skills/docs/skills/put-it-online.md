# Put It Online (`/dumdum:put-it-online`)

**Phase:** Ship

## What It Does

Put It Online takes your project from your computer and puts it on the internet so anyone with a link can visit it. It walks you through the entire process step by step, using free hosting services like Vercel, Railway, or Render. You do not need to understand servers, domains, or deployment pipelines. The skill explains every step in plain English and handles the technical details.

Before deploying, the skill checks your project for common problems that could cause the deployment to fail. It looks for build errors, missing files, and configuration issues. If something needs to be fixed first, it tells you exactly what to do. This saves you from the frustrating experience of deploying a broken project and seeing a confusing error page.

The skill always starts with free hosting tiers. You will never be asked to enter a credit card or pay for anything unless you specifically want to upgrade later. Most small projects, including personal sites, portfolios, and side projects, fit comfortably within the free limits of these hosting services.

If your project needs environment variables (settings that should not be visible in your code, like API keys), the skill helps you set those up on the hosting platform too. It explains what each variable does and why it needs to be configured separately from your code.

Once deployment is complete, you get a live URL that you can share with anyone. The skill also explains how to update your site later when you make changes. Your project is now on the internet for the world to see.

## Example Conversation

**User:** `/dumdum:put-it-online`

**Claude:** Let me look at your project to figure out the best way to put it online.

**Claude:** Your project is a React app with a Node.js backend. For this type of project, I would recommend Vercel for the frontend and Railway for the backend. Both have free tiers that should work well for you. Do you have accounts on either of these services?

**User:** No, I have never used either one.

**Claude:** No problem. Let us start with Vercel for the frontend since it is the simpler part. Go to vercel.com and click "Sign Up." You can sign up with your GitHub account if you have one, or use your email. Let me know when you have created an account.

**User:** Okay, I signed up with my email.

**Claude:** Before we deploy, let me check your project for any issues. One moment.

**Claude:** I found one small problem. Your project references an environment variable called `REACT_APP_API_URL`, but it is set to `http://localhost:3001` in your `.env` file. Once your backend is online, we will need to update this to the live URL. For now, let us get the frontend deployed first. I will walk you through installing the Vercel command line tool. Run this command in your terminal: `npm i -g vercel`

**User:** Done. What next?

**Claude:** Now run `vercel` in your project folder. It will ask you a few questions. For "Which scope?" pick your account name. For "Link to existing project?" say No. For "What's your project's name?" you can keep the default or type something custom. For the other questions, the defaults should work. Let me know what happens.

**User:** It deployed! It gave me a URL.

**Claude:** Excellent. That URL is your live frontend. Now let us set up Railway for your backend so the API calls work too. Go to railway.app and create an account there.

**User:** I am on Railway now. What do I do?

**Claude:** Click "New Project," then "Deploy from GitHub repo" if your code is on GitHub, or "Empty Project" if it is not. Since your backend is in the `/server` folder, we will set it up to deploy just that part. Let me walk you through the configuration.

## What It Produces

- **A live URL** where anyone on the internet can visit your project. This is a real, working website hosted on a professional platform.
- **Deployment configuration** tailored to your specific project type (static site, React app, Node.js server, Python app, etc.).
- **Environment variable setup** on the hosting platform, ensuring your secrets and configuration values are properly configured without being exposed in your code.
- **Update instructions** explaining how to redeploy when you make changes to your project later.

## Tips and Common Questions

1. **Always starts with free tiers.** You will never be pushed toward a paid plan. The free tiers on Vercel, Railway, and Render are generous enough for personal projects, demos, and small apps.

2. **Build errors are caught early.** The skill runs a build check before deploying to make sure your project compiles successfully. If there are errors, it helps you fix them before you attempt to deploy.

3. **Environment variables are handled carefully.** If your project uses `.env` files or references environment variables, the skill identifies each one and helps you configure it on the hosting platform. It also explains which values need to change for production (like switching from `localhost` URLs to live URLs).

4. **You can update your site later.** Deploying is not a one-time event. The skill explains how to push updates whenever you change your project. Most hosting services can be configured to update automatically when you save your progress.

## Related Skills

- `/dumdum:tell-people` - Once your project is online, use this skill to create a README, project description, and social media post so you can share the link with the right context.
- `/dumdum:save-progress` - Always save your progress before deploying. That way you have a checkpoint of the exact version that went live.
