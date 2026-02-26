# Unlocked

> **The methodology for turning expert knowledge into ventures.**
> Powered by the Domain Intelligence Framework (DIF).

[![Built with Claude](https://img.shields.io/badge/Built%20with-Claude%20Opus%204-8A2BE2?logo=anthropic)](https://anthropic.com)
[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-0066CC)](https://modelcontextprotocol.io)
[![Obsidian Ready](https://img.shields.io/badge/Obsidian-Vault%20Included-7C3AED)](obsidian-vault/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## The Insight

You have more value trapped in your head than you realize.

Experts trade time for money forever — or they productize their knowledge once and earn forever. The gap between "I know this" and "this is a product" is not skill. It's structure.

**Unlocked is the structure.**

---

## What This Is

Three things stacked on top of each other:

**1. An intelligence business**
Every engagement extracts domain knowledge and feeds a growing private database. After ten domains, you have cross-domain insights. After fifty, you're sitting on something no one else has — a proprietary signal map that no search engine has indexed.

**2. A co-creation studio**
SMEs bring their knowledge and their network. You bring structure, AI leverage, and build capacity. Together you ship products — tools, courses, SaaS, or startups — in weeks instead of years.

**3. A distribution machine**
Every SME you work with brings their domain peers as your next audience. Each engagement is a referral channel. The flywheel compounds.

The methodology that powers all three is the **Domain Intelligence Framework (DIF)** — a structured, AI-native process for extracting expert knowledge, enriching it with market signals, and turning it into a launchpad.

---

## The Five-Phase Process

```
┌─────────────────────────────────────────────────────────────────────────┐
│                         UNLOCKED / DIF                                  │
│                                                                         │
│  Phase 1      Phase 2      Phase 3      Phase 4      Phase 5            │
│  LISTEN   →  EXTRACT   →  STRUCTURE →  ENRICH   →   BUILD              │
│                                                                         │
│  Structured   Problem      Knowledge    Market        Venture           │
│  SME          mining       pillars +    research +    track +           │
│  sessions     (tacit +     problem      competitive   GTM               │
│               latent)      map          signals       activation        │
│                                                                         │
│  [Discovery   [Claude      [Claude      [MCP:         [Claude           │
│  Bot pre-     tool use     extended     Search +      skills            │
│  loads]       prompts]     thinking]    GitHub]       stack]            │
└─────────────────────────────────────────────────────────────────────────┘
```

**Maps to the BRIDGE Framework** (for emerging market operators):

| DIF Phase | BRIDGE Stage | What Happens |
|---|---|---|
| Listen | **B**lueprint + **R**ecruit | Research plan + find/engage the right SMEs |
| Extract | **I**nteract | Structured data collection through guided sessions |
| Structure | **D**istill | Analyze raw insight into a classified problem map |
| Enrich | **G**enerate | Transform findings into market-validated intelligence |
| Build | **E**xecute | From insight to product — prototype, validate, launch |

See [BRIDGE.md](BRIDGE.md) for how to apply this in emerging market contexts, and [VENTURE-STUDIO.md](VENTURE-STUDIO.md) for the RDG venture studio model that DIF is built to power.

---

## The Value Ladder

Every SME engagement slots into a value ladder. Free tools generate leads. The ladder converts them.

```
FREE              LOW-TICKET          MID-TICKET          HIGH-TICKET         PARTNERSHIP
─────────         ────────────────    ────────────────    ─────────────────   ──────────────
Domain            Unlocked            Domain              Full Unlocked       Co-build output
Question          Starter Kit         Intelligence        Engagement          with equity /
Generator         ($97–197)           Session             ($3,000–5,000)      rev share 50/50
                  templates +         ($1,500)
AI Problem        prompts +           1 expert,           2-week cycle,       Funded startup
Prioritizer       question bank       full report         full output         track (equity)

GTM Fit                               0→1 Validation
Calculator                            Sprint ($2,500)
```

The 0→1 Sprint (14-day, AI-leveraged engagement) slots into the mid-ticket tier and feeds directly into the high-ticket and partnership tracks.

See [VALUE-LADDER.md](VALUE-LADDER.md) for Hormozi-framed positioning, the guarantee structure, and value stack.

---

## Output Decision Tree

After the Problem Map is built, let the data decide what to build. This removes speculation and sets expectations upfront.

```
Is the problem urgent enough that people would pay to solve it TODAY?
│
├─ YES → Is it a $100M+ market?
│        │
│        ├─ YES → Startup track (co-found, raise capital, build team)
│        │
│        └─ NO  → Is it solvable with a simple tool?
│                 │
│                 ├─ YES → Micro-tool (SaaS, $29–99/mo, Claude API)
│                 │
│                 └─ NO  → Productized service or API
│
└─ NO  → Is the expert's knowledge worth packaging for others?
          │
          ├─ YES → Course or template pack ($297–1,997)
          │         OR SOP Pack (codify their tacit process)
          │
          └─ NO  → Intelligence Report only ($500–2,000)
                    (plant the seed, revisit in 6 months)
```

See [VENTURE-TRACKS.md](VENTURE-TRACKS.md) for the full breakdown of all five tracks — micro-tool to funded startup.

---

## The AI Stack

This framework is AI-native. Four ways to plug it into your existing setup:

### Option 1: Drop-In Claude Skills
Custom slash commands — copy them into `.claude/commands/` and they're live immediately in Claude Code.

| Skill | Command | When to Run |
|---|---|---|
| Session Synthesizer | `/synthesize-session` | After every interview session |
| Problem Extractor | `/extract-problems` | After Session 2 |
| Pillar Mapper | `/map-pillars` | After Session 3 |
| Research Enricher | `/enrich-domain` | Before Sessions 5–6 |
| GTM Canvas | `/gtm-canvas` | After enrichment |
| Pre-Brief Generator | `/generate-pre-brief` | Before Session 1 |
| SOP Generator | `/generate-sop` | When codifying expert process |
| Output Track Classifier | `/classify-output-track` | After Problem Map is built |

→ [claude-skills/](claude-skills/) · Setup in 2 minutes.

### Option 2: Copy-Paste Chatbot Prompts
Three standalone bots — paste the system prompt into any Claude interface (Claude.ai, API, or custom app) and run.

| Bot | When | What It Does |
|---|---|---|
| **Discovery Bot** | Before Session 1 | Runs 20–30 min domain scan; expert pre-loads before your live session |
| **Synthesis Bot** | After each session | Extracts themes, flags contradictions, generates follow-up queue |
| **GTM Bot** | After Problem Map | Tests GTM assumptions, surfaces distribution paths, identifies ICP |

→ [chatbot-prompts/](chatbot-prompts/) · Zero setup required.

### Option 3: MCP Server Config
One JSON file to connect the knowledge vault to Claude Desktop. Makes all sessions stateful — Claude walks in knowing everything from previous sessions.

```json
{
  "mcpServers": {
    "knowledge-vault": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/your-vault"]
    },
    "research": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-brave-search"],
      "env": { "BRAVE_API_KEY": "your-key" }
    }
  }
}
```

→ [mcp-setup/](mcp-setup/) · Full config + custom `domain-intelligence` MCP.

### Option 4: Obsidian Vault Template
A downloadable Obsidian vault with the full central brain structure pre-built — domains, patterns, SME network, portfolio. Drop in your vault directory and start using.

→ [obsidian-vault/](obsidian-vault/) · Works with or without MCP.

---

## The Central Brain

The knowledge vault isn't just storage — it's a flywheel.

```
1. Run engagement in domain X
   → feeds /domains/healthcare/
         ↓
2. Pattern recognition: "this looks like domain Y's problem"
   → feeds /patterns/cross-domain-repeaters.md
         ↓
3. Cross-domain insight surfaces:
   "medication handoff in healthcare = invoice reconciliation in accounting"
         ↓
4. New, broader product category identified
         ↓
5. MCP surfaces this insight automatically at the START of the next
   related engagement — you walk in pre-armed
```

**What the brain becomes at scale:**

| Brain Size | What You Have | Who Pays for It |
|---|---|---|
| 5 domains | Deep single-domain intelligence | SME partners, first clients |
| 10 domains | Cross-domain pattern library begins | Consultancies, accelerators |
| 20 domains | Proprietary intelligence database | VCs, research orgs, corporates |
| 50 domains | Comprehensive cross-sector signal map | Fund thesis, publications, speaking |

At scale, this is the moat. No competitor can replicate it. It accumulates every time you run an engagement.

See [obsidian-vault/](obsidian-vault/) for the folder structure and [mcp-setup/](mcp-setup/) for making it queryable.

---

## The SME Partnership Model

The highest-leverage engagement structure. Not consulting — co-building.

**What the SME brings:** Context (irreplaceable knowledge) · Credibility (their reputation validates the output) · Community (their network is your launch channel)

**What you bring:** Structure (the DIF methodology) · Speed (AI compresses months to 2 weeks) · Build (you ship the product)

**The deal:** Full engagement → co-build the output → 50/50 revenue split (equity in startup cases)

**The pitch:**
> "You've spent years building expertise nobody can buy. I've built a system that turns that expertise into a product that earns while you sleep. I run the whole process. You bring your knowledge and your network. We split what it produces."

See [PARTNERSHIP.md](PARTNERSHIP.md) for deal structure, partnership terms template, and the full pitch framework.

---

## SOPs: Codifying Expert Knowledge

One output track that is often overlooked: **SOP Packs**.

When an expert's tacit knowledge is systematized into a documented SOP, it becomes:
- A product in itself (templated, sold to domain peers)
- The foundation for a course
- The playbook for any venture built from the engagement
- The first version of internal documentation for a startup

DIF generates SOPs automatically. After knowledge mapping, `/generate-sop` structures the expert's process into a repeatable, transferable document.

This is how you turn tacit knowledge into leverage. The expert no longer has to be in the room for the knowledge to deliver value.

→ [sops/](sops/) · See the engagement, research, and synthesis SOPs that power each DIF cycle.

---

## The BRIDGE Framework Connection

For operators working in emerging markets, the BRIDGE Framework (Blueprint, Recruit, Interact, Distill, Generate, Execute) maps precisely to DIF.

Key adaptations for these markets:
- **First-party data is non-negotiable.** Published market data is often 3–5 years old, Westernized, or simply wrong. The SME IS the market data.
- **Relationships precede transactions.** The Recruit phase takes longer — trust is the currency.
- **Local context beats global frameworks.** The problems that matter, the payment models that work, the distribution channels that reach people — all different. DIF surfaces this from the inside out.

The BRIDGE Framework reinforces DIF's core thesis: the insight is inside the expert, not in a desk research report. Structure it correctly and it becomes a durable advantage.

→ [BRIDGE.md](BRIDGE.md) for the full mapping and market adaptation guide.

---

## Who This Is For

**Non-technical path (start here):**
- SMEs ready to productize their expertise but unsure where to start
- Operators building a knowledge-to-ventures studio
- Consultants wanting a repeatable methodology for domain intelligence

→ Start with [QUICKSTART.md](QUICKSTART.md) → Use the [chatbot prompts](chatbot-prompts/) → Build in the [Obsidian vault](obsidian-vault/)

**Technical path (go deeper):**
- Builders who want to fork and integrate DIF into their stack
- AI practitioners building custom intelligence pipelines
- Studios wanting to run this at scale with Claude + MCP

→ Start with [mcp-setup/](mcp-setup/) → Install [Claude skills](claude-skills/) → Build the custom MCP

---

## Case Studies

### Healthcare: Perioperative Workflow
**Domain:** Anesthesiology / Operating Room Operations
**SME:** Board-certified anesthesiologist, 12+ years clinical practice
**Sessions:** 4 × 60-minute structured interviews
**Output:** Problem Map (11 problems classified) · Knowledge Pillars (5) · GTM Canvas · Insight Brief

Key find: "Pre-op quiet" — a 15-minute window before surgery where the most consequential decisions happen, invisible to every existing clinical system. Surfaced in Session 1 from an offhand comment. No survey or desk research would have found it.

→ [View case study](case-studies/healthcare/README.md)

---

## Repository Structure

```
domain-intelligence-framework/
│
├── README.md                          ← You are here
├── METHODOLOGY.md                     ← Full interview protocol + synthesis guide
├── QUICKSTART.md                      ← Two paths: non-technical + technical
├── VENTURE-TRACKS.md                  ← 5 output tracks: micro-tool → funded startup
├── VALUE-LADDER.md                    ← Hormozi-framed value ladder + offer structure
├── PARTNERSHIP.md                     ← SME co-build model + deal terms
├── VENTURE-STUDIO.md                  ← The RDG venture studio model + dual-track system
├── BRIDGE.md                          ← BRIDGE Framework integration for emerging markets
│
├── chatbot-prompts/
│   ├── README.md                      ← Overview + when to use each bot
│   ├── discovery-bot.md               ← Full system prompt: pre-session domain scan
│   ├── synthesis-bot.md               ← Full system prompt: post-session synthesis
│   └── gtm-bot.md                     ← Full system prompt: GTM assumption testing
│
├── templates/
│   ├── session-notes.md               ← Interview session capture
│   ├── gtm-canvas.md                  ← Go-to-market mapping
│   ├── pre-brief.md                   ← Domain Pre-Brief (run before session 1)
│   ├── domain-brain.md                ← Central brain domain entry
│   ├── sme-profile.md                 ← SME network profile
│   ├── sop-pack.md                    ← SOP generation from expert knowledge
│   └── partnership-terms.md           ← Partnership agreement structure
│
├── obsidian-vault/
│   ├── README.md                      ← Setup + download instructions
│   └── vault-template/                ← Pre-built vault structure (drop in and go)
│
├── sops/
│   ├── README.md                      ← When and how to use SOPs
│   ├── engagement-sop.md              ← Running a full engagement end-to-end
│   ├── research-sop.md                ← Pre-engagement research protocol
│   └── synthesis-sop.md               ← Synthesis + output production process
│
├── mcp-setup/
│   ├── README.md                      ← MCP configuration guide
│   ├── claude_desktop_config.json     ← Drop-in MCP config
│   └── prompts/                       ← Raw prompts for each MCP interaction
│
├── claude-skills/
│   ├── README.md                      ← Skills overview + setup
│   └── commands/                      ← Individual skill definitions
│
├── case-studies/
│   └── healthcare/                    ← Anonymized healthcare case study
│
└── .claude/
    ├── CLAUDE.md                      ← Context loaded into every session
    └── commands/                      ← Local Claude skill definitions
```

---

## Get Started

**Not technical? Start here:**
1. Read [QUICKSTART.md](QUICKSTART.md) — non-technical path
2. Copy the [Discovery Bot prompt](chatbot-prompts/discovery-bot.md) into Claude.ai
3. Download the [Obsidian vault template](obsidian-vault/) and start your first domain

**Technical? Start here:**
1. Set up the MCP stack: [mcp-setup/README.md](mcp-setup/README.md)
2. Install Claude skills: [claude-skills/README.md](claude-skills/README.md)
3. Run [METHODOLOGY.md](METHODOLOGY.md) — full protocol

**Want to partner?**
See [PARTNERSHIP.md](PARTNERSHIP.md) or visit [mohammud.com/unlocked](https://mohammud.com/unlocked).

---

> *The goal is not to consult for the expert. It's to build with them — where their domain knowledge is the unfair advantage and your systems are the acceleration layer.*
