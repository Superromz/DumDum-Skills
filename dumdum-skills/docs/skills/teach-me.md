# Teach Me (`/dumdum:teach-me`)

**Phase:** Learn

## What It Does

Teach Me explains any concept using a three-layer teaching method. First, it gives you a simple analogy that connects the concept to something you already understand. Second, it adds more technical detail for a fuller picture. Third, it connects the concept directly to your project so you can see it in action. Each layer builds on the last, and you control how deep you want to go.

Programming is full of jargon that can feel like a foreign language. Words like "middleware," "state management," "API endpoint," and "dependency injection" get thrown around as if everyone already knows what they mean. This skill breaks those terms down without being condescending. It does not assume you are stupid. It assumes you are smart but have not encountered this particular idea before.

The three-layer method works because learning sticks better when it is anchored to something familiar. If you understand how a restaurant kitchen works, you can understand how a server handles requests. If you understand how a library card catalog works, you can understand how a database index works. The skill finds these bridges between what you know and what you are learning.

You can ask about anything, not just things in your project. Curious about how the internet works? How encryption protects your passwords? What "the cloud" actually means? The skill handles all of it. But when the concept does appear in your project, the third layer of the explanation points directly at the relevant code so you can see the abstract idea made concrete.

If an analogy does not click for you, just say so. The skill will try a completely different approach. Some people think visually, some think in terms of processes, and some prefer numerical examples. The skill adapts until the explanation lands.

## Example Conversation

**User:** `/dumdum:teach-me` what is an API?

**Claude:** Great question. Let me explain this in three layers.

**The simple version:** An API is like a waiter at a restaurant. You (the customer) do not go into the kitchen and cook your own food. Instead, you tell the waiter what you want, the waiter brings your order to the kitchen, the kitchen prepares it, and the waiter brings it back to you. An API is the waiter. It carries requests from one piece of software to another and brings back the response.

Want me to go deeper, or does that make sense so far?

**User:** That makes sense. Go deeper.

**Claude:** **More detail:** API stands for Application Programming Interface. It is a set of rules that define how two pieces of software can talk to each other. When your app needs data from somewhere else, like weather information, user accounts, or recipe lists, it sends a request to an API. That request follows a specific format: it includes the URL (where to send it), the method (what you want to do, like GET for reading or POST for creating), and sometimes data (like a search term).

The API receives the request, does whatever work is needed (looking up data, saving something, running a calculation), and sends back a response. The response is usually in a format called JSON, which looks like a structured list of labels and values.

Ready for how this shows up in your project?

**User:** Yeah, show me.

**Claude:** **In your project:** You actually built an API already. In your file `server/routes/recipes.js`, you have this code:

```javascript
router.get('/api/recipes/search', (req, res) => {
    const query = req.query.q;
    // ... searches the database ...
    res.json(results);
});
```

This is one API endpoint. The "waiter" analogy maps directly: your React frontend (the customer) sends a request to `/api/recipes/search?q=pasta` (tells the waiter what it wants). The Express server (the waiter) receives the request, asks the database (the kitchen) for matching recipes, and sends the results back as JSON (brings the food to the table).

Your frontend calls this API in `src/services/api.js` on line 12 with `fetch('/api/recipes/search?q=' + query)`. That fetch call is your customer placing the order.

**User:** Oh, that makes total sense now. So every route in my routes file is a different thing I can order?

**Claude:** Exactly. Each route is a different item on the menu. Your `/api/recipes/search` endpoint lets you search for recipes. Your `/api/recipes/:id` endpoint lets you get the details of one specific recipe, like ordering a specific dish by name. And when you finish building the favorites feature, `/api/favorites` will let you save and retrieve your favorite recipes, like asking the waiter to remember your usual order.

**User:** What about when people say "third-party API"?

**Claude:** That is when you use someone else's restaurant. Instead of your own server doing the work, you send a request to a completely different service. For example, if you wanted to add nutritional information to your recipes, you might call a nutrition API run by another company. Your server would send a request to their server, get the data back, and pass it along to your frontend.

You are still the customer, but now there are two restaurants involved: yours (your Express server) and theirs (the nutrition API). Your server acts as both a waiter for your frontend and a customer of the external API.

**User:** That is really clear. Thanks.

**Claude:** You are welcome. If you run into other terms that feel confusing, just run `/dumdum:teach-me` again with the new topic.

## What It Produces

- **A three-layer explanation** of any concept:
  - **Layer 1: Simple analogy.** A comparison to something from everyday life that makes the core idea click immediately.
  - **Layer 2: More detail.** The real technical explanation with proper terminology, but still in plain English. Builds on the analogy from layer 1.
  - **Layer 3: Project connection.** Points to specific files and lines in your project where this concept appears, showing you the abstract idea in concrete code you have already written or will write.
- **Follow-up answers** to any related questions that come up during the conversation.

## Tips and Common Questions

1. **You can pass the topic directly with the command.** Instead of running `/dumdum:teach-me` and waiting to be asked, you can type `/dumdum:teach-me what is a database index` to jump straight to the explanation.

2. **It works for concepts outside your project too.** Want to understand how Wi-Fi works, what blockchain is, or how a computer stores data? The skill can teach anything. It will skip the project-connection layer if the topic is unrelated.

3. **Ask for a different analogy if the first one does not click.** Everyone thinks differently. If a restaurant analogy does not resonate, say "try a different analogy" and the skill will come at it from a completely different angle, maybe using a library, a post office, or a factory instead.

4. **No question is too basic.** This skill is designed for people who are learning. Asking "what is a variable" is just as valid as asking "what is a microservice architecture." There is no judgment.

5. **Each layer is optional.** You can stop after the simple analogy if that is enough, or go all three layers deep. You control the pace.

## Related Skills

- `/dumdum:glossary` - If you want definitions for every technical term in your project all at once, use this skill to generate a complete dictionary.
- `/dumdum:explain-it` - If you want a specific piece of code explained rather than a general concept, use this skill to walk through what a file or function does line by line.
