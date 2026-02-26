# Quickstart — Run Your First Session in 30 Minutes

This guide gets you operational. Read [METHODOLOGY.md](METHODOLOGY.md) when you want to go deep.

---

## Before the First Session

### 1. Set up the MCP stack (15 min)

Follow [mcp-setup/README.md](mcp-setup/README.md). At minimum, you need the filesystem MCP pointing to this repo. The Brave Search MCP is required for Phase 4 (enrichment) but not for Sessions 1–3.

### 2. Install Claude skills (2 min)

Skills are already in `.claude/commands/`. If you're in Claude Code and have opened this repo, they're live. Test it:

```
/synthesize-session
```

Claude should respond with a brief explanation of the skill. If it doesn't, check that you're running Claude Code from this directory.

### 3. Update the context file (2 min)

Open `.claude/CLAUDE.md` and fill in the "Current Engagement" section:
- Domain
- SME name/role
- Sessions completed: 0
- Current phase: Listen

---

## Running Session 1

**Objective:** Build a mental map of the domain. Don't ask about problems yet.

**Before the session:** Open `templates/session-notes.md` and create a copy at `sessions/session-01.md`.

**Opening question:**
> "Walk me through a day in your work — not the ideal version, the actual one."

**Your job during the session:**
- Take notes in `sessions/session-01.md`
- Use **bold** for high-energy moments
- Capture vocabulary exactly as the SME uses it
- Don't redirect — follow their energy

**After the session (5 min):**
```
/synthesize-session
```

Claude will read your notes and produce `sessions/session-01-synthesis.md`. Review it. Correct anything that feels off. The synthesis is your brief for Session 2.

---

## After 4 Sessions

Run the full skill sequence:

```
/extract-problems
/map-pillars
/enrich-domain
/gtm-canvas
```

Each skill reads the previous outputs. By the end, you have:
- A classified problem map
- A knowledge pillar taxonomy
- Market-validated insights
- A GTM canvas with a defined first move

Total time from first session to GTM canvas: 2–3 weeks (including scheduling).

---

## Questions?

The methodology is in [METHODOLOGY.md](METHODOLOGY.md). The MCP setup is in [mcp-setup/README.md](mcp-setup/README.md). The case study shows what the output looks like in practice: [case-studies/healthcare/](case-studies/healthcare/).
