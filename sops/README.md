# SOPs

> Standard operating procedures for running the Unlocked / DIF engagement cycle.

These SOPs serve two purposes:

1. **For running the studio:** Step-by-step playbooks for every phase of the DIF process — so the methodology is repeatable, teachable, and not dependent on any one person's memory.

2. **As a product output model:** The same structure used to produce these SOPs is what you use to codify an expert's tacit knowledge for a client. Every SOP you produce internally demonstrates the methodology in action.

---

## The Three Core SOPs

| SOP | When to Use | Time |
|-----|-------------|------|
| [Engagement SOP](engagement-sop.md) | Starting a new engagement — end-to-end playbook | Ongoing reference |
| [Research SOP](research-sop.md) | Before Session 1 — pre-engagement research protocol | 60–90 minutes |
| [Synthesis SOP](synthesis-sop.md) | After each session — processing raw notes into structured output | 15–30 minutes |

---

## Why SOPs Matter in an AI-First Studio

Without SOPs, your studio is as good as your memory. With SOPs, it's as good as your process — and processes can be improved, delegated, and automated.

**What AI enables in each SOP:**
- Research SOP: Claude + MCP handle Layer 2 research automatically. Perplexity handles Layer 1. Human judgment is applied to the synthesis, not the data gathering.
- Engagement SOP: The Discovery Bot, Synthesis Bot, and GTM Bot run most of the non-live work. You review and direct.
- Synthesis SOP: The Synthesis Bot produces the first draft. You edit. Total time: 15 minutes instead of 90.

**The SOP as a training document:**
As the studio scales, these SOPs are what you hand to a new team member. They don't need to be present for the founder to have figured it out — the methodology is documented, tested, and transferable.

**The SOP as an output:**
When a client engagement surfaces expert knowledge worth codifying, you use the same template structure to produce their SOP Pack. The tool you use internally is the product you sell externally.

---

## Generating SOPs from Domain Engagements

After Session 3 (Knowledge Mapping), run:

```
/generate-sop
```

Claude reads the session notes and knowledge pillar taxonomy, identifies the process with the highest tacit knowledge density, and produces a first-draft SOP using the [sop-pack.md template](../templates/sop-pack.md).

Review, edit, and fill in gaps in Session 4 or async with the expert. The resulting SOP becomes:
- A standalone product (sell to domain peers)
- The playbook for any service or tool built from the engagement
- Internal documentation if the engagement goes startup track

---

## Keeping SOPs Current

SOPs are living documents. Update them when:
- A new engagement reveals a better approach
- A step consistently fails in practice
- The AI stack makes a step faster or more accurate
- Feedback from an SME partner reveals a blind spot

Add a version note at the top of each SOP when you make material changes.
