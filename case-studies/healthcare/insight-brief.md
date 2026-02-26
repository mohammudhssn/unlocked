# Insight Brief: Perioperative Workflow Intelligence

**Prepared:** Post-Session 4 + Research Enrichment
**Confidence level:** High (3 of 3 priority problems externally confirmed)

---

## The One-Paragraph Summary

Anesthesiologists carry an enormous amount of tacit knowledge that the current healthcare infrastructure cannot capture, transfer, or leverage. The most acute failure point is the patient handoff — a moment where decisions are high-stakes, time-compressed, and dependent on verbal communication that frequently loses critical context. The highest-opportunity product space is a lightweight, structured pre-op and handoff layer that captures decision rationale, not just clinical state — purpose-built for how anesthesiologists actually think, not how EMR vendors think they think.

---

## Priority Opportunity: Pre-Op Decision Layer

**The problem:** The 15 minutes before surgery involve the most consequential decisions in the perioperative workflow. None of this is captured. Clinicians rely on memory. The EMR records what happened, not why.

**Who feels it most:** Attending anesthesiologists supervising residents; anesthesiologists in high-volume community hospital settings where handoffs are frequent.

**The insight from the SME:** "The EMR knows what drug I gave. It has no idea why I chose that dose for that patient at that moment. That reasoning lives in my head and nowhere else."

**Why existing solutions fail:** EMR pre-op modules are built for compliance documentation, not clinical reasoning. They capture checkboxes, not decisions.

**The opportunity:** A structured, low-friction tool that captures the *why* behind pre-op decisions — designed to take 2–3 minutes, not 15 — and surfaces it at the next handoff point.

---

## Market Context

- **Medication reconciliation errors** account for approximately 1 in 5 hospital adverse events (Joint Commission, 2023)
- **EMR adoption** in US hospitals is near-universal, but clinician satisfaction remains low — average 2.4/5 for workflow fit (KLAS, 2024)
- **AI in clinical documentation** is a growing category ($2.3B market, growing 34% YoY), but most solutions focus on note generation, not decision capture
- **Regulatory tailwinds:** CMS has introduced new requirements for structured care transitions documentation, creating compliance pressure that could accelerate adoption

**Competitor landscape:**
- Epic / Cerner: comprehensive but built for administrators, not clinicians. Friction is high.
- Nabla, Abridge, Nuance DAX: AI ambient documentation — captures *what* was said, not *why* decisions were made
- No identified direct competitor in structured pre-op decision capture

---

## ICP (First Version)

**Primary:** Attending anesthesiologist in a community hospital or ambulatory surgery center
- Performs 8–15 cases per day
- Frequently supervises residents or CRNAs
- Responsible for pre-op assessment and handoff communication
- Frustrated by EMR documentation burden but not a tech adopter by instinct

**Adoption pathway:** Does not buy technology. But their medical director does — if the tool reduces adverse events and improves compliance documentation.

---

## First Move Recommendation

Recruit 3 attending anesthesiologists to participate in a 2-week "structured pre-op note" pilot using a shared Notion template (no product yet). Measure: time to complete, information recalled at handoff, perceived usefulness.

This validates the core assumption — that a structured pre-op layer adds value — before building anything.

**Success signal:** 2 of 3 say they'd use it every day if it took under 3 minutes.

---

## What's Not Resolved

1. **Build vs. integrate:** Should this be a standalone tool or an EMR integration? The SME said standalone, but the medical director said EMR integration is the only way to get institutional adoption.
2. **AI assistance level:** Would clinicians trust AI-suggested decision frameworks, or does it need to be blank-canvas?
3. **HIPAA pathway:** Data architecture for capturing and storing patient decision data at scale.
