# 📓 Discovery Journal: AI Learning Journey

## 🗓️ Entry: 2026-01-04

### 🚀 Progress Summary
Today I moved from a noun-centric tool to a comprehensive **Language Companion** supporting 8 distinct word types (Verbs, Pronouns, Prepositions, etc.). I refined the product's value proposition with a new action-driven branding ("Search, learn, remember") and implemented an intelligent, color-coded search interface that handles bilingual inputs.

---

### 🧠 Key PM Learnings & Insights

#### 1. The Beachhead Strategy & Adjacency Scaling
* **The Learning:** I am managing growth by starting with a narrow persona ("Alex") and moving into **Adjacent Use Cases**.
* **The "Why":** A "Beachhead" allows for focus; scaling happens by adding layers like Verbs or Pronouns to the existing search engine.
* **PM Benefit:** Using a **Headless Architecture** allows us to scale to new personas or languages by simply adding data columns rather than rewriting the core application.

#### 2. Visual Hierarchy & Cognitive Load
* **The Learning:** I refactored the sub-header into a two-line "Action/Value" split: *Lookup, understand, apply. Your word companion for learning a language.*
* **The "Why":** Splitting the text aligns with the natural **F-Pattern** for user scanning, making the app's purpose clear in under two seconds.
* **Takeaway:** Managing visual hierarchy (like muting search placeholders) reduces cognitive load and directs user attention to the primary task: searching.

#### 3. Product Economics & Scalability
* **The Learning:** I mapped out a "Zero-Cost Stack" using Vercel, Supabase, and GitHub free tiers.
* **Rationale:** For an MVP, managing operational viability is critical. We can support hundreds of users before incurring hosting costs.
* **Impact:** This validates that the product is technically prepared for growth without immediate financial overhead.

---

### 🛠️ Technical Architecture
The app has evolved into a **Polymorphic Dictionary** where a single search interface handles multiple data structures.

The application is built on a Client-Side Heavy, Headless Architecture where the React frontend manages the logic and Supabase serves as a flexible data store.

Data Flow Summary:
The Search: useDictionarySearch strips German articles (der/die/das) from user input to ensure accurate fuzzy matching.

The Result: The UI toggles between the SearchBar and WordDeepDive based on the selectedEntryId state.

The Deep-Dive: useDictionaryDetails pulls grammar data from a JSONB metadata column, allowing the UI to render different tables (conjugations vs. declensions) without needing multiple database tables.

<img width="597" height="617" alt="image" src="https://github.com/user-attachments/assets/f72f6b32-23af-4c75-937c-997a12060c54" />


### 💡 Next Steps
- [ ] **Data Verification:** Audit the 80-word seed list in Supabase for grammatical accuracy.
- [ ] **Component Build:** Validate/ Develop the specific UI grids for other word types conjugations.



## 🗓️ Entry: 2026-01-03

### 🚀 Progress Summary
Today I moved from a PRD to a functional **Full-Stack Prototype**. I initialized the project in Lovable, connected it to a Supabase backend, and established a GitHub sync for version control. Most importantly, I began refining the "Alex Moment" by implementing a custom search logic that recognizes German articles (e.g., "Der H" -> "der Hund").

---

### 🧠 Key PM Learnings & Insights

#### 1. Solving for "Natural" Input (Article-Aware Search)
* **The Learning:** I directed Lovable to tweak the search logic to handle articles (Der/Die/Das) rather than just noun strings.
* **The "Why":** German learners often recall the article as part of the word itself. If the search is too literal, it creates a "dead end" for the user.
* **PM Benefit:** This is a classic example of **User Intent over Literal Input**. By making the search "smarter" about German grammar early on, we reduce friction and increase the tool's perceived "intelligence."

#### 2. The GitHub Sync as an Audit Trail
* **The Learning:** I linked Lovable to my `ai-language-app` repo.
* **Rationale:** This turns my AI-prompting sessions into a series of **Commits**. It allows for reversibility and provides a technical portfolio that shows *how* the code evolved, not just the final result.

#### 3. Data-First Foundation
* **The Learning:** I prioritized the Supabase schema over UI aesthetics today.
* **Takeaway:** A language app is essentially a specialized database. Getting the relational structure right (linking Articles to Lemmas) is more critical for V1 than the color of the search button.

### 🛠️ Technical Architecture
I have moved to a **Headless Architecture** to ensure the app remains fast and scalable.


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
