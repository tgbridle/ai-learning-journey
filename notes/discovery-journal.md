# 📓 Discovery Journal: AI Learning Journey

## 🗓️ Entry: 2026-01-20

### 🚀 Progress Summary
Today focused on refining the mobile user experience and strengthening the application's underlying data and documentation. Key improvements were made to search accessibility on small screens, grammatical data coverage, and the formalization of the technical architecture.

---

### 🧠 Key PM Learnings & Insights

#### **1. Mobile-First UX: The Keyboard Collision**
* **The Learning:** During mobile testing, I identified a critical UX flaw: the search suggestion dropdown was appearing below the input field, which meant it was completely obscured by the on-screen keyboard.
* **The "Why":** Standard desktop dropdown logic doesn't account for the "real estate heist" committed by mobile keyboards.
* **The Fix:** Implemented mobile-detection logic to flip the UI. If a mobile device is detected, suggestions now appear **above** the search box, ensuring visibility during active typing.

#### **2. Visual Polish: Case & Readability**
* **The Learning:** I moved away from "All-Caps" shouting in the UI. 
* **The Change:** Refactored status indicators like "ALWAYS ACCUSATIVE" to standard sentence case (e.g., "Always Accusative").
* **The "Why":** Standard casing improves readability and aligns with a more sophisticated, modern brand aesthetic.

#### **3. Data Enrichment: Grammar Insights**
* **The Learning:** Identified a data gap where most words were missing the "Grammar Insight" context.
* **The Progress:** Generated missing grammar notes for the current word list to ensure the "Deep-Dive" view provides actual value beyond simple translation.

---

### 🏛️ Architecture & Documentation
* **Project Formalization:** I worked with the AI to extract a comprehensive breakdown of the Langly tech stack, including the state-based SPA architecture and the modular renderer pattern.
* **Automated Documentation:** Directed the AI to write these technical specifications and data schemas directly to the GitHub repository to ensure the "Source of Truth" remains synchronized with the code.

---

### 🛠️ Next Steps: The Langly Roadmap

* **Schema Validation:** Verify that the newly generated grammar notes are rendering correctly within the Indigo/Teal/Magenta borders of the Deep-Dive views.
* **Master Prompt Creation:** Design a "System Prompt" to generate perfectly formatted JSON batches for bulk ingestion into Supabase.
* **v0 Feature Set** Decide on a v0 feature set that will get this off the ground before the end of March.
* * **Testing:** Before I populate the whole database - I want to create test cases via Lovable to test the app in and out.
* * **Mass data creation!:** Now I've decided on an approach to populate the database - I want to start putting this in place.


# 📓 Discovery Journal: AI Learning Journey

## 🗓️ Entry: 2026-01-19

### 🚀 Progress Summary
Today, the project shifted focus from frontend UI templates to backend system architecture. We evaluated the critical "Scaling Crossroads": how to move Langly from a narrow 80-word beachhead to a robust, 10,000+ word "v0" production-ready MVP.

---

### 🧠 Key PM Learnings & Insights

#### **1. The "Certainty" Mandate for Language Learning**
* **The Learning:** For a grammar-focused app, "Dynamic Generation" (LLMs) is a liability for core data like gender and cases.
* **The "Why":** A single hallucination (e.g., calling "Hund" neuter) breaks user trust immediately. Accuracy must be "Hard-Coded" in the database, not "Guessed" by a model at runtime.
* **Takeaway:** We will use a **Local Database (Pre-populated)** as our Source of Truth to ensure instant performance and 100% accuracy.


---

### 🏛️ Architectural Decision Matrix: Sourcing & Storage

| Strategy | Accuracy | Performance | Recommendation |
| :--- | :--- | :--- | :--- |
| **External API** | 🟠 Variable | 🟡 Medium | Too generic; lacks our specific "Articulated Schema" requirements. |
| **Live LLM** | 🔴 Low (Risk) | 🔴 Slow (3s+) | High cost and risk of grammatical hallucinations. |
| **AI-to-DB Pipeline** | 🟢 High | 🟢 Instant | **Selected.** AI generates bulk data; humans/scripts validate; Supabase stores. |


---

### 🛠️ Next Steps: The Langly Roadmap

* **Master Prompt Creation:** Design a "System Prompt" to generate perfectly formatted JSON batches for bulk ingestion into Supabase.
* **v0 Feature Set** Decide on a v0 feature set that will get this off the ground before the end of March. 


# 📓 Discovery Journal: AI Learning Journey

## 🗓️ Entry: 2026-01-11

### 🚀 Progress Summary
By the end of this session, we have mapped out unique, high-utility deep-dive templates for all **8 core word types**, ensuring that Langly isn't just a dictionary, but a functional grammar engine.

---

### 🧠 Key PM Learnings & Insights

#### **1. The "Articulated Schema" Breakthrough**
* **The Learning:** I discovered a critical "data-logic" mismatch. Storing only the noun stem (e.g., "Hund") forced the UI to guess the grammar, resulting in incorrect articles (showing "der Hund" for every case).
* **The "Why":** In German, the article *is* the grammar. By refactoring the database to store the full phrase (e.g., "den Hund", "dem Hund"), we offloaded complex linguistic logic from the frontend code directly into the data layer.
* **PM Benefit:** This significantly reduces technical debt and makes the app 100% accurate for irregular words without needing custom code for every edge case.

#### **2. UI Modularity & The "Strict Boundary" Constraint**
* **The Learning:** As the app grew to support 8 word types, I had to enforce strict "frozen templates" for existing components (like Verbs and Nouns) while building new ones (like Prepositions).
* **The "Why":** This prevents "Refactor Regression"—where adding a new feature breaks an old one.
* **Takeaway:** Using specific, isolated prompts for Lovable allowed me to build custom "Logical Rule" displays for Prepositions and Conjunctions without disturbing the "Data Grids" used for Nouns.

#### **3. Branding & Context-Aware Headers**
* **The Learning:** I consolidated the brand identity by introducing the speech-bubble logo and a new tagline: *"Search, learn, use. Your language companion."*
* **The "Why":** Identified that "Double Branding" was cluttered. We moved to a brand-heavy home page and a minimalist, content-focused deep-dive page to reduce cognitive load for the learner.

### 🛠️ Next Steps

* **Scalability:** Decide how this will scale up and what I should use for storage (or word lookup) with thousands of words
* **MVP:** Decide on the 'line in the sand' - I'm keen to publish this when its ready
* **Testing** I want to learn (and do!) the creation of test cases via Lovable 
---

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
