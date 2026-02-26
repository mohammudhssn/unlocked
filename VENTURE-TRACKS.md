# Venture Tracks

> After the Problem Map is built, let the data decide what to build.

Every DIF engagement produces one primary output track. The track is determined by three criteria: **urgency of the problem**, **size of the addressable market**, and **speed to revenue**. This removes guesswork and sets expectations with your SME partner upfront.

Start every engagement by saying: *"We're going to run the process and let the data decide which track this goes down."* That framing keeps the process scientific rather than speculative.

---

## The Decision Tree

```
Is the problem urgent enough that people would pay to solve it TODAY?
│
├─ YES → Is it a $100M+ market?
│        │
│        ├─ YES → Track 5: Funded Startup
│        │
│        └─ NO  → Is it solvable with a simple tool?
│                 │
│                 ├─ YES → Track 1: Micro-Tool
│                 │
│                 └─ NO  → Track 2: Productized Service
│
└─ NO  → Is the expert's knowledge worth packaging for others?
          │
          ├─ YES → Track 3: Course / SOP Pack
          │
          └─ NO  → Track 4: Intelligence Report
                    (plant the seed, revisit in 6 months)
```

---

## Track 1: Micro-Tool

**Timeline to ship:** 2–4 weeks
**Revenue model:** Usage-based or monthly subscription, $29–99/mo
**Revenue potential:** $3k–30k/mo at scale (across multiple tools)

**What it is:** A focused AI-powered tool that solves one high-frequency problem in the domain. Built with Claude API + a simple form UI. No engineering team required.

**When the data points here:**
- The problem is specific and repetitive
- Practitioners have it daily or weekly
- Existing solutions are manual, clunky, or non-existent
- The solution is a workflow enhancement, not a workflow replacement

**How to build it:**
1. Extract the top 1–2 urgent problems from the Problem Map
2. Define the minimum valuable output (what does the tool produce?)
3. Build a prompt + form UI using Claude API
4. Deploy to tools.mohammud.com or a subdomain
5. SME shares with their network → first users → feedback loop

**Distribution:** SME's domain peers are the first audience. Their 2,000 LinkedIn followers are all potential users. This is targeted distribution no ad spend can replicate.

**Examples:**
- A nurse scheduling conflict detector — flags staffing gaps before they become crises
- A legal brief summarizer — structures case summaries for a specific niche
- A pre-op briefing formatter — structures the "pre-op quiet" decision window into a checklist

**AI leverage:** Claude API handles the core logic. The tool doesn't need to be perfect — it needs to be useful enough that someone would reach for it daily.

---

## Track 2: Productized Service

**Timeline to ship:** Immediate (start billing within days)
**Revenue model:** Fixed price per deliverable
**Revenue potential:** $2k–10k per engagement

**What it is:** A documented, repeatable service where AI handles the heavy lifting and a human handles quality assurance. The 0→1 Sprint is this track.

**When the data points here:**
- The problem is complex enough that humans still need to be in the loop
- The output is a document, analysis, or decision — not a software feature
- The SME's credibility is essential to the value proposition
- The workflow is repeatable but not yet automatable end-to-end

**How to build it:**
1. Document the process as an SOP (use `/generate-sop`)
2. Identify which steps Claude handles vs. which require human judgment
3. Package it with a fixed scope, timeline, and deliverable
4. Price based on value delivered, not time spent
5. Use the SME's case study as proof

**The SOP is the product.** Once the process is documented, anyone trained on it can deliver it. This is how the service scales beyond the original practitioner.

**Examples:**
- The 0→1 Validation Sprint (14-day idea-to-signal engagement, $2,500)
- A Domain Intelligence Report service ($1,500 per domain)
- A clinical workflow audit packaged as a fixed-scope engagement

**AI leverage:** Claude handles research enrichment, synthesis, and first drafts. Human QA time drops from hours to minutes.

---

## Track 3: Course / SOP Pack

**Timeline to ship:** 2–3 weeks to launch
**Revenue model:** One-time purchase or subscription
**Revenue potential:** $297–1,997 per sale, scale with SME's audience

**What it is:** The expert's knowledge packaged for others who want to acquire it. Either a structured curriculum or a set of documented SOPs that transfer their process.

**When the data points here:**
- The expert's knowledge has a steep learning curve
- Others in the domain want to acquire this knowledge
- There's an identifiable audience willing to pay for it
- The tacit knowledge can be articulated well enough to teach

**The SOP track specifically:**
SOPs codify tacit knowledge into transferable process. They're often the bridge between a knowledge engagement and a software product. They also sell — domain peers will pay for a documented playbook that compresses their learning curve.

After knowledge mapping with `/map-pillars`, run `/generate-sop` to structure the expert's process into a repeatable SOP document. The SOP becomes:
- A standalone product
- The playbook for any tool or software built from the engagement
- The foundation for a course curriculum
- Internal documentation if the engagement goes startup track

**Distribution:** The SME's existing audience (email list, LinkedIn, community) is the launch channel. Their credibility validates the content.

**Examples:**
- "Hemodynamics for Residents" — from a DIF engagement with an anesthesiologist
- A construction project handover SOP Pack — for PMs in mid-size firms
- A legal matter management playbook — structured from a senior lawyer's 20 years of tacit process

**AI leverage:** Claude generates the SOP structure from session notes. Course outlines emerge directly from knowledge pillars. Production time compresses from weeks to days.

---

## Track 4: Intelligence Report

**Timeline to ship:** 3–5 days after sessions complete
**Revenue model:** One-time fee, $500–2,000
**Revenue potential:** Best as the bottom of the ladder, not the ceiling

**What it is:** A structured synthesis of everything the DIF engagement produced — problem map, knowledge pillars, market context, and preliminary GTM hypotheses — packaged as a 2–3 page document any stakeholder can act on.

**When the data points here:**
- No urgent problem surfaced with clear commercial potential
- The domain is worth tracking but not ready to build in
- The SME isn't ready to co-build yet
- The engagement was exploratory — plant the seed, revisit later

**This is never a failure.** Every Intelligence Report feeds the central brain. Every domain enriches the cross-domain pattern library. At 20–30 domains, the pattern library alone is worth more than any single engagement. It becomes a VC briefing asset, a research publication, or the foundation of a fund thesis.

**Who pays for it:**
- VCs doing domain discovery before making bets
- Corporates doing innovation scouting
- Accelerators building sector expertise
- The SME themselves — getting paid for their own knowledge for the first time

---

## Track 5: Funded Startup

**Timeline:** 12–24 months to meaningful traction
**Revenue model:** VC-backed, path to acquisition or IPO
**Revenue potential:** Uncapped — this is the high-risk, high-upside track

**What it is:** A full company. Team, capital, board, the works. The problem is systemic enough, the market large enough, and the regulatory or structural dynamics complex enough that a micro-tool or service isn't the right vehicle.

**When the data points here:**
- The problem affects millions of people or touches a $100M+ market
- Regulatory or market structure change is required to solve it
- The SME's credibility is a genuine unfair advantage for fundraising
- You've validated commercial signal during the DIF engagement

**The co-founder structure:**
- SME takes domain/technical title (their expertise is the moat)
- You take execution (DIF + AI stack + build)
- Begin with documented IP, revenue share, or equity agreement from day one

**AI leverage:** The DIF output becomes the founding documents — the problem space is validated, the ICP is defined, the market context is researched. You walk into a first fundraising conversation with more data than most founders have after 6 months of building.

**Examples:**
- A pre-op coordination tool for anesthesiology departments (TAC track)
- A stablecoin payment infrastructure for underserved corridors
- A construction project intelligence platform built on domain expert data

---

## The SOP Layer: Cross-Track

Regardless of which track the engagement goes down, always run `/generate-sop` after Session 3.

**Why:** Tacit knowledge evaporates. The expert retires, changes roles, or moves on. The SOP preserves the knowledge in a transferable form — and turns it into a product.

**The SOP is:**
- A product (sell it to domain peers)
- A playbook (run the service without the original expert)
- A founding document (the startup's internal process bible)
- A training asset (onboard new team members fast)

Every engagement produces an SOP. Every SOP feeds the central brain. Over time, the SOP library is a standalone asset — a body of structured, transferable expert knowledge across domains.

---

## Connecting the Tracks

Tracks evolve. A micro-tool that finds product-market fit becomes a SaaS. A productized service that gets traction becomes a startup. An intelligence report that surfaces a massive problem becomes a co-build partnership.

Start with the track the data points to. Stay ready to upgrade.

The 14-day 0→1 Sprint is the fastest path to finding out which track is right:
- 4 structured sessions surface the problem map
- The enrichment layer validates commercial signal
- The output track decision is data-driven, not speculative

→ See [PARTNERSHIP.md](PARTNERSHIP.md) for how to structure the co-build across all tracks.
→ See [VALUE-LADDER.md](VALUE-LADDER.md) for how each track fits the commercial model.
