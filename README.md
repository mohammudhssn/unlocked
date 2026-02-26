# Domain Intelligence Framework

> **Turn subject matter expertise into market-ready ventures — systematically, in weeks.**

[![Built with Claude](https://img.shields.io/badge/Built%20with-Claude%20Opus%204-8A2BE2?logo=anthropic)](https://anthropic.com)
[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-0066CC)](https://modelcontextprotocol.io)
[![Methodology](https://img.shields.io/badge/Methodology-Interview%20→%20Insight%20→%20Venture-00AA66)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## The Problem This Solves

Subject matter experts are sitting on the most valuable asset in business: **deep domain knowledge**. They've lived the pain. They know what breaks, who it affects, and why existing solutions fall short.

What they lack is the language, structure, and systems to translate that knowledge into a venture.

Most "consulting" frameworks extract surface-level insight and hand back a report. This framework does something different — it treats the SME as a **co-founder**, their expertise as **proprietary data**, and uses AI to compress what would normally take months of market research into a structured, actionable map in weeks.

The output isn't a report. It's a launchpad.

---

## What This Is

The **Domain Intelligence Framework (DIF)** is a structured methodology for:

1. **Extracting** tacit domain knowledge from subject matter experts through guided interviews
2. **Structuring** that knowledge into pillars, problems, and opportunity spaces
3. **Enriching** it with market research, online signals, and competitive context
4. **Synthesizing** it into GTM-ready intelligence using Claude + a custom MCP stack
5. **Acting** — positioning the SME to build, partner, or validate their first product

It's been applied in healthcare. It works in any deep domain: law, engineering, finance, industrial operations, education, agriculture.

---

## The Five-Phase Process

```
┌─────────────────────────────────────────────────────────────────────┐
│                  DOMAIN INTELLIGENCE FRAMEWORK                      │
│                                                                     │
│  Phase 1         Phase 2         Phase 3         Phase 4   Phase 5  │
│  LISTEN     →   EXTRACT    →   STRUCTURE   →   ENRICH  →  BUILD    │
│                                                                     │
│  Deep SME        Problem         Knowledge       Market     GTM +   │
│  sessions        mining          pillars         research   Venture  │
│                                                                     │
│  [Claude]        [Claude]        [Claude]       [MCP:      [Claude  │
│  active          tool use        extended       Search +   skills   │
│  listening       prompts         thinking]      Files]     stack]   │
└─────────────────────────────────────────────────────────────────────┘
```

See [METHODOLOGY.md](METHODOLOGY.md) for the full interview protocol and session structure.

---

## The AI Stack

This framework is AI-native. Each phase uses a specific combination of Claude capabilities and MCP servers.

### Claude Model

All synthesis, extraction, and GTM ideation runs on `claude-opus-4-6`. Extended thinking is used for knowledge pillar mapping — the step where the model needs to hold the full domain context and reason across multiple sessions simultaneously.

### MCP Servers

| Server | Role | When Used |
|---|---|---|
| `@modelcontextprotocol/server-filesystem` | Reads/writes the knowledge vault (session notes, pillars, outputs) | All phases |
| `@modelcontextprotocol/server-brave-search` | Pulls live market data, competitor landscape, research papers | Phase 4 (Enrich) |
| `@modelcontextprotocol/server-github` | Versions the knowledge base, tracks changes across sessions | Ongoing |
| `domain-intelligence` *(custom)* | Serves the full SME knowledge graph to any Claude session on demand | Phase 5 (Build) |

The custom `domain-intelligence` MCP is what makes this composable — once the knowledge vault is built, it becomes a persistent context layer that can inform product decisions, pitch decks, content strategy, and GTM without re-running interviews.

See [mcp-setup/README.md](mcp-setup/README.md) for configuration.

### Claude Skills (Custom Slash Commands)

Each phase of the framework has a dedicated Claude skill — a custom slash command that loads the right prompt, context, and toolchain for that stage.

| Skill | Command | What It Does |
|---|---|---|
| Session Synthesizer | `/synthesize-session` | Extracts themes, problems, and threads from raw session notes |
| Problem Extractor | `/extract-problems` | Structures problems by urgency, frequency, and solvability |
| Pillar Mapper | `/map-pillars` | Organizes domain knowledge into a structured taxonomy |
| Research Enricher | `/enrich-domain` | Cross-references internal insights with market data via search MCP |
| GTM Canvas | `/gtm-canvas` | Generates positioning, ICP, channels, and first-move strategy |

See [claude-skills/README.md](claude-skills/README.md) for setup and usage.

---

## Why SMEs Are the Unfair Advantage

Most AI-assisted research starts with a search query. This framework starts with a person who has spent years — sometimes decades — accumulating pattern recognition that no search engine has indexed.

The interview methodology is designed to surface **three types of knowledge**:

- **Explicit knowledge** — what they can already articulate (processes, terminology, known problems)
- **Tacit knowledge** — what they know but can't easily explain (workarounds, unwritten rules, felt friction)
- **Latent knowledge** — what they know but don't realize is valuable (the thing they mention offhand that turns out to be the biggest opportunity)

The third type is where the real insight lives. The interview protocol is engineered to find it.

---

## Case Studies

### Healthcare: Perioperative Workflow
**Domain:** Anesthesiology / Operating Room Operations
**SME:** Board-certified anesthesiologist, 12+ years clinical practice
**Sessions:** 4 × 60-minute structured interviews
**Output:** 3 validated problem spaces, 1 prioritized opportunity, GTM brief

→ [View case study](case-studies/healthcare/README.md)

---

## Repository Structure

```
domain-intelligence-framework/
│
├── README.md                      ← You are here
├── METHODOLOGY.md                 ← Full interview protocol + synthesis guide
├── QUICKSTART.md                  ← Run your first session in 30 minutes
│
├── templates/
│   ├── session-notes.md           ← Interview session capture template
│   ├── problem-map.md             ← Structured problem extraction
│   ├── knowledge-pillar.md        ← Domain pillar documentation
│   ├── insight-brief.md           ← Output synthesis template
│   └── gtm-canvas.md              ← Go-to-market mapping
│
├── mcp-setup/
│   ├── README.md                  ← MCP configuration guide
│   ├── claude_desktop_config.json ← Drop-in MCP config
│   └── prompts/                   ← Raw prompts for each MCP interaction
│
├── claude-skills/
│   ├── README.md                  ← Skills overview and setup
│   └── commands/                  ← Individual skill definitions
│
├── case-studies/
│   └── healthcare/                ← Anonymized healthcare case study
│
└── .claude/
    ├── CLAUDE.md                  ← Context file loaded into every session
    └── commands/                  ← Local Claude skill definitions
```

---

## Who This Is For

- **Venture builders** working with domain experts who have deep knowledge but no product/GTM background
- **Operators** running discovery for new products in regulated or technical domains
- **Consultants** who want a systematic, repeatable methodology for turning expertise into ventures
- **SMEs** ready to productize their knowledge but don't know where to start

---

## Guiding Principle

> *The goal is not to consult for the expert. It's to build with them — where their domain knowledge is the unfair advantage and your systems are the acceleration layer.*

---

## Get Started

1. Read [METHODOLOGY.md](METHODOLOGY.md) to understand the full interview protocol
2. Follow [QUICKSTART.md](QUICKSTART.md) to run your first session
3. Set up the MCP stack: [mcp-setup/README.md](mcp-setup/README.md)
4. Install Claude skills: [claude-skills/README.md](claude-skills/README.md)
