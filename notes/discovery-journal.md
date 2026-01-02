# 📓 Discovery Journal: AI Learning Journey

## 🗓️ Entry: 2026-01-02

### 🚀 Progress Summary
Today I moved from a broad language-learning concept to a high-conviction **Product Hypothesis**: solving the "Search-to-Deep-Dive" friction for German learners. I built an automated market research engine in n8n, defined my technical stack, and finalized the V1 PRD.

---

### 🧠 Key PM Learnings & Insights

#### 1. Workflow Engineering vs. Chatbot Interaction
* **The Learning:** I used an n8n workflow for market research instead of a standard chatbot (like ChatGPT).
* **The "Why":** While a chatbot is a one-off conversation, a **Workflow** is a repeatable, documented logic engine. 
* **PM Benefit:** Documenting a workflow shows technical discipline. It demonstrates I can handle data injection (JavaScript), API logic, and structured output (JSON) rather than just "chatting" with an AI.

#### 2. Model Economics & Cost Optimization
* **The Learning:** I accidentally used a "Pro" model (GPT-4) for the 15-item research loop, which was significantly more expensive than necessary.
* **The "Why":** For synthesis and research tasks, `gpt-4o-mini` is roughly 30 to 50 times cheaper and equally effective. 
* **Takeaway:** Always match the model "intelligence" to the task complexity. High-volume loops should almost always use "mini" models to protect the product's margin.

#### 3. Strategic Pivot: The Unified AI Stack
* **The Learning:** I decided to remove n8n as the "middleman" for the app build, moving to **Lovable + Supabase**.
* **Rationale:** * **Reduced Complexity:** Lovable handles the full-stack (React/Tailwind) and backend (Supabase) in one unified context.
    * **Relational Data:** Using **Supabase (PostgreSQL)** is critical for German grammar, where lemmas must have structured relationships with their inflections.
    * **Portfolio Impact:** Lovable's GitHub sync creates a tangible "Proof of Work" through automatic commits to my repository.

---

### 🛠️ Technical Concepts Mastered
* **Lemma:** The base, "dictionary" form of a word (e.g., *Hund*).
* **Inflection:** The grammatical variations of a word (e.g., *Hunden*, *Hundes*).
* **RTC Framework:** Professional prompt structuring: **Role, Task, Constraints**.
* **Fuzzy Matching:** A search logic that allows the system to resolve partial inputs or inflected forms back to the correct Lemma.

---

### 🔍 The Product Hypothesis: "The Alex Moment"
**The Problem:** English speakers learning German currently context-switch between fast translators (speed) and deep dictionaries (grammar) because no single tool handles both well.

**The Solution:** A "Search-to-Deep-Dive" interface. 
* **Input:** User types "Hu".
* **Suggestion:** App shows "der Hund (dog)".
* **Selection:** App instantly reveals a 4-case grammar table and plural forms.

---

### 💡 Next Steps
- [ ] Initialize Lovable project and link to `ai-language-app` repo.
- [ ] Set up the Supabase database schema for Nouns.
- [ ] Run the "Master Setup Prompt" to build the search interface.
