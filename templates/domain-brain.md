# Domain Brain Entry Template

> One file per domain in `/domains/[domain-name]/`. This is the master record for everything the DIF engagement produced.

Copy this template into `/domains/[domain-name]/README.md` at the start of every engagement. It grows over time — the first version is sparse; by Session 4, it's the most complete picture of this domain you've ever had.

---

```markdown
# Domain: [DOMAIN NAME]

**Expert:** [Name, title, years in field, institution type]
**Engagement start:** [DATE]
**Sessions completed:** [0/4/6]
**Current phase:** [Listen / Extract / Structure / Enrich / Build]
**Output track:** [TBD / Micro-tool / Course / SOP Pack / Startup / Report]
**Status:** [Active / Co-building / Complete]

---

## The Domain in One Paragraph

[2–3 sentences: what this field is, who operates in it, what the core workflows look like. Written in the expert's vocabulary, not ours.]

---

## Problem Map

### Urgent (people would pay to solve this now)

- [ ] **[Problem]** — Signal: *"[exact quote from expert]"*
  - Frequency: [daily / weekly / per-project]
  - Who has it: [role / institution type]
  - Current workaround: [what they do instead]
  - Revenue signal: [what expert said about what people would pay]

- [ ] **[Problem]** — Signal: *"[quote]"*

### Important (real pain, currently tolerated)

- [ ] **[Problem]** — Signal: *"[quote]"*
  - Notes: [why it's important but not urgent]

### Latent (they don't know they have it yet)

- [ ] **[Problem]** — Signal: *"[quote]"*
  - Notes: [how you surfaced it — what question revealed it]

---

## Knowledge Pillars

### Pillar 1: [NAME]
**What it is:** [Plain language definition]
**Why it matters:** [What breaks if you don't understand this]
**Where it's misunderstood:** [Common misconceptions in the market]
**SME's edge:** [What this expert knows about this that most don't]
**Opportunity signal:** [How this knowledge gap creates a product opportunity]

### Pillar 2: [NAME]
[Same structure]

### Pillar 3: [NAME]
[Same structure]

---

## Market Context

*From the Domain Pre-Brief and research enrichment layer.*

**Market size:** [Number, source, date]
**Growth trajectory:** [CAGR, key drivers]
**Key incumbents:**
| Company | What they do | What they're failing at |
|---|---|---|

**Recent funding:** [What VCs are betting on in this space]
**Regulatory:** [Key constraints and changes]
**Community signals:** [What practitioners are complaining about publicly]

---

## GTM Canvas (Draft)

*Populated after Session 4–6.*

**Priority problem:** [The one problem this engagement is building toward]
**ICP:** [Title / role at institution type in geography]
**Positioning angle:** [One-sentence positioning statement]
**Primary channel:** [Where the ICP lives and trusts]
**Pricing hypothesis:** $[X] for [what]
**First move:** [Specific test, 14 days, binary signal]

---

## SOP Produced

- [ ] **[SOP Name]** — [Brief description of the process codified]
  - Status: [Draft / Reviewed / Published]
  - Location: `../sops/[sop-name].md` or external link

---

## Partnership Terms

**Deal structure:** [Revenue share / Equity / Hybrid]
**Split:** [50/50 / negotiated]
**Agreement date:** [DATE]
**Status:** [Verbal / Documented / Active]
**Notes:** [Any relevant terms]

---

## Output Track Progress

**Track:** [Micro-tool / Course / SOP Pack / Startup / Report]
**Status:** [Identified / In build / Live]
**Revenue:** $[0] / month
**Next milestone:** [Specific next action]

---

## Vocabulary Glossary

*The expert's exact terminology. These are product copy seeds.*

| Term | Definition | Context |
|------|-----------|---------|
| | | |

---

## Session Log

| Session | Date | Type | Key Insight | Synthesis File |
|---------|------|------|-------------|----------------|
| Pre | | Discovery Bot | | `/sessions/pre-session.md` |
| 1 | | World-building | | `/sessions/session-01-synthesis.md` |
| 2 | | Problem mining | | `/sessions/session-02-synthesis.md` |
| 3 | | Knowledge mapping | | `/sessions/session-03-synthesis.md` |
| 4 | | Solution space | | `/sessions/session-04-synthesis.md` |
| 5 | | Market validation | | `/sessions/session-05-synthesis.md` |
| 6 | | GTM co-creation | | `/sessions/session-06-synthesis.md` |

---

## Cross-Domain Notes

*Problems or patterns from this domain that appear in others.*

| Pattern | Also seen in | Notes |
|---------|-------------|-------|
| | | |

*Link to central patterns file: `/patterns/cross-domain-repeaters.md`*

---

## SME Network: Warm Intros Available

*People this expert knows who might be the next engagement.*

| Name | Domain | Connection | Status |
|------|--------|------------|--------|
| | | | |

---

## Files in This Domain Folder

```
/domains/[domain-name]/
├── README.md              ← This file (master record)
├── pre-brief.md           ← Domain Pre-Brief (produced before Session 1)
├── problem-map.md         ← Classified problem map (output of /extract-problems)
├── knowledge-pillars.md   ← Pillar taxonomy (output of /map-pillars)
├── insight-brief.md       ← Synthesized insight + market context (output of /enrich-domain)
├── gtm-canvas.md          ← GTM canvas (output of /gtm-canvas)
├── sop-[name].md          ← SOP(s) produced from this engagement
└── sessions/
    ├── pre-session.md     ← Discovery Bot output
    ├── session-01.md      ← Raw session 1 notes
    ├── session-01-synthesis.md
    └── [...]
```
```
