## Course 6: Forming Analytical Questions <a id="course-6"></a>

**Level:** Basic | **Instructor:** [Konstantinos Kattidis](https://www.datacamp.com/instructors/kkattidis) — Data Analytics Lead  
**Chapters:** 3 | **Lessons:** 35 (12 🎬 Video + 23 📝 Exercise) | **XP:** 2,400 | **Duration:** 1 hour  
**Updated:** May 2026 | **Learners:** 33,263 *(checked 21 July 2026)* | **Prerequisites:** None  
**CPE:** 2.4 credits | **Qualified assessment:** course completion and a score of at least 70%  
**Status:** 🟡 In progress  
**Part of track:** [Data Literacy Professional](https://app.datacamp.com/learn/skill-tracks/data-literacy-professional) — Course 6

> 🔗 [Open the full course on DataCamp](https://www.datacamp.com/courses/forming-analytical-questions)  
> 📖 [Course glossary (PDF)](https://assets.datacamp.com/production/repositories/6194/datasets/1f1981108b95330fd98fb78e93de13d9dd017437/Forming%20Analytical%20Questions.pdf)

> **Source note:** Lesson titles, links, timestamps, and course metadata come from DataCamp. The timestamped notes are faithful paraphrases of the video transcripts, not verbatim reproductions. Open the linked DataCamp lesson and select **Transcript** to read the original wording.

---

### Course description

Business questions change with context and purpose: a company may need to choose a pricing strategy, improve retention, or understand another operational problem. Those broad questions normally cannot be answered directly with data. They first need to be translated into analytical questions precise enough to guide hypotheses, data selection, methods, and interpretation.

This non-technical course teaches that translation. It follows the path from a business goal and business question to a well-formed analytical question, then to a suitable analytical solution. The final chapter applies the process to descriptive, diagnostic, predictive, and prescriptive problems across several industries.

### Course goal

By the end of the course, the learner should be able to:

- distinguish a broad business question from an answerable analytical question;
- clarify business needs through effective communication;
- form analytical questions that are specific, measurable, actionable, relevant, and time-bound;
- account for context, available data, constraints, and team capabilities;
- match the question to an appropriate analytical approach;
- translate analytical findings back into business meaning and a decision.

### Why this course matters in Data Brain Gym

This course sits directly at the business ↔ technical boundary. Its purpose is not merely to produce a technically correct analysis, but to prevent a team from solving the wrong problem precisely.

The central translation chain is:

```text
Business goal → Business question → Analytical question → Evidence → Meaning → Decision
```

### How to use this guide

1. Open the linked DataCamp lesson and attempt the material there first.
2. Use **Quick Recall** to reconstruct the central model in under two minutes.
3. Use the **Source layer** to revisit the course logic and original sequence.
4. Use the **Learning layer** to understand Data's interpretation, the key distinction, and the practical transfer.
5. For exercises, select an answer before reading the solution table.

---

### 📊 Course Progress

| Chapter | Lessons | XP | Status |
|---|---:|---:|---|
| Ch1: Delivering value through data | 1/9 | 50/650 | 🟡 In progress |
| Ch2: Impactful solutions need the right questions | 0/13 | 0/850 | ⬜ Not started |
| Ch3: Analytical questions in action | 0/13 | 0/900 | ⬜ Not started |
| **Total** | **1/35** | **50/2,400** | **2%** |

---

### 🗺️ Course Knowledge Map

```mermaid
flowchart LR
    A[Strategic business goals] --> B[Business questions]
    B --> C[Well-formed analytical questions]
    C --> D[Select analytical solutions]
    D --> E[Develop the solutions]
    E --> F[Deliver through storytelling or deployment]
    F --> G[Business decision and value]
```

| Chapter | Central question | Learning outcome |
|---|---|---|
| 1. Delivering value through data | How does analysis move from a business goal to business value? | Understand the workflow, distinguish business and analytical questions, and recognize translation challenges. |
| 2. Impactful solutions need the right questions | How do we form the right question and choose a suitable solution? | Clarify business needs, form well-structured analytical questions, and match them to analytical approaches. |
| 3. Analytical questions in action | How does the process change with the type of problem? | Apply descriptive, diagnostic, predictive, and prescriptive thinking to realistic industry cases. |

---

### Instructor and contributors

**Konstantinos Kattidis** is a Data Analytics Lead with more than nine years of analytics experience across automotive, logistics, and e-commerce. His stated focus is enabling data-informed business decisions and creating value through analytics.

**Course collaborators:** Jess Ahmet, Joe Franklin, and Joanne Xiong.

---

### Review queue

- [ ] **Same session:** Reconstruct the six-step Value from Analytics workflow without looking.
- [ ] **+1 day — 2026-07-22:** Explain the difference between a business question and an analytical question.
- [ ] **+3 days — 2026-07-24:** Translate one real business question into two analytical questions.
- [ ] **+7 days — 2026-07-28:** Explain how an analytical result returns to business language and supports a decision.

---

### Chapter 1: Delivering value through data

Data and analytics create value only when analysis remains connected to a real business goal. This chapter introduces the end-to-end workflow, the distinction between business and analytical questions, and the recurring difficulties that arise while translating between the two environments.

| # | Lesson | Type | XP |
|---:|---|---|---:|
| 1 | Making a business impact | 🎬 Video | 50 |
| 2 | The "Value from analytics" workflow | 📝 Exercise | 100 |
| 3 | Reasons to form analytical questions | 📝 Exercise | 100 |
| 4 | Difference between business and analytical questions | 🎬 Video | 50 |
| 5 | The right analytical questions for the business question | 📝 Exercise | 50 |
| 6 | Classifying business and analytical questions | 📝 Exercise | 100 |
| 7 | Challenges in transforming business questions | 🎬 Video | 50 |
| 8 | The key to a well formed analytical question | 📝 Exercise | 50 |
| 9 | Conquering the challenges in each step | 📝 Exercise | 100 |

**Chapter 1 XP: 650**

---

#### Chapter 1 — Lesson 1: Making a business impact *(Video / 50 XP)*

> 🎬 [Watch on DataCamp](https://campus.datacamp.com/courses/forming-analytical-questions/delivering-value-through-data?ex=1) *(requires login)*  
> 📜 Open **Transcript** inside the lesson for DataCamp's complete original transcript.

---

**⚡ QUICK RECALL — under two minutes**

**Main idea:** Analytics creates business value through a translation workflow. Strategic goals become business questions; business questions become answerable analytical questions; analytical work is then translated back into business meaning and a decision.

**Key distinction:** Business and technical teams do not necessarily seek the same intermediate answer. They work on the same business problem and should remain aligned around the decision that the evidence must support.

**One model:**

```text
Goal → Business question → Analytical question → Select → Develop → Deliver
```

**Retrieval prompt:** Why is beginning with a preferred model or technique riskier than beginning with the business goal and question?

---

**📚 SOURCE LAYER — Timestamped transcript-derived notes**

| Time | Video section | Source-faithful notes |
|---|---|---|
| 00:00–00:08 | Introduction | Konstantinos introduces himself and the course on forming analytical questions. |
| 00:08–00:45 | The data-driven path to success | Decisions based only on intuition or accepted theory can inherit false assumptions and bias. Analytics strengthens decisions with evidence, but value depends on focusing on the right area and choosing an appropriate solution. |
| 00:45–01:16 | Value from Analytics workflow | The instructor introduces a simplified six-step path: understand business goals, define business questions, translate them into analytical problems, select a solution, develop it, and deliver it. |
| 01:16–01:37 | Strategic business goals | Organizations set targets for a defined period. These goals act as a compass that directs teams toward the work that matters. |
| 01:37–02:08 | Business questions | Teams turn strategic goals into team-level goals, questions, or problems—for example, understanding rising customer churn or increasing sales to existing customers. |
| 02:08–02:47 | Analytical questions | A business question is often too broad to guide analysis. Translation produces questions that support hypotheses and can be addressed using available data and analytical methods. This is the bridge from the business environment to the analytical environment. |
| 02:47–03:23 | Selecting analytical solutions | The solution should follow the analytical question. Selection also depends on data availability and the team's technical capability. Possible methods include regression, time-series analysis, and forecasting. |
| 03:23–03:48 | Develop and deliver | The analytics team builds the selected solution and returns it to the business through mechanisms such as data storytelling or model deployment. Findings must be translated back into business language to improve decisions. |
| 03:48–04:21 | Course focus | The course concentrates on understanding business questions, translating them into well-formed analytical questions, and choosing analytical solutions that solve the original problem and create value. |
| 04:21–04:27 | Practice | The video closes by moving from the introductory model to a knowledge check. |

**The six-step Value from Analytics workflow**

| Step | Question answered | Primary environment |
|---:|---|---|
| 1. Know the strategic business goals | What outcome is the organization trying to achieve? | Business |
| 2. Define the business questions | What problem or decision must the business address? | Business |
| 3. Form the analytical questions | What can data and analysis answer precisely? | Translation bridge |
| 4. Select the analytical solutions | Which approach fits the question, data, and capabilities? | Analytical |
| 5. Develop the analytical solutions | How will the team perform the analysis or build the model? | Analytical |
| 6. Deliver the analytical solutions | How will the result return to the business and influence action? | Analytical → Business |

---

**🧠 LEARNING LAYER — Data's angle**

**Data's first explanation:** Business and technical people may formulate questions differently, but they are trying to resolve the same underlying problem.

**Spock's refinement:** They do not necessarily produce the same answer. A business question asks about an outcome, problem, or decision. An analytical question asks what can be measured, compared, explained, or predicted. Their common anchor is the original business goal and the decision the evidence should support.

```text
Business language                         Analytical language
"Why are we losing customers?"     →     "Which segments changed, when, and with which measurable factors?"
                                      ↓
                              Evidence and interpretation
                                      ↓
"What should we test or change?"   ←     Finding translated into business meaning
```

**DIKW connection**

| DIKW layer | Role in the workflow |
|---|---|
| Data | Observations and measurements available for analysis |
| Information | Organized comparisons, patterns, segments, and context |
| Knowledge | An explanation or reusable finding that answers the analytical question |
| Wisdom | A context-sensitive business decision, including assumptions and trade-offs |

**💡 Why this matters**

A technically correct method can still produce no value if it answers the wrong question. The translation step protects the connection between strategic purpose, analytical work, and a decision.

**Practical transfer**

| Layer | Customer-retention example |
|---|---|
| Strategic goal | Improve sustainable revenue from existing customers. |
| Business question | How can the company reduce customer churn? |
| Analytical questions | Which customer segments show the largest increase in churn? When did the change begin? Which observable factors are associated with it? |
| Possible solution | Segment comparison followed by an appropriate diagnostic or predictive analysis, depending on the refined question and available data. |
| Business return | Translate the finding into a testable retention action, state uncertainty, and measure whether the intervention works. |

**✅ RECAP**

- Analytics delivers value through an end-to-end workflow, not through a model in isolation.
- Business questions provide purpose; analytical questions make the problem answerable with evidence.
- The selected analytical solution must fit the question, data availability, and team capability.
- Delivery completes the loop by translating the result into business language, storytelling, deployment, and ultimately a decision.

**🔗 Connection**

- *Introduction to Data Culture* established that evidence should improve decisions; this course explains how to formulate the question that makes useful evidence possible.
- Data Storytelling appears in step 6: findings must return from the analytical environment to the business environment without losing their meaning or limitations.

---

### Chapter 2: Impactful solutions need the right questions

This chapter develops the communication and reasoning practices needed to understand a business problem, form a well-structured analytical question, distinguish major analytics types, and choose a technique suitable for the question and constraints.

| # | Lesson | Type | XP |
|---:|---|---|---:|
| 1 | Understanding the business question | 🎬 Video | 50 |
| 2 | Best communication practices | 📝 Exercise | 50 |
| 3 | Asking the right questions | 📝 Exercise | 100 |
| 4 | Forming the analytical questions | 🎬 Video | 50 |
| 5 | Re-phrasing the question | 📝 Exercise | 50 |
| 6 | Choosing the relevant question | 📝 Exercise | 100 |
| 7 | Types of analytical solutions | 🎬 Video | 50 |
| 8 | An advice for the analytics types | 📝 Exercise | 50 |
| 9 | Questions for the right type of analytics | 📝 Exercise | 50 |
| 10 | The best technique for the solution | 📝 Exercise | 100 |
| 11 | Choosing the best analytical solution | 🎬 Video | 50 |
| 12 | Best practices for selecting the right technique | 📝 Exercise | 50 |
| 13 | Analytical solutions in action! | 📝 Exercise | 100 |

**Chapter 2 XP: 850**

---

### Chapter 3: Analytical questions in action

The final chapter applies the translation process to realistic problems from e-commerce, automotive, healthcare, and banking. It organizes questions and techniques around the four major analytics perspectives: descriptive, diagnostic, predictive, and prescriptive.

| # | Lesson | Type | XP |
|---:|---|---|---:|
| 1 | What happened? | 🎬 Video | 50 |
| 2 | Choose the relevant descriptive questions | 📝 Exercise | 50 |
| 3 | Map the descriptive technique to the right question | 📝 Exercise | 100 |
| 4 | Why did it happen? | 🎬 Video | 50 |
| 5 | Relevant diagnostic questions | 📝 Exercise | 100 |
| 6 | Map the diagnostic technique to the right question | 📝 Exercise | 100 |
| 7 | What will happen? | 🎬 Video | 50 |
| 8 | Choose the best predictive analytics question | 📝 Exercise | 50 |
| 9 | Map the predictive technique to the right question | 📝 Exercise | 100 |
| 10 | What should we do next? | 🎬 Video | 50 |
| 11 | Choose the best prescriptive analytics question | 📝 Exercise | 50 |
| 12 | Solving the question classification challenge! | 📝 Exercise | 100 |
| 13 | Congratulations! | 🎬 Video | 50 |

**Chapter 3 XP: 900**

