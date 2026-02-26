# Claude Skills

Claude skills are custom slash commands that load the right prompt, context, and toolchain for each phase of the Domain Intelligence Framework. Instead of writing prompts from scratch each session, you invoke a skill and Claude knows exactly what to do.

Skills are defined as markdown files in `.claude/commands/`. When you type `/skill-name` in Claude Code, it loads the skill definition and runs it with your current context.

---

## Available Skills

| Skill | Command | Phase | What it does |
|---|---|---|---|
| Session Synthesizer | `/synthesize-session` | After every session | Extracts themes, problems, vocabulary, and threads from raw notes |
| Problem Extractor | `/extract-problems` | Phase 2 | Classifies problems by urgency, frequency, solvability, and market opportunity |
| Pillar Mapper | `/map-pillars` | Phase 3 | Builds a structured knowledge taxonomy from session context |
| Research Enricher | `/enrich-domain` | Phase 4 | Cross-references internal insights with live market data via search MCP |
| GTM Canvas | `/gtm-canvas` | Phase 5–6 | Generates ICP, positioning angles, channel hypotheses, and pricing |

---

## Installation

Skills live in `.claude/commands/` at the root of this repo. If you're using Claude Code, they're available automatically when you open this directory.

```bash
# Verify skills are available
ls .claude/commands/
```

You should see:
```
synthesize-session.md
extract-problems.md
map-pillars.md
enrich-domain.md
gtm-canvas.md
```

---

## Skill Definitions

### `/synthesize-session`

**When to use:** Immediately after each interview session, before the next one.

**What Claude does:**
1. Reads the latest session notes from the vault (via filesystem MCP)
2. Identifies 3–5 key themes from the session
3. Extracts any problems mentioned (raw, unclassified)
4. Builds a vocabulary glossary from the expert's language
5. Flags the top 3 threads to pull in the next session
6. Writes a structured synthesis back to the vault

**Output:** `sessions/session-0N-synthesis.md`

---

### `/extract-problems`

**When to use:** After Session 2 (Problem Mining), and iteratively as more sessions surface new problems.

**What Claude does:**
1. Reads all session syntheses from the vault
2. Consolidates raw problem mentions into discrete problem statements
3. Classifies each problem:
   - **Type:** Urgent / Important / Latent
   - **Frequency:** How often it was mentioned across sessions
   - **Solvability:** High / Medium / Low (based on SME's own comments)
   - **Market signal:** Whether the problem is domain-specific or cross-domain
4. Ranks problems by opportunity score (urgency × frequency × solvability)
5. Writes structured problem map to vault

**Output:** `outputs/problem-map.md`

---

### `/map-pillars`

**When to use:** After Session 3 (Knowledge Mapping).

**What Claude does:**
1. Reads all session notes and the problem map
2. Identifies the underlying knowledge clusters (pillars) that structure the domain
3. For each pillar, documents:
   - Plain-language definition
   - Why it matters
   - Common market misconceptions
   - SME's specific edge in this area
   - Connection to identified problems
4. Maps relationships between pillars (what depends on what)
5. Flags intersections between pillars and high-priority problems — these are the highest-signal opportunity spaces

**Output:** `outputs/knowledge-pillars.md`

---

### `/enrich-domain`

**When to use:** After the knowledge vault is built (Sessions 1–4 complete). Requires Brave Search MCP.

**What Claude does:**
1. Reads the problem map and knowledge pillars
2. For each high-priority problem, generates targeted search queries
3. Executes searches via Brave Search MCP
4. Cross-references results against internal insights:
   - **Confirmed:** Internal and external signals agree → high confidence
   - **Diverged:** They disagree → flag for further investigation
   - **Novel:** External research surfaces something not in sessions → add to problem map
5. Adds market size estimates, competitor landscape, and adjacent products
6. Writes enriched insight brief

**Output:** `outputs/insight-brief.md`

---

### `/gtm-canvas`

**When to use:** After enrichment. Can be run iteratively as hypotheses are tested.

**What Claude does:**
1. Reads the full knowledge vault: problems, pillars, solution space notes, market research
2. Generates a GTM canvas covering:
   - **ICP:** Who has this problem most acutely? (Pulled from SME's "who would you call" answers)
   - **Positioning:** What's the angle that makes this obviously the right solution?
   - **Channels:** Where does the ICP already gather, read, and trust?
   - **Pricing hypotheses:** What would feel like a fair exchange? What would feel like a steal?
   - **First move:** The single highest-leverage action to validate the opportunity
3. Flags the top 3 risk assumptions that need validation before building

**Output:** `outputs/gtm-canvas.md`

---

## Extending the Skill Stack

Skills are just markdown prompt files. You can add your own for domain-specific use cases:

```bash
# Create a new skill
touch .claude/commands/my-skill.md
```

Format:
```markdown
# Skill: [Name]

## Context
[What you want Claude to know before running this skill]

## Instructions
[What Claude should do, step by step]

## Output
[What the output should look like and where it should go]
```

Skills can reference MCP tools directly in their instructions — e.g., "use the filesystem MCP to read all files in /sessions/ before proceeding."
