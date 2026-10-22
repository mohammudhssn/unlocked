---
description: Recommend the right venture track (micro-tool, service, course, report, startup) from the problem map
---

# Skill: Classify Output Track

## When to Use
After Session 4, or after the problem map is built. Run this to get a data-driven output track recommendation based on the classified problem map and GTM canvas draft.

## Context
The output track decision determines what to build from the DIF engagement. It should be made from data, not intuition. This skill applies the output decision tree systematically.

Read `outputs/problem-map.md`, `outputs/knowledge-pillars.md`, and `outputs/gtm-canvas.md` before proceeding.

## Instructions
1. Read the problem map — identify the top-ranked URGENT problem
2. Evaluate against the decision tree:
   - Is the problem urgent enough people would pay TODAY? (signals: SME said peers would pay, daily/weekly occurrence)
   - Is the addressable market $100M+? (signals: from pre-brief market size estimate, from SME's description of who has this problem)
   - Is it solvable with a simple tool? (signals: the solution the SME described, whether it requires human judgment)
   - Is the expert's knowledge worth packaging for others? (signals: learning curve, tacit knowledge density)
3. Recommend one primary track with explicit reasoning:
   - **Micro-Tool:** URGENT + <$100M + simple AI tool
   - **Productized Service:** URGENT + complex/human-in-loop + repeatable
   - **Course / SOP Pack:** IMPORTANT + high tacit knowledge + teachable
   - **Intelligence Report:** LOW urgency + knowledge worth documenting
   - **Funded Startup:** URGENT + $100M+ market
4. Note the other tracks that were considered and why they were deprioritized
5. Provide a confidence level: HIGH / MEDIUM / LOW — and what would change the recommendation

## Output
Append to `outputs/gtm-canvas.md` under a "## Output Track Recommendation" section.

Format:
```
## Output Track Recommendation

**Primary track:** [Track name]
**Confidence:** HIGH / MEDIUM / LOW

**Reasoning:** [2–3 sentences explaining why this track, based on specific data from the problem map]

**What would upgrade this:** [What signal would move this to a higher track — e.g., "if market size validation confirms $100M+, consider startup track"]

**Tracks considered and deprioritized:**
- [Track] — [Why not this one]
- [Track] — [Why not this one]
```
