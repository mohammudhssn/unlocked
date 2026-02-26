# Interview Methodology

> The Domain Intelligence Framework runs on structured conversations. This document explains how they're designed, why they work, and how raw session output becomes actionable insight.

---

## Core Philosophy

Most market research starts outside — with desk research, surveys, and competitor analysis. DIF starts inside, with the person who already knows the answers.

The SME has lived in the domain. They have pattern recognition that no dataset captures. The job of the interviewer is not to ask smart questions — it's to **create the conditions for the expert to surprise themselves**.

Three principles guide every session:

1. **Follow energy, not the script** — when the expert gets animated, slow down and dig
2. **Surface the workaround** — every workaround is a product waiting to be built
3. **Name the unspeakable** — the things "everyone knows" but no one talks about are often the most valuable

---

## Pre-Engagement: The Research Layer

Before Session 1, run the 2-layer research protocol. Full details in [sops/research-sop.md](sops/research-sop.md).

**The goal:** Walk in already knowing the official narrative. Your live time with the expert is spent mining what's not in the official narrative.

**Produce a Domain Pre-Brief** (2 pages). Share with the expert 24–48 hours before Session 1. It signals credibility and primes deeper conversation from the first minute.

**Discovery Bot:** Send to the SME async before Session 1. They work through 20–30 structured questions at their own pace. When you arrive for Session 1, you're already 30 minutes deep.

→ [sops/research-sop.md](sops/research-sop.md) · [templates/pre-brief.md](templates/pre-brief.md) · [chatbot-prompts/discovery-bot.md](chatbot-prompts/discovery-bot.md)

---

## Session Architecture

A full engagement runs 4–6 sessions. Each session has a specific job.

```
Pre-session:  Discovery Bot (async, SME completes before Session 1)
Session 1:    World-building    → "What does your day actually look like?"
Session 2:    Problem mining    → "What breaks? What's missing?"
Session 3:    Knowledge mapping → "What does mastery look like in your field?"
Session 4:    Solution space    → "What would the ideal world look like?"
Session 5:    Market validation → "Who else has this? How big is it?"
Session 6:    GTM co-creation  → "How would you reach them? What would they pay?"
```

Sessions 1–4 are internal (expert knowledge only). Sessions 5–6 blend internal insight with external market data pulled via the MCP research layer.

---

## The Full Question Bank

Organized by knowledge type. These questions are domain-agnostic — they work for any expert in any field.

### Explicit Knowledge (what they can name)

*The surface layer. Start here.*

- "Walk me through what a good day in your work looks like vs. a bad day."
- "What do junior people in your field consistently get wrong?"
- "What's the thing you know that took you the longest to learn?"
- "What tool or process do you rely on that most people don't know exists?"
- "If you were writing a manual for someone entering your field, what's chapter one?"
- "What's the most common mistake you see people make in your domain?"
- "What questions do people always ask you that they could answer themselves if they knew [X]?"

---

### Tacit Knowledge (what they can't write down)

*The gold layer. Go slowly here.*

- "If you were training your replacement, what would take them the longest to *really* get?"
- "What do you do differently from the textbook that actually works?"
- "What's the workaround you use that nobody officially endorses?"
- "What do you know in the first 30 seconds of a [situation] that a junior person wouldn't notice for an hour?"
- "What's something you do on instinct that you'd struggle to explain to someone else?"
- "When you walk into a [situation], what tells you immediately whether it's going to go well or badly?"
- "What's the thing you've stopped explaining to people because it's too hard to articulate?"
- "What pattern do you recognize that others seem completely blind to?"

---

### Latent Demand (problems they haven't named yet)

*The opportunity layer. The most valuable — and the hardest to surface.*

- "What would you pay for if it existed and nobody had built it yet?"
- "What do you complain about with colleagues but assume is just how it is?"
- "What did you used to do manually that you still do manually, even though better tools exist?"
- "What problem do you solve for free, informally, for peers — that you could charge for if it were packaged?"
- "If you woke up tomorrow and [the biggest friction in your workflow] was gone, what would change?"
- "What do you Google repeatedly that still doesn't have a good answer?"
- "What's the thing everyone in your field accepts as normal that you think is actually broken?"
- "What task do you dread most? Why hasn't anyone solved it?"

---

### Market Intelligence (what the field is missing)

*The positioning layer. Surfaces competitive context and structural blindspots.*

- "Who's trying to solve this and failing? Why are they failing?"
- "Who benefits from this problem *not* being solved?"
- "What would change about your work if this problem disappeared tomorrow?"
- "Which people in your field have figured this out and aren't telling anyone?"
- "What do the best in your field do that the average practitioner doesn't know about?"
- "What's the conventional wisdom in your field that you think is wrong?"
- "Where does money get wasted in your domain that nobody talks about?"
- "What did you believe 5 years ago that turned out to be completely wrong?"

---

### Kill Criteria (qualifying the opportunity before building)

*Run these in Sessions 4–5. Only build what passes these.*

- "Would your peers pay to solve this? What would they pay?"
- "Has anyone tried to build this? What happened?"
- "Is this a symptom of a bigger structural problem, or the problem itself?"
- "How many people in your network have this exact problem? Could you name 5?"
- "Is this a daily pain or a once-a-year pain?"
- "Would you personally use this if someone built it tomorrow?"
- "What would make you stop using a solution to this once you started?"

---

### Follow-Up Probes

*Use when an answer is interesting but shallow.*

- "Say more about that."
- "What's a specific example of when that happened?"
- "How often does that come up?"
- "Who else in your world has that same experience?"
- "What's the cost of that — time, money, stress?"
- "What do people do instead, when they can't solve that?"
- "If you had to guess the root cause, what would it be?"

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

**End of session prompt:**
```
/synthesize-session
```
Outputs: key themes, threads to pull in Session 2, vocabulary glossary.

---

## Session 2: Problem Mining

**Goal:** Go deep on friction. This session generates the raw material for the problem map.

**The problem is not the symptom.** Most experts will describe symptoms. Your job is to dig to root cause.

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

**End of session prompt:**
```
/extract-problems
```
Outputs: structured problem map, classified by type, frequency, and solvability.

---

## Session 3: Knowledge Mapping

**Goal:** Map the terrain of expertise. Identify where the SME's knowledge creates defensibility.

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

**End of session prompts:**
```
/map-pillars
/generate-sop
```

`/map-pillars` organizes domain knowledge into a structured pillar taxonomy.
`/generate-sop` produces a first-draft SOP from the pillar structure — ready for review in Session 4.

---

## Session 4: Solution Space

**Goal:** Let the expert imagine. This session is generative, not analytical.

**The "magic wand" technique:**
> "If you had unlimited resources and no technical constraints, what would you build to solve [problem X]?"

Let them describe it. Don't push back. Don't ask if it's feasible. The goal is to surface their mental model of the ideal solution — which often reveals what a real MVP could look like.

**The "who would you call" technique:**
> "If this product existed today, who would be the first person you'd call to tell them about it?"

This surfaces the Ideal Customer Profile from the expert's own social graph — far more reliable than persona work.

**End of session prompts:**
```
/classify-output-track
/gtm-canvas
```

`/classify-output-track` reads the full problem map and produces an output track recommendation.
`/gtm-canvas` generates a first-draft GTM canvas — ICP, positioning, channels, pricing, first move.

---

## Sessions 5–6: Market Validation + GTM Co-Creation

By this point, you have a fully structured knowledge base. Sessions 5–6 use the MCP research layer to validate the internal insights against external signals.

**Research enrichment flow:**

```
Internal insight (from sessions 1–4)
  ↓
/enrich-domain (triggers search MCP)
  ↓
External validation: market size, competitors, adjacent products, papers
  ↓
Synthesis: where internal + external signals agree = high-confidence opportunity
           where they diverge = further investigation needed
```

**Session 6 is co-creation, not presentation.** The SME sits in and reacts to the GTM hypotheses. Their gut reactions are data. When they say "that would never work because..." — that's more valuable than anything the research layer surfaced.

Run the [GTM Bot](chatbot-prompts/gtm-bot.md) live in Session 6. Share your screen. Build the canvas together.

---

## Signal Classification

After each session, tag every problem surfaced:

| Tag | Meaning | Action |
|---|---|---|
| `urgent` | People pay to solve this NOW | Prioritize in problem map |
| `important` | Real pain but not immediate | Second tier in problem map |
| `latent` | They don't know they have it yet | Opportunity for education-led GTM |
| `explicit` | They can name and describe it | Already in market's conversation |
| `tacit` | Can't be written down easily | Competitive moat if productized |
| `$` | Has direct revenue implication | Flag for GTM canvas |

Multiple tags allowed.

---

## From Sessions to Insight: The Synthesis Layer

Every session flows into the knowledge vault. After each session, Claude skills automatically process the notes into structured outputs.

```
Raw session notes (markdown)
  ↓ /synthesize-session
Themes + threads + vocabulary glossary
  ↓ /extract-problems
Structured problem map (classified by type + solvability)
  ↓ /map-pillars
Knowledge pillar taxonomy
  ↓ /generate-sop
First-draft SOP from pillar structure
  ↓ /enrich-domain (+ MCP search layer)
Market-validated insight brief
  ↓ /gtm-canvas
GTM canvas: ICP, positioning, channels, pricing, first move
  ↓ /classify-output-track
Output track recommendation with rationale
```

The final output — the **Insight Brief** — is a 2–3 page document that any founder, investor, or product team can act on immediately. See [templates/insight-brief.md](templates/insight-brief.md) for the template.

---

## The Role of the Expert Post-Engagement

The DIF engagement is not a one-time event. Once the knowledge vault is built, it becomes a persistent asset:

- **As an MCP context layer** — any future Claude session can query the domain knowledge base, making the expert's insight available to product, content, and GTM decisions without re-running interviews
- **As a co-founder data room** — if the SME wants to build a venture, the knowledge vault is the first version of their internal documentation
- **As a positioning engine** — content, pitch decks, and partnerships are all rooted in the same structured knowledge base, ensuring consistency
- **As a training foundation** — the SOP Pack codifies the expert's process for anyone who joins the venture after them

The expert goes from knowing their domain to **owning it as a structured, queryable, business-ready asset**.

---

## The BRIDGE Framework Connection

The DIF methodology maps precisely to the BRIDGE Framework developed for emerging market contexts. See [BRIDGE.md](BRIDGE.md) for the full mapping.

Key adaptation: in relationship-first markets, the Recruit phase (finding the right SME) takes longer. Trust precedes transaction. Build more buffer into the pre-engagement phase — and treat the Domain Pre-Brief as a trust signal as much as a research signal.
