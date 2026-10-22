# interview-intelligence

Turn expert interviews into something you can build on. Eight Claude Code commands that run the Unlocked method: interview, synthesize, classify, structure, enrich, decide.

## Install

```
/plugin marketplace add mohammudhssn/unlocked
/plugin install interview-intelligence@unlocked
```

## Commands

| Command | When | What it does |
|---|---|---|
| `/generate-pre-brief` | Before session 1 | Researches the domain and writes a pre-brief to share with the expert |
| `/synthesize-session` | After every session | Themes, problems, vocabulary and threads from raw notes |
| `/extract-problems` | After session 2 | Classifies problems by urgency, frequency, solvability and market |
| `/map-pillars` | After session 3 | Builds a knowledge taxonomy |
| `/generate-sop` | After session 3 | First-draft SOP from the pillars |
| `/enrich-domain` | After session 4 | Checks insights against live market data (needs a search MCP) |
| `/gtm-canvas` | After enrichment | ICP, positioning, channels, pricing |
| `/classify-output-track` | After the problem map | Micro-tool, service, course, report or startup |

## Vault layout

The commands read and write a simple folder structure in your project:

```
sessions/   raw notes and transcripts, one file per session
outputs/    problem-map.md, knowledge-pillars.md, sop-draft.md, insight-brief.md, gtm-canvas.md
```

Drop a transcript (Fathom, Granola, Otter) into `sessions/` and run `/synthesize-session`.

## Want it done for you?

I run these interviews and builds for experts and teams: [mohammud.com](https://mohammud.com).
