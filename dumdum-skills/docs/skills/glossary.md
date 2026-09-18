# Glossary (`/dumdum:glossary`)

**Phase:** Learn

## What It Does

Glossary scans your entire project and builds an alphabetical dictionary of every technical term it finds. Each entry includes a plain-English definition, the location where the term appears in your project, and a real-world analogy to help the concept stick. It also groups related terms together so you can see how different pieces of the puzzle connect.

When you are learning to build software, the hardest part is often the vocabulary. You open a file and see words like `package.json`, `middleware`, `useState`, `.gitignore`, and `env`. Each one means something specific, but nobody explains them when you first encounter them. This skill fills that gap by identifying every term that might be unfamiliar and explaining it in plain English.

The glossary is not limited to code keywords. It covers file names (what is `package.json` and why does it exist?), configuration files (what does `.eslintrc` do?), dependencies (what is `express` and why is it listed in your project?), file extensions (what does `.jsx` mean?), and terminal commands (what does `npm install` actually do?). If it appears in your project and a beginner might not recognize it, the glossary includes it.

After building the glossary, the skill offers to save it as a `GLOSSARY.md` file in your project. This becomes a reference you can check anytime without running the skill again. It is also helpful if someone else looks at your project and wants to understand the terminology.

The "related terms" groupings are particularly useful. For example, `npm`, `package.json`, `node_modules`, and `dependencies` are all connected. The glossary groups them together and explains how they relate, so you understand the ecosystem rather than isolated definitions.

## Example Conversation

**User:** `/dumdum:glossary`

**Claude:** Let me scan your entire project and identify every technical term. This will take a moment since I am looking at every file, folder name, configuration, and dependency.

**Claude:** I found 47 technical terms in your project. Here is the complete glossary, organized alphabetically. I will show the first few entries, and you can ask me to continue or jump to any letter.

---

**`.env`** (file)
*Found in: project root*
A file that stores secret settings for your project, like passwords and API keys. Think of it like a locked drawer in your desk where you keep private notes. Your code reads from this file, but it should never be shared publicly.
*Related terms: environment variable, .gitignore*

**`.gitignore`** (file)
*Found in: project root*
A list of files and folders that git should not save. Think of it like telling a filing clerk "do not file these papers." You use it to keep things like `.env` files, `node_modules`, and other generated files out of your save history.
*Related terms: git, .env, node_modules*

**`axios`** (dependency)
*Found in: package.json, used in src/services/api.js*
A library that makes it easy to send requests to APIs. Think of it like a pre-addressed envelope. Instead of writing out the full mailing details every time, axios gives you shortcuts for common request types. It is an alternative to the built-in `fetch` function.
*Related terms: API, fetch, HTTP request*

---

Want me to continue through the alphabet, or would you like to jump to a specific term?

**User:** Keep going. Show me a few more.

**Claude:** ---

**`component`** (React concept)
*Found in: src/components/ (12 files)*
A reusable piece of your user interface. Think of it like a LEGO brick. Each component is a self-contained block (a button, a navigation bar, a recipe card) that you can combine to build a full page. In your project, `RecipeCard.jsx` and `SearchBar.jsx` are both components.
*Related terms: JSX, props, state*

**`dependencies`** (section in package.json)
*Found in: package.json*
A list of external libraries your project needs to run. Think of it like a recipe's ingredient list. Before you can cook, you need to have all the ingredients. Before your project can run, it needs all the dependencies installed. Running `npm install` downloads them.
*Related terms: npm, node_modules, package.json, devDependencies*

**`Express`** (dependency)
*Found in: package.json, used in server/index.js*
A framework for building web servers in Node.js. Think of it like a restaurant's floor plan and workflow system. It gives you a structure for receiving customer orders (requests), routing them to the right kitchen station (route handlers), and sending back the finished dishes (responses).
*Related terms: route, middleware, Node.js, API*

---

**User:** This is really helpful. What about "middleware"? I see that in my server code.

**Claude:** ---

**`middleware`** (Express concept)
*Found in: server/index.js (lines 8-15)*
A function that runs between receiving a request and sending a response. Think of it like a security checkpoint at an airport. Before you reach your gate, you pass through security, show your ID, and get your bags scanned. Middleware does similar checks: verifying login status, parsing incoming data, or logging requests. In your project, `express.json()` on line 9 is middleware that reads incoming JSON data so your routes can use it.
*Related terms: Express, route, request, response*

---

**User:** Can you save this as a file in my project?

**Claude:** I will save the complete glossary with all 47 terms as `GLOSSARY.md` in your project root. Done. You can open that file anytime to look up a term without running this skill again.

**User:** Are the related terms grouped anywhere?

**Claude:** Yes, at the bottom of the glossary file I added four "Related Terms" groups:

1. **The npm ecosystem:** npm, package.json, node_modules, dependencies, devDependencies, scripts
2. **React building blocks:** component, JSX, props, state, useState, useEffect, hooks
3. **Server concepts:** Express, route, middleware, API, endpoint, request, response, HTTP
4. **Git and version control:** git, .gitignore, commit, branch, repository

Each group has a short paragraph explaining how the terms work together as a system.

## What It Produces

- **An alphabetical glossary** containing every technical term found in the project. Each entry includes:
  - The term and what type of thing it is (file, concept, dependency, command, etc.)
  - Where it appears in the project (file path and sometimes line number)
  - A plain-English definition written for someone with no programming background
  - A real-world analogy to help the concept stick
  - A list of related terms for further exploration
- **Related terms groups** at the end, clustering connected concepts and explaining how they fit together as a system.
- **An optional `GLOSSARY.md` file** saved to the project root for future reference.

## Tips and Common Questions

1. **It covers everything, not just code.** File names, folder structures, config files, dependencies, file extensions, terminal commands, and code concepts are all included. If it appears in your project and might be unfamiliar, it gets an entry.

2. **You do not need to read the whole thing at once.** The glossary is a reference document. Scan through it to get a sense of the vocabulary, then come back to look up specific terms when you encounter them.

3. **The saved file stays up to date if you rerun the skill.** If you add new dependencies or introduce new concepts, run the skill again and it will regenerate the glossary with the new terms included.

4. **Ask about any term for a deeper explanation.** If a glossary entry is not detailed enough, use `/dumdum:teach-me` with that term to get the full three-layer teaching treatment.

5. **Related terms groups reveal the big picture.** Individual definitions tell you what each term means. The groups tell you how they work together, which is often more valuable for understanding the overall system.

## Related Skills

- `/dumdum:teach-me` - Use this for a deeper, multi-layered explanation of any single concept from the glossary. The glossary gives you the quick definition, and teach-me gives you the full lesson.
- `/dumdum:explain-it` - Use this to have a specific file or function explained line by line. The glossary defines terms in isolation, while explain-it shows how they work together in actual code.
