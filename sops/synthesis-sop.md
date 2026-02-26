# Synthesis SOP

> Post-session processing. Run this within 24 hours of every session.

**Version:** 1.0
**Time:** 15–30 minutes per session
**Output:** Structured session synthesis, updated problem map, vocabulary glossary, follow-up queue
**Bot:** [Synthesis Bot](../chatbot-prompts/synthesis-bot.md) handles the heavy lifting

---

## Why Synthesize Immediately After Each Session

Session memory degrades fast. Within 24 hours, the offhand comment that turned out to be the most important thing the expert said will feel less significant than it did in the room. The Synthesis Bot processes it before your memory reweights it.

The synthesis also feeds the next session. The Follow-Up Queue becomes the opening of Session N+1. The longer you wait, the more you're starting cold.

---

## The Synthesis Flow

### Immediately After the Session (5 minutes)

Before closing your notes:

1. **Star the top 3 moments** — the places where the expert's energy shifted, or you felt something significant was being said. These are what you don't want the bot to miss.

2. **Add a "Post-session gut note"** at the bottom of your notes:
   ```
   ## Post-session gut note
   *Written immediately after — before reviewing notes.*
   The most important thing from this session was: [sentence]
   The thing I almost missed: [sentence]
   The question I wish I'd asked: [sentence]
   ```

3. **Save your notes** to `/sessions/session-0N.md`

### Running the Synthesis (10–15 minutes)

Open the [Synthesis Bot](../chatbot-prompts/synthesis-bot.md) — paste the system prompt into a new Claude conversation or use `/synthesize-session` in Claude Code.

**Input:** Paste your full session notes (or transcript if you recorded)

**Output:** Claude produces:
- Problem list (tagged by type, with signal quotes)
- Tacit knowledge signals
- Latent demand flags
- Contradictions to explore
- Vocabulary additions
- Follow-Up Queue (3 questions for the next session)

**Time:** 2–5 minutes for Claude to process.

### Reviewing the Synthesis (10 minutes)

Don't accept the synthesis as-is. Review critically:

**Checklist:**
- [ ] Does the problem list include everything you noted? Add anything missing.
- [ ] Are the tags accurate? URGENT vs. IMPORTANT vs. LATENT? Correct if off.
- [ ] Are the tacit signals capturing the actual nuance, or just the surface? Clarify if shallow.
- [ ] Does the Follow-Up Queue reflect the threads YOU most want to pull? Reorder if needed.
- [ ] Is the vocabulary correct? Does the definition match how the expert actually used the term?

**Save to:** `/sessions/session-0N-synthesis.md`

---

## Updating the Problem Map

After Sessions 2–4, each synthesis feeds the consolidated Problem Map. Run:

```
/extract-problems
```

Claude reads all session syntheses and produces an updated, ranked problem map at `/outputs/problem-map.md`.

**After each update, review the problem map and ask:**
- Are there problems appearing in multiple sessions? Flag as high-confidence.
- Are there problems that seemed important in session 1 but haven't come up since? Deprioritize.
- Is the top-ranked URGENT problem the right one to build toward? Trust the data, not your initial hypothesis.

---

## The Cross-Domain Check

After each synthesis, scan the problems for patterns that appear in other domains you've studied.

Open `/patterns/cross-domain-repeaters.md` and ask:
> "Have I seen a version of this problem in another domain?"

If yes, add a note to both files. Cross-domain patterns are the moat.

Common cross-domain patterns to watch for:
- **The handoff gap:** Problems that occur at transitions between roles, shifts, or systems (healthcare, legal, construction, finance — all have this)
- **Decision debt:** Decisions deferred under time pressure that compound into larger problems later
- **The tacit expertise bottleneck:** Knowledge that lives in one person's head and fails to transfer
- **The documentation lag:** Events that need to be recorded but aren't — creating information asymmetry

---

## After Session 4: Full Synthesis Run

Once Sessions 1–4 are complete, run the complete skill sequence:

```
/extract-problems      → consolidated problem map
/map-pillars           → full knowledge pillar taxonomy
/generate-sop          → first-draft SOP from pillar taxonomy
/enrich-domain         → external market research layer (requires Search MCP)
/gtm-canvas            → GTM canvas draft
/classify-output-track → output track recommendation
```

**Time:** 30–60 minutes, mostly automated. Review each output in order — each one feeds the next.

The full synthesis is what you bring to Sessions 5–6. The SME reacts to it. Their reactions complete the picture.

---

## The Quality Signal

A good synthesis has these properties:

1. **Specificity:** Problems are one-sentence, discrete, not collapsed into categories
2. **Groundedness:** Every item traces to a specific moment in the session
3. **Tacit capture:** At least one tacit knowledge signal per session (if there isn't one, you missed it — go back and look)
4. **Energy-fidelity:** The synthesis prioritizes the moments the expert got animated, not the moments they spoke most fluently
5. **Latent visibility:** At least one latent demand flag — something framed as "just how it is" that is actually an opportunity

If the synthesis doesn't have all five, it's incomplete. Don't move to the next session without it.
