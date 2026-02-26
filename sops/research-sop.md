# Research SOP

> Pre-engagement research protocol. Run this before every SME engagement.

**Version:** 1.0
**Time:** 60–90 minutes
**Output:** Domain Pre-Brief (2 pages)
**Skill:** `/generate-pre-brief` (auto-drafts the Pre-Brief from research outputs)

---

## Why Research Before Talking to the Expert

The Domain Pre-Brief does two things:

1. **Signals credibility.** When the SME sees you've already mapped the official narrative, they understand the conversation will be different. You're not there to learn what's in the textbook — you're there to learn what isn't.

2. **Primes deeper conversation.** The Pre-Brief ends with a "provocation" — one hypothesis you hold lightly. The expert's reaction to it (especially their disagreement) is often the most valuable thing you take from Session 1.

The goal: walk in already knowing what everyone knows, so your time is spent on what nobody knows.

---

## The 2-Layer Research Stack

### Layer 1: Surface Research (30 minutes, Perplexity AI)

Open Perplexity.ai and run queries for each of these. Copy results into a working doc.

**Query 1: Market overview**
```
What is the current state of the [DOMAIN] market? Size, growth rate, key trends.
```
→ Looking for: market size estimate, CAGR, major structural changes

**Query 2: Incumbent landscape**
```
What are the major tools, platforms, and companies in [DOMAIN]? What are their weaknesses?
```
→ Looking for: 5 key players, what they're failing at, gaps in their offering

**Query 3: Recent funding**
```
What are the most recent venture capital investments in [DOMAIN] startups? 2024–2025.
```
→ Looking for: where VCs are betting, what problems they think are big enough

**Query 4: Regulatory context**
```
What are the key regulatory constraints and upcoming changes affecting [DOMAIN]?
```
→ Looking for: what's constrained, what's opening up, where the rules are changing

**Query 5: Practitioner sentiment**
```
What do [DOMAIN] practitioners complain about most? Common frustrations.
```
→ Looking for: the exact language of frustration from people inside the domain

**Query 6: Gap analysis**
```
What do [DOMAIN] practitioners say they need that doesn't exist yet?
```
→ Looking for: explicit unmet needs, wish-list items, workarounds that signal missing tools

---

### Layer 2: Deep Signal Mining (30 minutes, MCP-powered)

With the MCP stack active, run these queries in Claude Code. Results feed directly into the vault.

**GitHub: What's being hacked together?**

Open the GitHub MCP and search for repos in this domain. Look for:
- Open-source tools with activity but no commercial equivalent
- Issues that reveal what the tool can't do
- Forks of existing tools that add domain-specific features

Signal: if practitioners are building their own tooling, a commercial product is usually viable.

**ArXiv/PubMed: What have researchers identified?**

Search for recent papers in the domain that identify workflow gaps, inefficiencies, or unmet needs. Academic papers often surface problems years before commercial tools solve them.

Search terms: `[domain] + "gap" OR "challenge" OR "barrier" OR "unmet need"`

**LinkedIn: Who are the loudest practitioners?**

Use LinkedIn search to find the top 20–30 domain voices. Look at:
- What problems do they write about repeatedly?
- What tools do they praise vs. complain about?
- What do their followers ask them about in comments?

Their consistent topics are the domain's known frustrations. Their followers' questions are the latent demand.

**Crunchbase: What's been tried?**

Search for startups in this domain that have failed or pivoted. Understanding what didn't work is as valuable as knowing what's working.

---

## Synthesizing the Research

After completing both layers, run:
```
/generate-pre-brief
```

Claude reads your research notes and produces a first-draft Pre-Brief using the [pre-brief template](../templates/pre-brief.md).

**Review checklist before sending:**
- [ ] Less than 2 pages
- [ ] Written in plain language — no jargon the expert doesn't use
- [ ] The "official narrative" section accurately reflects published sources
- [ ] The "practitioners saying" section uses actual quotes/paraphrases from community discussions
- [ ] The "provocation" is specific and invites reaction (not a general statement)
- [ ] No invention — everything cites an actual signal

---

## What to Do When Research Is Thin

In some domains (niche industries, emerging markets, specialized sub-fields), there's very little published data. This is actually a signal — thin research means:

1. The domain is underserved by commercial intelligence
2. First-party data from the SME is MORE valuable, not less
3. The engagement itself may produce the first structured intelligence on this domain

Adapt the Pre-Brief:
- Focus Layer 1 on adjacent domains instead of the target domain
- Lead the Pre-Brief with: "Published data on this domain is sparse — which is part of why this conversation matters."
- Use the thin research as a provocation: "I couldn't find good data on [X]. Is that because it doesn't exist, or because nobody's looked?"

---

## After the Engagement

Store every Pre-Brief in the central brain:
```
/domains/[domain-name]/pre-brief.md
```

As the vault grows, new engagements in adjacent domains start with the existing pre-briefs as context. You walk in knowing not just the current domain — but how it connects to everything you've already studied.

This is how the knowledge base compounds.
