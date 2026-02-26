# Chatbot Prompts

> Zero setup. Paste a system prompt into any Claude interface and run.

These three bots are standalone. They don't require MCP servers, Claude Code, or any technical setup. Open Claude.ai, paste the system prompt, and the bot runs.

Each one handles a specific phase of the DIF engagement — and together, they make it possible to run a significant portion of the process without live expert sessions.

---

## The Three Bots

### 1. Discovery Bot
**When:** Before Session 1
**What it does:** Runs a structured 20–30 minute domain scan with the expert. Surface-level questions are handled by the bot, so your live session starts deeper.

→ [discovery-bot.md](discovery-bot.md)

**How to run it:**
1. Copy the system prompt from `discovery-bot.md`
2. Open a new Claude conversation
3. Paste the system prompt + fill in `[DOMAIN]` and `[PRE-BRIEF]`
4. Share the conversation link with your SME
5. They work through it async, you review before Session 1

**Expected output:** A structured summary of the expert's domain context, 3–5 surface-level problems identified, vocabulary glossary, and a thread list for your first live session.

---

### 2. Synthesis Bot
**When:** After each live session (1–4)
**What it does:** Reads session notes or a transcript, extracts themes, flags contradictions, classifies problems by type, and generates the follow-up queue for the next session.

→ [synthesis-bot.md](synthesis-bot.md)

**How to run it:**
1. Copy the system prompt from `synthesis-bot.md`
2. Open a new Claude conversation
3. Paste the system prompt
4. Paste your session notes or transcript
5. Claude produces the synthesis in 2–5 minutes

**Expected output:** Problem list (tagged Urgent / Important / Latent), tacit knowledge signals, latent demand flags, contradictions to explore, 3 follow-up questions for the next session.

---

### 3. GTM Bot
**When:** After the Problem Map is built (post-Session 3 or 4)
**What it does:** Tests GTM assumptions, surfaces distribution paths, identifies ICP from the expert's own network, and generates the first-move hypothesis.

→ [gtm-bot.md](gtm-bot.md)

**How to run it:**
1. Copy the system prompt from `gtm-bot.md`
2. Open a new Claude conversation
3. Paste the system prompt + your Problem Map
4. Run it with the expert present (Session 5 or 6) or solo first

**Expected output:** ICP definition, 3 positioning angles, channel hypotheses, pricing hypotheses, top 3 risk assumptions, first-move recommendation.

---

## How the Bots Connect

```
SME completes Discovery Bot (async, before Session 1)
          ↓
Live Sessions 1–4 (you run these — deeper, faster because of Discovery Bot pre-load)
          ↓
After each session → Synthesis Bot processes notes (5 min, async)
          ↓
After Session 3–4 → Problem Map is built
          ↓
GTM Bot tests assumptions (Session 5–6, or async with SME)
          ↓
GTM Canvas produced → Venture track decision
```

The bots don't replace the live sessions. They make the live sessions count more — no time wasted on surface-level questions, no manual note-taking, no losing threads between sessions.

---

## Plugging Into Your Existing Setup

**If you use Claude.ai:** Paste the system prompt into a Project. It persists across conversations and remembers your previous work.

**If you use the Claude API:** Use the system prompt as-is in the `system` parameter. The bots are API-ready.

**If you use Claude Code:** Drop the prompts into `.claude/commands/` as custom skills. They become slash commands you can invoke mid-session.

**If you use Obsidian + MCP:** The bot outputs feed directly into the vault structure. Copy the JSON output from the Discovery Bot into `/domains/[domain]/pre-session.md`. The Synthesis Bot outputs go into `/sessions/session-0N-synthesis.md`.

All four integration paths work. Use what you already have.
