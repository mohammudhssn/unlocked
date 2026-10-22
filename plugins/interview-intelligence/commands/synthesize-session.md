---
description: Extract themes, problems, vocabulary and threads from raw interview notes
---

# Synthesize Session

You are running the **Session Synthesizer** for the Domain Intelligence Framework.

## Context

You have access to the knowledge vault via the filesystem MCP. Before synthesizing, read:
1. All previous session syntheses in `/sessions/`
2. The current problem map at `/outputs/problem-map.md` (if it exists)
3. The latest raw session notes — the most recently modified file in `/sessions/`

## Instructions

Synthesize the latest session notes into the following structured output:

### 1. Session Summary (2–3 sentences)
What was the primary focus of this session? What shifted or surprised you compared to previous sessions?

### 2. Key Themes (3–5 bullet points)
The major topics, patterns, or ideas that emerged. Use the expert's own language where possible.

### 3. Problems Surfaced (raw list)
Every friction point, complaint, workaround, or gap mentioned — even offhand. Don't classify yet. Just capture them verbatim or close to it.

### 4. Vocabulary Glossary (additions only)
New domain-specific terms, acronyms, or phrases the expert used that weren't in previous sessions. Include a plain-language definition.

### 5. Threads to Pull (top 3)
The most promising threads that deserve dedicated time in the next session. For each:
- **Thread:** [Topic]
- **Why it matters:** [What it might unlock]
- **Opening question:** [How to reopen it naturally]

### 6. Energy Map
Note the moments in this session where the expert's energy changed — where they got more animated, more frustrated, or more resigned. These emotional signals are often the most reliable indicators of real pain.

## Output

Write the synthesis to `/sessions/session-0[N]-synthesis.md` where N is the session number.

If a problem map already exists, flag any new problems that should be added. Do not modify the problem map directly — that's the job of `/extract-problems`.
