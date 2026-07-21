---
mode: 'agent'
description: "Scaffold a new SQL or Python problem — create all four required files."
---

<!--
  HOW TO RUN THIS PROMPT:
  In Copilot Chat, type # and select "new-problem.prompt.md" from the dropdown.
  Use this at the start of every new problem session.
-->

Ask me:
1. Is this a SQL or Python problem?
2. What is the problem name? (use kebab-case, e.g. `top-three-salaries`)
3. What is the source? (e.g. DataLemur, DataCamp)
4. What is the difficulty? (Easy / Medium / Hard)
5. Is there a company associated with this problem? (e.g. Amazon, Meta — or "unknown")

Then announce the folder and files you will create, and wait for my confirmation before proceeding.
Approval covers only the announced folder and exact four files. Any additional file, command,
dependency, or wider scope requires a new proposal and new explicit approval.

Once confirmed, create the folder and scaffold these four files:

**For SQL problems:** `sql/problems/<problem-name>/`
**For DataLemur problems:** `sql/datalemur/<problem-name>/`
**For Python problems:** `python/problems/<problem-name>/`

```
├── problem.md      ← problem statement, source, difficulty, company
├── solution.sql    ← (SQL only) solution placeholder + explanation structure
├── solution.py     ← Python/Pandas solution placeholder + explanation structure
└── notes.md        ← when to use which tool, key concepts, ✅ Notes for Students
```

**`problem.md` template:**
```
# Problem Name

**Source:** [DataLemur / DataCamp]
**Difficulty:** Medium
**Company:** Unknown

## Problem Statement

[Paste problem statement here]

## Tables / Input Data

[Describe tables or dataframes]
```

**`solution.sql` template:**
```sql
-- Problem: [name]
-- Source: [source]
-- Difficulty: [difficulty]

-- SOLUTION

-- Line-by-line explanation:
-- Step 1:
-- Step 2:
```

**`solution.py` template:**
```python
# Problem: [name]
# Source: [source]
# Difficulty: [difficulty]

import pandas as pd

# SOLUTION

# Line-by-line explanation:
# Step 1:
# Step 2:
```

**`notes.md` template:**
```
# Notes — [Problem Name]

## When to use SQL vs Python
-

## Key concepts
-

## ✅ Notes for Students
-
```

After creating the approved files, show what changed and how it was verified, then stop. Creation
approval does not authorize staging, commit, or push; each later stage requires separate explicit
approval.
