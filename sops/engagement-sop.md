# Engagement SOP

> End-to-end playbook for running a full DIF engagement — from SME identification to venture track activation.

**Version:** 1.0
**Total engagement duration:** 2–4 weeks (including session scheduling)
**Sessions:** 4–6 × 60 minutes
**AI tools used:** Claude Code, Discovery Bot, Synthesis Bot, GTM Bot, MCP stack

---

## Overview

```
Pre-Engagement (2–3 days)
  → Research the domain
  → Produce Domain Pre-Brief
  → Share with SME before Session 1

Sessions 1–4 (1.5–3 weeks, scheduling dependent)
  → Session 1: World-building
  → Session 2: Problem mining
  → Session 3: Knowledge mapping
  → Session 4: Solution space

Post-Session Synthesis (after each session)
  → Run Synthesis Bot on notes
  → Save to vault
  → Review and set up for next session

Sessions 5–6 (optional, for high-ticket and partnership track)
  → Session 5: Market validation
  → Session 6: GTM co-creation

Output Production
  → Run GTM Bot
  → Produce all outputs
  → Output track decision

Partnership Activation (if applicable)
  → Document terms
  → Begin co-build
```

---

## Phase 1: Pre-Engagement (Days 1–3)

### Step 1.1: Domain Research

Run the 2-layer research protocol. Full details in [research-sop.md](research-sop.md).

- **Output:** Domain Pre-Brief (2 pages)
- **Time:** 60–90 minutes
- **Skill:** `/generate-pre-brief`

### Step 1.2: Vault Setup

```
/new-engagement
```

Or manually:
1. Create `/domains/[domain-name]/` in your vault
2. Copy `templates/domain-brain.md` → `/domains/[domain-name]/README.md`
3. Fill in: Domain name, SME name/role, Session start date
4. Update `.claude/CLAUDE.md` with the new engagement context

### Step 1.3: Discovery Bot (SME Async Prep)

Send the Discovery Bot to the SME 2–3 days before Session 1. See [chatbot-prompts/discovery-bot.md](../chatbot-prompts/discovery-bot.md).

- **How:** Share a Claude conversation link, or email the questions directly
- **Output:** Pre-session domain summary, problem seeds, vocabulary glossary
- **Save to:** `/domains/[domain-name]/sessions/pre-session.md`

### Step 1.4: Send the Pre-Brief

Email the Domain Pre-Brief to the SME 24–48 hours before Session 1. Include:
- The 2-page Pre-Brief document
- A brief note: "I've done some background research on your domain. Read this before we talk — wherever you disagree, that's the most interesting place to start."
- The Session 1 calendar invite

**Green light for Session 1:** Pre-Brief sent + SME has completed the Discovery Bot.

---

## Phase 2: Sessions 1–4

### Session 1: World-Building

**Objective:** Build a mental map of the domain. Do not ask about problems yet.

**Opening:**
> "Walk me through a day in your work — not the ideal version, the actual one."

**Your job:**
- Take notes in `/sessions/session-01.md` (use the [session-notes template](../templates/session-notes.md))
- Bold high-energy moments
- Capture vocabulary exactly as the SME uses it
- Don't redirect — follow their energy

**After the session (15 min):**
```
/synthesize-session
```
Save synthesis to `/sessions/session-01-synthesis.md`.

Review synthesis. Set your opening question for Session 2 from the Follow-Up Queue.

---

### Session 2: Problem Mining

**Objective:** Surface friction. Go from symptom to root cause.

**Opening:** Pull the top thread from Session 1's Follow-Up Queue.

**The problem ladder:**
```
"What's the most frustrating part of [X]?"
  → "Why is that frustrating?"
    → "What would have to be true for that to not be a problem?"
      → "Has anyone tried to solve that? What happened?"
        → "What would a good solution look like to you?"
```

**After the session:**
```
/synthesize-session
/extract-problems
```

The problem map begins here. Every session adds to it.

---

### Session 3: Knowledge Mapping

**Objective:** Map the terrain of expertise. Identify where the SME's knowledge creates defensibility.

**Opening:**
> "If I wanted to understand your field in 3 months, what would I need to learn first? What builds on what?"

**After the session:**
```
/synthesize-session
/map-pillars
/generate-sop
```

The SOP draft is produced from the pillar taxonomy. Review and mark sections that need more expert input.

---

### Session 4: Solution Space

**Objective:** Let the expert imagine. Generative, not analytical.

**Opening:**
> "If you had unlimited resources and no technical constraints, what would you build to solve [Priority Problem]?"

**The "who would you call" technique:**
> "If this product existed today, who's the first person in your network you'd call to tell them about it?"

**After the session:**
```
/synthesize-session
/extract-problems
/classify-output-track
```

The Output Track recommendation is generated here. Review with the SME before committing.

---

## Phase 3: Synthesis and Enrichment

**After Sessions 1–4 are complete, run the full skill sequence:**

```
/extract-problems      → consolidated problem map across all sessions
/map-pillars           → full pillar taxonomy
/enrich-domain         → market research enrichment (requires Brave Search MCP)
/gtm-canvas            → GTM canvas draft
```

Review each output. Correct anything that feels off. These are the inputs to Sessions 5–6.

**Time:** 30–60 minutes, mostly automated.

---

## Phase 4: Sessions 5–6 (High-Ticket + Partnership Track)

### Session 5: Market Validation

Share the enriched Insight Brief with the SME. Run through it together:
- Where does external data confirm what they said?
- Where does it contradict?
- What's missing that they know and the research missed?

Their reactions are data. The contradictions are the most valuable moments.

### Session 6: GTM Co-Creation

Run the GTM Bot live (share screen, generate output together). The SME reacts to the canvas in real time.

> "That would never work because..." → this is the most valuable sentence in the session. Capture it verbatim.

End with the First Move definition: one action, binary signal, 14 days, no building yet.

---

## Phase 5: Output Production

After all sessions are complete:

1. **Final problem map:** Consolidated, ranked, classified
2. **Knowledge Pillar Taxonomy:** Final version, reviewed by SME
3. **SOP Pack:** Completed with expert input from Session 4
4. **Insight Brief:** 2–3 pages, investor-grade
5. **GTM Canvas:** Final version, reviewed in Session 6
6. **Partnership Terms:** If co-build track — document before building

**File all outputs in:**
```
/domains/[domain-name]/
├── problem-map.md
├── knowledge-pillars.md
├── insight-brief.md
├── gtm-canvas.md
└── sop-[name].md
```

---

## Phase 6: Partnership Activation (Co-Build Track)

1. **Review Output Track decision** — confirm which track the data points to
2. **Produce Partnership Terms** using [templates/partnership-terms.md](../templates/partnership-terms.md)
3. **Get it signed** — digital signature (DocuSign, Adobe Sign) or physical
4. **Begin co-build sprint** — first 2 weeks focused on the MVP
5. **Update domain brain** — log partnership terms in `/domains/[domain-name]/README.md`

---

## Checklist: Engagement Complete

- [ ] Pre-Brief produced and sent
- [ ] Discovery Bot completed by SME
- [ ] Sessions 1–4 completed and synthesized
- [ ] Problem Map produced (`/extract-problems`)
- [ ] Knowledge Pillars produced (`/map-pillars`)
- [ ] SOP draft produced (`/generate-sop`)
- [ ] Domain enriched (`/enrich-domain`)
- [ ] GTM Canvas produced (`/gtm-canvas`)
- [ ] Output Track selected and rationale documented
- [ ] Insight Brief finalized
- [ ] Partnership Terms documented (if co-build track)
- [ ] Domain Brain updated (`/domains/[domain-name]/README.md`)
- [ ] Cross-domain patterns noted (`/patterns/cross-domain-repeaters.md`)
- [ ] SME Profile created (`/sme-network/[expert-name].md`)
