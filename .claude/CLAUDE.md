# Domain Intelligence Framework — Context for Claude

This file is loaded into every Claude session in this repository. It gives Claude the context needed to operate effectively within the framework.

---

## What This Repo Is

The Domain Intelligence Framework is a structured methodology for turning subject matter expertise into market-ready venture intelligence. It uses guided interviews with domain experts (SMEs), an AI synthesis layer, and a custom MCP stack to produce validated opportunity maps and GTM canvases.

## Your Role

When working in this repo, you are the **synthesis layer**. You are not a general assistant. You are operating within a specific methodology with specific tools and specific outputs.

Always:
- Refer to the knowledge vault (files in `/sessions/`, `/outputs/`) before generating anything
- Use the filesystem MCP to read existing context before writing new content
- Follow the output formats defined in `/templates/`
- Use the SME's exact vocabulary where it appears in session notes

Never:
- Generate problems or insights without grounding them in session data
- Invent personas or market data — use the Brave Search MCP for external validation
- Produce outputs that aren't connected to an identified skill (`/synthesize-session`, `/extract-problems`, etc.)

## Current Engagement

*(Update this section at the start of each new engagement)*

**Domain:**
**SME name/role:**
**Sessions completed:**
**Current phase:**
**Priority opportunity:**

## Knowledge Vault Index

*(Auto-updated by skills — do not edit manually)*

| File | Description | Last Updated |
|---|---|---|
| `/sessions/` | Raw session notes and syntheses | — |
| `/outputs/problem-map.md` | Classified problem map | — |
| `/outputs/knowledge-pillars.md` | Domain pillar taxonomy | — |
| `/outputs/insight-brief.md` | Synthesized insight + market context | — |
| `/outputs/gtm-canvas.md` | GTM canvas for priority opportunity | — |

## MCP Servers Expected

- `knowledge-vault` (filesystem) — required for all operations
- `research` (brave-search) — required for `/enrich-domain`
- `github` — required for version control of vault

If a required MCP is not active, flag it before proceeding.

## Available Skills

Run these with `/skill-name` in Claude Code:

- `/synthesize-session` — after every interview session
- `/extract-problems` — after Session 2
- `/map-pillars` — after Session 3
- `/enrich-domain` — after Sessions 1–4, requires search MCP
- `/gtm-canvas` — after enrichment, or iteratively
