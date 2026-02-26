# Interview Methodology

> The Domain Intelligence Framework runs on structured conversations. This document explains how those conversations are designed, why they work, and how raw session output becomes actionable insight.

---

## Core Philosophy

Most market research starts outside — with desk research, surveys, and competitor analysis. DIF starts inside, with the person who already knows the answers.

The SME has lived in the domain. They have pattern recognition that no dataset captures. The job of the interviewer is not to ask smart questions — it's to **create the conditions for the expert to surprise themselves**.

Three principles guide every session:

1. **Follow energy, not the script** — when the expert gets animated, slow down and dig
2. **Surface the workaround** — every workaround is a product waiting to be built
3. **Name the unspeakable** — the things "everyone knows" but no one talks about are often the most valuable

---

## Session Architecture

A full engagement runs 4–6 sessions. Each session has a specific job.

```
Session 1: World-building        → "What does your day actually look like?"
Session 2: Problem mining        → "What breaks? What's missing?"
Session 3: Knowledge mapping     → "What does mastery look like in your field?"
Session 4: Solution space        → "What would the ideal world look like?"
Session 5: Market validation     → "Who else experiences this? How big is it?"
Session 6: GTM co-creation       → "How would you reach them? What would they pay?"
```

Sessions 1–4 are internal (expert knowledge only). Sessions 5–6 blend internal insight with external market data pulled via the MCP research layer.

---

## Session 1: World-Building

**Goal:** Understand the terrain. Build a mental map of the domain before asking about problems.

**Opening move:**
> "Walk me through a day in your work — not the ideal version, the actual one."

**Probing framework (STAR-P):**
- **S**ituation — What's the context you operate in?
- **T**ask — What are you actually responsible for?
- **A**ction — What does the work actually look like, step by step?
- **R**esult — What does success look like? Who measures it?
- **P**ain — Where does the friction live? (Don't ask this directly — let it surface)

**What to capture:**
- Vocabulary (exact words they use — these are product copy seeds)
- Recurring touchpoints (people, systems, moments in the workflow)
- Signals of frustration (sighs, qualifiers, "it's just how it is")
- Moments where they slow down to explain something — that's a knowledge gap in the market

**End of session prompt to Claude:**
```
/synthesize-session
```
Loads session notes → outputs: key themes, threads to pull in Session 2, vocabulary glossary.

---

## Session 2: Problem Mining

**Goal:** Go deep on friction. This session generates the raw material for the problem map.

**The problem is not the symptom** — most experts will describe symptoms. The interviewer's job is to dig to root cause.

**Problem ladder technique:**
```
"What's the most frustrating part of [X]?"
  → "Why is that frustrating?"
    → "What would have to be true for that to not be a problem?"
      → "Has anyone tried to solve that? What happened?"
        → "What would a good solution look like to you?"
```

**Problem classification (run after session with Claude):**

| Type | Description | Signal |
|---|---|---|
| **Urgent** | Causes immediate pain when it occurs | "This happens every week" |
| **Important** | Significant impact but tolerated | "It's just part of the job" |
| **Latent** | Not recognized as a problem yet | "That's just how it is in this field" |

Latent problems are the highest-value opportunities. They signal an underdeveloped market.

**End of session prompt to Claude:**
```
/extract-problems
```
Loads session notes → classifies problems by type, frequency, and solvability → outputs structured problem map.

---

## Session 3: Knowledge Mapping

**Goal:** Map the terrain of expertise. Identify where the SME's knowledge creates genuine defensibility.

**The knowledge pillar technique:**

Ask the SME to teach you the domain as if you're a smart person with no background.

> "If I wanted to understand your field in 3 months, what would I need to learn first? What builds on what?"

This surfaces the **knowledge architecture** — the underlying structure of the domain. Each cluster becomes a pillar.

**Pillar documentation format:**
```markdown
## Pillar: [Name]
**What it is:** [Plain language definition]
**Why it matters:** [What breaks if you don't understand this]
**Where it's misunderstood:** [Common misconceptions in the market]
**SME's edge:** [What the expert knows about this that most don't]
**Opportunity signal:** [How misunderstanding creates a problem to solve]
```

**End of session prompt to Claude:**
```
/map-pillars
```
Loads session notes + previous problem map → organizes domain into structured pillar taxonomy → flags intersections between problems and pillars (these are the highest-signal opportunity spaces).

---

## Session 4: Solution Space

**Goal:** Let the expert imagine. This session is generative, not analytical.

**The "magic wand" technique:**
> "If you had unlimited resources and no technical constraints, what would you build to solve [problem X]?"

Let them describe it. Don't push back. Don't ask if it's feasible. The goal is to surface their mental model of the ideal solution — which often reveals insights about what a real MVP could look like.

**The "who would you call" technique:**
> "If this product existed today, who would be the first person you'd call to tell them about it?"

This surfaces the Ideal Customer Profile from the expert's own social graph — far more reliable than persona work.

**End of session prompt to Claude:**
```
/gtm-canvas
```
Loads problem map + pillar taxonomy + solution space notes → generates: ICP definition, positioning angles, first distribution channels, pricing hypotheses.

---

## Sessions 5–6: Market Validation + GTM Co-Creation

By this point, you have a fully structured knowledge base. Sessions 5–6 use the MCP research layer to validate the internal insights against external signals.

**Research enrichment flow:**

```
Internal insight (from sessions 1–4)
  ↓
/enrich-domain (triggers brave-search MCP)
  ↓
External validation: market size, competitors, adjacent products, papers
  ↓
Synthesis: where internal and external signals agree = high-confidence opportunity
           where they diverge = further investigation needed
```

**Session 6 is co-creation, not presentation.** The SME sits in and reacts to the GTM hypotheses. Their gut reactions are data. When they say "that would never work because..." — that's more valuable than anything the research layer surfaced.

---

## From Sessions to Insight: The Synthesis Layer

Every session flows into the knowledge vault (a structured Obsidian vault managed by the filesystem MCP). After each session, Claude skills automatically process the notes into structured outputs.

```
Raw session notes (markdown)
  ↓ /synthesize-session
Themes + threads + vocabulary glossary
  ↓ /extract-problems
Structured problem map (classified by type + solvability)
  ↓ /map-pillars
Knowledge pillar taxonomy
  ↓ /enrich-domain (+ MCP search layer)
Market-validated insight brief
  ↓ /gtm-canvas
GTM canvas: ICP, positioning, channels, pricing
```

The final output — the **Insight Brief** — is a 2–3 page document that any founder, investor, or product team can act on immediately.

See [templates/insight-brief.md](templates/insight-brief.md) for the output template.

---

## The Role of the Expert Post-Framework

The DIF is not a one-time engagement. Once the knowledge vault is built, it becomes a persistent asset:

- **As an MCP context layer** — any future Claude session can query the domain knowledge base, making the expert's insight available to product, content, and GTM decisions without re-running interviews
- **As a co-founder data room** — if the SME wants to build a venture, the knowledge vault is the first version of their internal documentation
- **As a positioning engine** — content, pitch decks, and partnerships are all rooted in the same structured knowledge base, ensuring consistency

The expert goes from knowing their domain to **owning it as a structured, queryable, business-ready asset**.
