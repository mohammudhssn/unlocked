# Obsidian Vault Template

> A pre-built Obsidian vault for running the Unlocked / DIF methodology. Drop it in your vault directory and start your first domain.

---

## What's Included

The vault template includes the full central brain structure:

```
unlocked-vault/
├── _inbox/                        ← Drop raw notes here before filing
│
├── domains/                       ← One folder per domain engagement
│   └── _template/                 ← Copy this for every new domain
│       ├── README.md              ← Master domain record
│       ├── pre-brief.md           ← Domain Pre-Brief
│       ├── problem-map.md         ← Classified problem map
│       ├── knowledge-pillars.md   ← Pillar taxonomy
│       ├── insight-brief.md       ← Synthesized output
│       ├── gtm-canvas.md          ← GTM canvas
│       └── sessions/              ← Raw + synthesized session notes
│
├── patterns/                      ← Cross-domain intelligence (THE MOAT)
│   ├── cross-domain-repeaters.md  ← Problems that appear across multiple domains
│   ├── gtm-patterns.md            ← What GTM works for which output type
│   └── failure-modes.md           ← What kills early traction by track
│
├── sme-network/                   ← The expert relationship database
│   ├── _index.md                  ← Master list of all SMEs
│   └── _template.md               ← SME profile template
│
├── portfolio/                     ← Active ventures, tools, and courses
│   ├── active-tools/              ← Live micro-tools with metrics
│   ├── active-courses/            ← Live courses with metrics
│   └── active-startups/           ← Startups with cap table + milestones
│
├── resources/
│   ├── question-bank.md           ← Full interview question bank
│   ├── output-decision-tree.md    ← The track decision logic
│   └── value-ladder.md            ← Offer structure reference
│
└── _system/
    ├── INDEX.md                   ← Master navigation
    └── settings.md                ← Vault configuration notes
```

---

## Setup Instructions

### Option 1: Manual Setup (5 minutes)

1. Create a new folder in your Obsidian vault: `unlocked/`
2. Copy the folder structure above manually
3. Copy template files from this repo's `/templates/` into the corresponding vault folders
4. Open the vault in Obsidian and verify all links resolve

### Option 2: With MCP (Recommended, 15 minutes)

With the filesystem MCP configured (see [mcp-setup/](../mcp-setup/)), the vault becomes queryable by Claude. Every future session starts with Claude pre-loaded with everything you've built.

1. Point the filesystem MCP to your Obsidian vault directory
2. Set the `VAULT_PATH` in your MCP config
3. Run `/synthesize-session` — Claude will automatically save outputs to the right vault folders
4. Run `get_domain` (custom MCP) to query the knowledge base at the start of any session

### Option 3: Standalone (No MCP, No Obsidian)

If you prefer plain markdown files, the vault structure works identically in any folder on your computer. Use VS Code, Notion, or any markdown editor. The Claude skills and chatbot prompts work the same way — they just read and write files instead of Obsidian-linked notes.

---

## How the Vault Grows

**Week 1 (first engagement):**
- One domain folder, 4 session files, first problem map

**Month 1 (2–3 engagements):**
- 3 domain folders, patterns file starts populating, SME network begins

**Month 3 (5–8 engagements):**
- Cross-domain patterns become visible
- The patterns file is the most valuable thing in the vault
- SME network has warm intro paths

**Month 6+ (10+ engagements):**
- The vault is a proprietary intelligence database
- Pattern-level insights are worth selling independently
- VC briefings, research publications, accelerator partnerships become possible

---

## The MCP Interface

With the custom `domain-intelligence` MCP server active, you can query the vault with natural language:

**At the start of any engagement:**
```
"What do we know about problems in [adjacent domain]?"
```
→ MCP pulls from `/patterns/cross-domain-repeaters.md` and relevant domain folders

**Before writing a GTM canvas:**
```
"What GTM approaches have worked in similar domains?"
```
→ MCP pulls from `/patterns/gtm-patterns.md`

**Before making an output track decision:**
```
"What failure modes should I watch for with a SaaS build in a regulated domain?"
```
→ MCP pulls from `/patterns/failure-modes.md`

The vault is no longer a filing system. It's a co-founder with institutional memory.

---

## Vault Conventions

**File naming:** `[domain-slug]-[file-type].md` (e.g. `healthcare-problem-map.md`)

**Status tags (in frontmatter):**
```yaml
---
status: active | complete | archived
domain: [domain name]
session: [N]
date: [YYYY-MM-DD]
---
```

**Problem tagging in problem-map.md:**
```markdown
- [x] Urgent: [Problem] #urgent #tacit #$
- [ ] Important: [Problem] #important #explicit
- [ ] Latent: [Problem] #latent
```

**Cross-linking:** Use Obsidian `[[wikilinks]]` to connect:
- Domain problems → patterns
- SME profiles → domain folders
- Portfolio items → their originating domain folder

---

## Keeping the Vault Honest

The vault is only as good as the data you put in it. Rules:
1. **Nothing invented.** Every entry in the problem map traces to a session note.
2. **Update after every session,** not in batches weeks later.
3. **Cross-domain patterns require 2+ confirmations.** Don't add something to `cross-domain-repeaters.md` until you've seen it in at least 2 separate domains.
4. **Archive, don't delete.** Completed engagements move to `archived/` — they still feed the pattern engine.
