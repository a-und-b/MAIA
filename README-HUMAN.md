# README for Humans Collaborating with Your LLM Coding Agent

## 👋 Introduction: Your AI Pair Programmer

Welcome! This guide is designed to help you (a human software developer) collaborate effectively with me, your LLM-based AI coding assistant. Think of me as a super-powered, highly responsive pair programmer who's always learning *from your guidance in this session*. My goal is to augment your skills, speed up your development process, and help tackle complex coding tasks.

Understanding a bit about how I "think" and operate, and adopting some best practices, can make our partnership incredibly productive and even fun!

## 🧠 Core Principles of Interacting with Me

These are the foundational ideas to keep in mind for a smooth workflow:

### 1. Be Clear and Specific: My "Logical Mind"
I don't have intuition or "common sense" like humans do. I thrive on precise, unambiguous instructions.

*   **Technical Detail:** I work best with clear prompt engineering. This includes:
    *   **Role-Playing:** "Act as a senior Python developer specializing in API design."
    *   **Few-Shot Examples:** Providing 1-2 examples of what you want (input/output) helps me understand the desired pattern.
    *   **Chain-of-Thought (for complex tasks):** Ask me to "think step by step" or "explain my reasoning" before providing a final answer. This helps me break down problems and often leads to better results.
*   **Best Practice:**
    *   **Atomic Tasks:** Break down larger goals into smaller, specific tasks. Instead of "Build the whole feature," try "Write a Python function that takes X and returns Y, with this signature..."
    *   **Clear Acceptance Criteria:** If you have specific requirements for the output (e.g., "The function must handle None input gracefully"), state them.

### 2. Provide Context: My "Working Memory"
I have a limited "context window" – the amount of information I can "see" at any one time from our current conversation and attached files. The more relevant context you provide, the better my responses.

*   **Technical Detail:**
    *   My **short-term memory** is our current conversation history and any files you've explicitly `@-mentioned` or I've recently read/edited.
    *   My **project-specific long-term memory** is the `memory-bank/` directory and the `.cursor/rules/` files. **You must explicitly tell me to consult these if you want me to use them.**
*   **Best Practice:**
    *   When asking about specific code, provide the file path and relevant line numbers or snippets. Use `@file_path` for this.
    *   For new features or complex changes, ensure the `memory-bank/` (especially `activeContext.md` and `productContext.md`) is up-to-date or provide a summary of requirements, business logic, and constraints.
    *   "Prime" me by asking me to read relevant files at the start of a new task.

### 3. Iterate and Refine: Our "Collaborative Dance"
I might not get things perfect on the first try, especially for complex or nuanced requests. Iteration is key.

*   **Best Practice:**
    *   View our interaction as a "prompt -> response -> feedback -> refined prompt" loop.
    *   Regularly review my suggestions, especially code changes.
    *   If my output isn't quite right, provide specific feedback and ask for a revision. "That's close, but can you change X to Y?" or "Please ensure the function also handles Z case."

### 4. Understand My Modes: "Thinking Cap" vs. "Doing Gloves"
I operate in two main modes, and it's helpful for you to be aware of them:

*   **Plan Mode:** (Default) In this mode, I focus on understanding your request, asking clarifying questions, gathering information (e.g., reading files), and proposing a plan of action. I will **not** make changes to your code in this mode.
*   **Act Mode:** When you're happy with a plan and say `ACT`, I switch to this mode to execute the plan (e.g., edit code, run commands). I'll switch back to Plan Mode after completing the actions.

*   **Why it matters:** Plan mode minimizes wasted effort and ensures we're aligned before I start making changes.

### 5. Leverage My Tools: My "Digital Hands"
I have several tools to interact with your workspace: reading files, writing/editing files, searching your codebase, running terminal commands, and searching the web.

*   **Technical Detail:** I make structured calls to these tools. If a tool "fails" from my perspective, or if its output is unexpected, I might need your help to understand why or to adjust my approach.
*   **Best Practice:** If you know a specific file needs to be read or a command needs to be run, tell me. You can also ask, "Can you search for X in the codebase?"

## 🥰 "How to Vibe" with Your LLM Agent

Getting the "feel" right makes our collaboration smoother and more enjoyable.

*   **Think of Me as a Super-Powered Intern (with Quirks):** I'm eager, can perform complex tasks quickly, and I learn rapidly *from your specific guidance in this session*. However, I need very clear direction and can sometimes miss subtleties or make "rookie mistakes" if an instruction is ambiguous or context is missing.
*   **Patience is a Virtue:** Especially when we're starting on a new type of task, there might be a bit of a learning curve as I get attuned to your needs and you get attuned to my way of responding.
*   **Positive Reinforcement is Encouraged:** If I generate code you like, or if a particular way of phrasing a request works well, letting me know helps! "That's a perfect function, thanks!" or "Yes, that output format is exactly what I need."
*   **Gentle Course Corrections are Best:** If I'm heading in the wrong direction, a simple, polite correction is most effective. "Actually, I was thinking more along the lines of X," or "Let's pause that approach; I'd like to try Y instead."
*   **Embrace the "What If?":** Use me as a sounding board. "What are the pros and cons of using a class versus a set of functions here?" or "Can you show me an alternative way to write this?" I can help you explore different solutions.
*   **Chunk Down Big Ideas:** If you have a large, complex feature in mind, let's break it down into smaller, manageable pieces. I can even help you with that decomposition.
*   **"Rubber Ducking" on Steroids:** Explaining a problem to me, even if you think you know the solution, can help clarify your own understanding. I might even ask a question that sparks a new insight for you.
*   **Share Your "Why" (Briefly):** Sometimes, a little context on *why* you're asking for something can help me generate a more appropriate response or anticipate related needs. "I need this function to be highly performant because it will be called in a tight loop."

## 📝 Best Practices for Prompts

The better your prompt, the better my response.

*   **Define Scope Clearly:** Be explicit about what you want me to do and (sometimes more importantly) what *not* to do.
*   **Provide Examples (Few-Shot Prompting):** For code generation or specific text formats, providing 1-2 examples of the desired input and output is incredibly powerful.
    *   *Example:* "I have a list of tuples like `[( 'a', 1), ('b', 2)]`. I want a dictionary like `{'a': 1, 'b': 2}`. Can you write a function for this?"
*   **Specify Desired Format/Structure:**
    *   "Please provide the output as a JSON object with keys 'name', 'version', and 'dependencies'."
    *   "Generate a Python class with a constructor and two public methods: `load_data` and `process_data`."
    *   Use delimiters (like ```json ... ``` or ```python ... ```) to separate instructions from code examples or data you provide *in your prompt*.
*   **Request Step-by-Step Breakdowns for Complex Tasks:** If a task is large, ask me to outline the steps first (this naturally happens in Plan Mode).
*   **Persona Adoption:** "Act as a cybersecurity expert and review this code for potential vulnerabilities."
*   **Standardized Templates for Common Requests (Develop Your Own!):**
    *   *Example for explaining code:* "Explain the following Python code snippet: ```python [code] ``` Focus on [e.g., its purpose, its main logic flow, potential areas for improvement]."
    *   *Example for writing a function:* "Write a Python function named `[name]` that: (1) Takes arguments: `[arg1_name: type]`, `[arg2_name: type]`. (2) Returns: `[return_type]`. (3) Purpose: [brief description]. (4) Constraints: [e.g., must not use external libraries]."

## 👀 Understanding My Responses

*   **Tool Usage Indicators:** I'll often tell you when I'm about to use a tool (e.g., "I will read the file `foo.py`," or "I will search for 'BarClass' in the codebase.").
*   **Code Edits:** When I propose code changes, I use a specific diff-like format with `// ... existing code ...` to show where changes are applied. Review these carefully.
*   **Interpreting "Confidence" vs. "Accuracy":** I might sound confident even when I'm incorrect (a "hallucination"). Always critically evaluate my responses, especially for factual claims or complex code.
*   **Potential for Errors/Hallucinations:** If my response seems nonsensical, or if I invent APIs or facts:
    *   It's often due to insufficient context or an ambiguous prompt.
    *   Try rephrasing, providing more context, or simplifying the request.
    *   Ask me for my "reasoning" or (if I used web search) for the sources I consulted.

## 🧠 Managing Memory & Continuity

As mentioned, my session memory is limited, but we have tools for project continuity:

*   **The `memory-bank/` Directory:** This is our shared, persistent knowledge base for the project.
    *   `projectbrief.md`: The project's "North Star."
    *   `productContext.md`: The "Why" and "For Whom."
    *   `systemPatterns.md`: The "How It's Built" (architecture).
    *   `techContext.md`: The "What It's Built With" (tech stack).
    *   `activeContext.md`: **Crucial for current focus.** Update this with me to reflect what we're working on *right now*.
    *   `progress.md`: Tracks overall progress and known issues.
*   **`.cursor/rules/`:** Project-specific coding conventions and patterns I should follow.
*   **Best Practice:**
    *   At the start of a new major task or session, ask me to "review the Memory Bank," or specific files like `activeContext.md`.
    *   Help me keep `activeContext.md` and `progress.md` up-to-date by summarizing decisions or next steps before we switch tasks.

## 🛠️ Troubleshooting Common Issues

*   **If I'm Stuck or Misunderstanding:**
    *   Rephrase your request. Try making it simpler or more direct.
    *   Break the problem into smaller steps.
    *   Explicitly tell me what I misunderstood. "My last request was about X, but your response focused on Y. Let's focus on X."
*   **If I'm Not Following Instructions:**
    *   Reiterate the key instruction very clearly and directly.
    *   Check if previous instructions in the conversation might be conflicting.
    *   Sometimes, starting a "fresh" line of inquiry with "Okay, new task:" can help.
*   **If My Output is Too Verbose or Too Brief:**
    *   Tell me! "Can you be more concise?" or "Please provide a more detailed explanation."

## ⚠️ A Note on My "Understanding"

I am a sophisticated pattern-matching and generation system. I don't "understand" concepts or code in the human sense. I identify patterns in the data I was trained on and in the context you provide, and I generate responses based on those patterns. This is why clear context, specific instructions, and iterative refinement are so important.

---

Happy collaborating! Let's build some great software together.