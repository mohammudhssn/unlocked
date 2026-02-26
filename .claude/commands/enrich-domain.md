# Enrich Domain

You are running the **Research Enricher** for the Domain Intelligence Framework.

## Context

This skill requires the **Brave Search MCP** to be active. Confirm it's available before proceeding.

Read the current knowledge vault:
- Problem map at `/outputs/problem-map.md`
- Knowledge pillars at `/outputs/knowledge-pillars.md`

You are not starting from scratch — you are validating and extending what the SME already told us. The internal insight is the anchor. External research is the calibration layer.

## Instructions

### Step 1: Generate search queries
For each Priority Opportunity in the problem map, generate 3–5 targeted search queries:
- One for market size / TAM
- One for existing competitors or adjacent solutions
- One for recent news or regulatory context
- One for research papers or industry reports
- One for communities or watering holes where this problem is discussed

### Step 2: Execute searches via Brave Search MCP
Run the searches. Capture the most relevant results — don't try to read everything, focus on signals.

### Step 3: Cross-reference against internal insights
For each finding, classify:

| Signal | Internal Match | Assessment |
|---|---|---|
| [Finding] | Confirms / Diverges / Adds | [What it means] |

- **Confirms:** Internal and external signals agree. Confidence goes up.
- **Diverges:** They disagree. Don't dismiss either — understand why. The SME may know something the market doesn't yet. Or the market may have moved and the SME's mental model is behind.
- **Adds:** External research surfaces something not covered in sessions. Add it to the problem map as a new signal (flagged as "research-sourced, not SME-confirmed").

### Step 4: Build the external context layer

For each Priority Opportunity, add:
- **Market size:** Best available estimate (with source and confidence level)
- **Competitor landscape:** Who's trying to solve this? How? What's the gap?
- **Timing signals:** Why is now the right moment? (Regulatory shifts, technology unlocks, market events)
- **Adjacent proof points:** Other markets where similar solutions have worked

### Step 5: Update the insight brief
Integrate the external context into `/outputs/insight-brief.md`. The brief should now answer:
- "Is this a real problem?" (from SME sessions)
- "Is this a real market?" (from research enrichment)
- "Is this the right time?" (from timing signals)

## Output

1. Update `/outputs/insight-brief.md` with the enriched external context layer
2. Append a "Research Sources" section with all sources consulted
3. Flag the top 3 unanswered questions that would require primary research (customer calls, surveys) to resolve
