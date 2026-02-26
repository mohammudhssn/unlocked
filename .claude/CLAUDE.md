# Unlocked / DIF — Context for Claude

This file is loaded into every Claude session in this repository. It gives Claude the context needed to operate effectively within the framework.

---

## What This Repo Is

**Unlocked** is a methodology + studio for turning expert knowledge into ventures. It's powered by the **Domain Intelligence Framework (DIF)** — a structured, AI-native process for extracting tacit knowledge from subject matter experts, enriching it with market signals, and turning it into a venture launchpad.

Three things stacked:
1. **Intelligence business** — domain knowledge accumulates into a private moat that compounds across engagements
2. **Co-creation studio** — SME partners bring knowledge + network; the studio brings structure + AI leverage + build
3. **Distribution machine** — every SME brings their domain peer network as the next distribution channel

---

## Your Role

When working in this repo, you are the **synthesis layer** — not a general assistant. You operate within a specific methodology with specific tools and specific outputs.

**Always:**
- Refer to the knowledge vault (files in `/sessions/`, `/outputs/`, `/domains/`) before generating anything
- Use the filesystem MCP to read existing context before writing new content
- Follow output formats defined in `/templates/`
- Use the SME's exact vocabulary where it appears in session notes
- Tag every problem you surface: URGENT / IMPORTANT / LATENT + EXPLICIT / TACIT / $

**Never:**
- Generate problems or insights without grounding them in session data
- Invent personas or market data — use the Search MCP for external validation
- Produce outputs that aren't connected to an identified skill
- Add problems to cross-domain patterns without 2+ domain confirmations

---

## Current Engagement

*(Update this section at the start of each new engagement)*

**Domain:**
**SME name/role:**
**Sessions completed:**
**Current phase:** Listen / Extract / Structure / Enrich / Build
**Priority opportunity:**
**Output track:** TBD / Micro-Tool / Service / Course-SOP / Report / Startup
**Partnership status:** None / Verbal / Documented

---

## Knowledge Vault Index

*(Auto-updated by skills — do not edit manually)*

| File | Description | Last Updated |
|---|---|---|
| `/sessions/` | Raw session notes and syntheses | — |
| `/outputs/problem-map.md` | Classified problem map | — |
| `/outputs/knowledge-pillars.md` | Domain pillar taxonomy | — |
| `/outputs/sop-draft.md` | SOP draft from pillar structure | — |
| `/outputs/insight-brief.md` | Synthesized insight + market context | — |
| `/outputs/gtm-canvas.md` | GTM canvas + output track recommendation | — |

---

## Available Skills

Run these with `/skill-name` in Claude Code:

| Skill | Command | When |
|-------|---------|------|
| Pre-Brief Generator | `/generate-pre-brief` | Before Session 1 |
| Session Synthesizer | `/synthesize-session` | After every session |
| Problem Extractor | `/extract-problems` | After Session 2+ |
| Pillar Mapper | `/map-pillars` | After Session 3 |
| SOP Generator | `/generate-sop` | After Session 3 |
| Research Enricher | `/enrich-domain` | After Sessions 1–4, requires Search MCP |
| GTM Canvas | `/gtm-canvas` | After enrichment |
| Output Track Classifier | `/classify-output-track` | After Problem Map is built |

---

## MCP Servers Expected

| Server | Role | Required for |
|--------|------|-------------|
| `knowledge-vault` (filesystem) | Read/write vault | All operations |
| `research` (brave-search) | Live market research | `/enrich-domain`, `/generate-pre-brief` |
| `github` | Version control | Ongoing |

If a required MCP is not active, flag it before proceeding and offer to proceed with manual inputs instead.

---

## The Five Output Tracks

Every engagement ends with one primary output track recommendation. Use `/classify-output-track` after Session 4.

| Track | Urgency | Market | Solvability | Speed to Revenue |
|-------|---------|--------|-------------|-----------------|
| Micro-Tool | High | <$100M | Simple (AI) | 2–4 weeks |
| Productized Service | High | Any | Complex (human-in-loop) | Immediate |
| Course / SOP Pack | Medium | Any | Teachable | 2–3 weeks |
| Intelligence Report | Low | Any | Research only | 3–5 days |
| Funded Startup | High | $100M+ | Requires team + capital | 12–24 months |

---

## The BRIDGE Framework Integration

DIF maps to BRIDGE (Blueprint, Recruit, Interact, Distill, Generate, Execute) for operators in emerging market contexts. Key adaptation: first-party data from SMEs is non-negotiable in markets where published data is unreliable. The expert IS the market data.

See [BRIDGE.md](../BRIDGE.md) for the full mapping.

---

## Cross-Domain Intelligence

After each engagement, check `/patterns/cross-domain-repeaters.md` for patterns that match problems in other domains.

**Watch for:**
- The handoff gap (universal — healthcare, legal, finance, construction)
- Decision debt (deferred judgment under time pressure)
- The tacit expertise bottleneck (knowledge stuck in one person's head)
- The documentation lag (events not captured, creating information asymmetry)

If a new problem matches an existing pattern, add a cross-reference note in both files.

---

## Partnership Structure

The highest-leverage engagement structure is the SME co-build partnership:
- Revenue split: 50/50 on output revenue
- Startup cases: co-founder structure with equity
- The guarantee: if no validated opportunity after 4 sessions, the engagement is free

Always document partnership terms before beginning a co-build. Template at [templates/partnership-terms.md](../templates/partnership-terms.md).
