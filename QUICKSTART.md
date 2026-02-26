# Quickstart

> Two paths. Pick yours.

---

## Path A: Non-Technical (Start in 10 minutes)

No MCP setup. No Claude Code. Just Claude.ai and a copy of this repo.

### Step 1: Pick your domain and expert (2 min)

Think about who you want to run a DIF engagement with. This person should:
- Have 10+ years in a specific domain
- Have a peer network (LinkedIn presence, community involvement)
- Be willing to do 4 × 60-minute conversations

If you don't have someone in mind yet, identify a domain you know well enough to have a meaningful conversation — and use yourself as the test case first.

### Step 2: Run the pre-engagement research (30 min)

Follow the [Research SOP](sops/research-sop.md). Use Perplexity AI for Layer 1 (30 min). Skip Layer 2 for now — you can add MCP later.

Produce a Domain Pre-Brief using the [pre-brief template](templates/pre-brief.md). Keep it under 2 pages. End with a provocation.

### Step 3: Send the Discovery Bot (5 min)

Open [Claude.ai](https://claude.ai) → New conversation. Paste the system prompt from [chatbot-prompts/discovery-bot.md](chatbot-prompts/discovery-bot.md). Fill in the domain and your pre-brief summary.

Send the link to your SME or work through it with them on a call.

### Step 4: Set up the Obsidian vault (5 min)

If you use Obsidian: follow the setup in [obsidian-vault/README.md](obsidian-vault/README.md). Create your first domain folder from the template.

If you don't use Obsidian: create a folder on your desktop called `unlocked/domains/[domain-name]/`. Copy the files from `templates/` into it. Plain markdown works fine.

### Step 5: Run Session 1

Open your session notes file. Use the [session-notes template](templates/session-notes.md).

**Opening question:**
> "Walk me through a day in your work — not the ideal version, the actual one."

After the session: paste your notes into Claude.ai with the [Synthesis Bot prompt](chatbot-prompts/synthesis-bot.md). Save the output.

### Step 6: Run Sessions 2–4, synthesize after each

After Session 4: run the [GTM Bot](chatbot-prompts/gtm-bot.md) with your problem map. You'll have an output track recommendation and a first-move hypothesis.

**That's it.** You've completed a DIF engagement.

---

## Path B: Technical (Full Stack, 15 min setup)

Claude Code + MCP + Claude skills. Fully automated synthesis pipeline.

### Step 1: Set up the MCP stack (10 min)

Follow [mcp-setup/README.md](mcp-setup/README.md). At minimum, you need:
- `knowledge-vault` (filesystem MCP) pointing to your vault directory
- `research` (brave-search MCP) for enrichment — requires a Brave API key (free tier: 2,000 queries/month)

Drop the config into `~/.claude/` or `~/Library/Application Support/Claude/` depending on your OS.

### Step 2: Install Claude skills (2 min)

Skills live in `.claude/commands/`. If you've opened this repo in Claude Code, they're already active. Test:

```
/synthesize-session
```

Claude should respond with an explanation of the skill. If not, check that you're running Claude Code from this repo's root directory.

### Step 3: Update the context file (2 min)

Open `.claude/CLAUDE.md` and fill in the "Current Engagement" section:

```
Domain: [DOMAIN]
SME name/role: [NAME / ROLE]
Sessions completed: 0
Current phase: Listen
Priority opportunity: TBD
```

### Step 4: Run pre-engagement research

```
/generate-pre-brief
```

Claude will prompt you for the domain and run the research stack. Output: `templates/pre-brief.md` — review and edit before sending to the SME.

### Step 5: Run your first session

Open `templates/session-notes.md` and create a copy at `sessions/session-01.md`.

**After the session:**
```
/synthesize-session
```

Claude reads your notes and writes `sessions/session-01-synthesis.md`. The synthesis is your brief for Session 2.

### Step 6: Run the full sequence after Session 4

```
/extract-problems
/map-pillars
/generate-sop
/enrich-domain
/gtm-canvas
/classify-output-track
```

Each skill reads the previous outputs. By the end, you have:
- A classified problem map
- A knowledge pillar taxonomy
- A first-draft SOP
- Market-validated insights
- A GTM canvas with a defined first move
- An output track recommendation

Total time from first session to GTM canvas: 2–3 weeks (including scheduling).

---

## After Both Paths: The Output Track Decision

After Session 4 (or `/classify-output-track`), you'll have a recommended output track:

| Track | What It Is | Timeline |
|-------|-----------|----------|
| Micro-Tool | AI-powered tool for one high-frequency problem | 2–4 weeks |
| Productized Service | Fixed-scope, repeatable service (like the 0→1 Sprint) | Immediate |
| Course / SOP Pack | Expert knowledge packaged for others | 2–3 weeks |
| Intelligence Report | Insight Brief + market context | 3–5 days |
| Funded Startup | Full company — co-found, raise, build | 12–24 months |

See [VENTURE-TRACKS.md](VENTURE-TRACKS.md) for the full breakdown.

---

## Questions?

- Full methodology: [METHODOLOGY.md](METHODOLOGY.md)
- MCP setup: [mcp-setup/README.md](mcp-setup/README.md)
- Claude skills: [claude-skills/README.md](claude-skills/README.md)
- Chatbot prompts: [chatbot-prompts/README.md](chatbot-prompts/README.md)
- Case study (healthcare): [case-studies/healthcare/](case-studies/healthcare/)
- Partnership model: [PARTNERSHIP.md](PARTNERSHIP.md)
- Value ladder: [VALUE-LADDER.md](VALUE-LADDER.md)
