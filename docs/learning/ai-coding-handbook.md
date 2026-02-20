# AI Coding Handbook 🚀

This handbook is your definitive guide to working effectively with AI coding assistants. It covers the infrastructure that allows the AI to act as a proactive engineer rather than just a chatbot.

---

## 🏗 1. The Infrastructure: Skills & MCP

### Skills
**Think of these as "New Brain Regions."**
- **What:** A folder-based system containing a `SKILL.md` (the "instruction manual") and often supporting scripts.
- **Why:** To teach the AI specialized processes (e.g., "How we deploy to AWS" or "How to use our internal UI library").
- **Pro-Tip:** If you find the AI repeating a mistake or forgetting a specific internal process, create a **Skill** for it.

### MCP (Model Context Protocol) 
**The "Nervous System" connecting the AI to the world.**
- **Purpose:** A standardized way for the AI to interact with your local tools and data securely.
- **Sources:**
    - **Filesystem:** How I read and edit your code.
    - **Database:** Querying schemas or live data.
    - **External:** Connecting to Slack, GitHub, or Jira.
- **Under the Hood:** MCP relies on **Indexing** and **RAG** to find the right data. 
- **Deep Dive:** See [Retrieval & Context](./retrieval-and-context.md) for more.


---

## 🔄 2. The Agentic Workflow: Artifacts

The AI doesn't just "write code"; it manages a lifecycle using **Artifacts**.

### The Task (`task.md`)
- **Utility:** A living checklist. Whenever a complex goal is set, the AI initializes a task.
- **Visibility:** You can see exactly what step is being worked on and what remains.

### Implementation Plan (`implementation_plan.md`)
- **Utility:** The architecture blueprint.
- **Constraint:** For complex changes, the AI will document *which* files will change and *how* before touching a single line of code.
- **Your Role:** Review this to ensure the AI isn't going in the wrong direction.

### Walkthrough (`walkthrough.md`)
- **Utility:** The "Definition of Done."
- **Content:** Proof of work—screenshots, terminal logs, or test results—showing that the task was completed successfully.

---

## ⚡ 3. Automation: Workflows & Turbo

### Workflows
- **Location:** `.agent/workflows/[name].md`
- **What:** Markdown files that define a sequence of terminal commands or steps.
- **Usage:** You can trigger these with slash commands (e.g., `/deploy`).

### Turbo Mode (`// turbo`)
- **Manual vs. Auto:** Normally, the AI asks for permission before running terminal commands. 
- **Turbo:** Annotating a workflow step with `// turbo` tells the AI it is **SafeToAutoRun**, allowing it to fly through repetitive tasks like `npm install` or running tests without stopping to ask you.

---

## 🧠 4. Memory: Knowledge Items (KIs) & Context

This is how the AI "grows" with your project.

### Knowledge Items (KIs)
- **What:** Distilled summaries of past research, architectural decisions, and bug fixes.
- **Storage:** Found in `<appDataDir>/knowledge`.
- **Function:** When the AI learns something new about your specific codebase (like a "gotcha" in the auth logic), it creates a KI so that future AI versions don't have to re-learn it from scratch.

### Persistent Context
- **Memory:** The AI can look back at past conversation logs and artifacts.
- **Benefit:** If you say "Remember that refactor we did last week?", the AI handles the search through old logs to regain that context.

---

## 🎨 5. Design & Proactiveness

### Visual Excellence
- The AI is programmed to prioritize "Premium Aesthetics." It avoids generic colors and uses modern design principles (gradients, micro-animations, glassmorphism) when building web apps.

### Proactive Engineering
- Don't expect the AI to just answer questions. Expect it to **suggest** improvements, **verify** its own code with tests, and **update** documentation (like this handbook!) without being asked for every single detail.

---

## 🧠 6. AI Thinking Models

### What they are
Standard models use "Fast Thinking" (predictive), while Thinking Models (like **o1** or **DeepSeek-R1**) use "Slow Thinking" (deliberate reasoning).

### When to use them
- Use for **Complex Debugging**, **Architectural Planning**, or **Advanced Logic**.
- They are less suited for creative writing or simple syntax fixes.

### How to ask
Provide **Context**, **Specific Constraints**, and the **"Why"** behind your problem. Detailed guides can be found in `docs/learning/thinking-models.md`.

---
*Last Updated: 2026-02-18*

