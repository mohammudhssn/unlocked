---
description: Classify problems from session notes by urgency, frequency, solvability and market opportunity
---

# Extract Problems

You are running the **Problem Extractor** for the Domain Intelligence Framework.

## Context

Read all session syntheses from `/sessions/` before proceeding. Pay attention to both the "Problems Surfaced" and "Energy Map" sections of each synthesis — problems with high emotional charge are often the most valuable.

## Instructions

### Step 1: Consolidate
Pull every raw problem mention across all session syntheses. Group near-duplicates into single problem statements. Use precise, specific language — not "workflow issues" but "no standardized handoff protocol between OR and recovery room."

### Step 2: Write a Problem Statement for each
Format:
```
**Problem:** [Specific, concrete description of the friction]
**Who feels it:** [Role or persona from the SME's world]
**When it occurs:** [Trigger or context]
**Current workaround:** [What people do today]
**Why the workaround fails:** [What it doesn't solve]
```

### Step 3: Classify each problem

**Type:**
- `Urgent` — causes immediate, felt pain when it occurs. SME used strong language.
- `Important` — meaningful impact but normalized. "It's just how things work here."
- `Latent` — not recognized as a problem by most people in the domain. The SME knows but doesn't expect it to be fixable.

**Frequency:** How many sessions mentioned this problem? How often does it occur in practice (daily / weekly / per project)?

**Solvability:** Based on the SME's own comments about what a solution would look like:
- `High` — SME described a clear solution path
- `Medium` — partial clarity, would need more discovery
- `Low` — structural or systemic, hard to address as a product

**Market signal:** Is this specific to this SME's context, or did they describe it as universal across the domain?

### Step 4: Score and rank
Opportunity score = Urgency weight × Frequency × Solvability × Market breadth

Surface the top 3–5 problems as "Priority Opportunities."

## Output

Write to `/outputs/problem-map.md` using the template at `/templates/problem-map.md`.

After writing, flag the top 3 problems that intersect most strongly with the knowledge pillars (if `/outputs/knowledge-pillars.md` exists). These intersections are where the highest-defensibility opportunities live.
