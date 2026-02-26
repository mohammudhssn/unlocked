# MCP Setup

The Domain Intelligence Framework uses a stack of Model Context Protocol (MCP) servers to give Claude persistent access to the knowledge vault, live market research, and version-controlled session data.

This makes the framework **stateful** — Claude isn't starting fresh each session. It reads existing pillars, problems, and session history before generating new output.

---

## The MCP Stack

| Server | Purpose | Install |
|---|---|---|
| `server-filesystem` | Read/write the knowledge vault (session notes, pillars, outputs) | Built-in |
| `server-brave-search` | Live market research, competitor lookup, research papers | Requires Brave API key |
| `server-github` | Version control for the knowledge base | Requires GitHub token |
| `domain-intelligence` | Custom MCP — serves the full knowledge graph to any Claude session | See below |

---

## Configuration

Add this to your `claude_desktop_config.json` (usually at `~/Library/Application Support/Claude/claude_desktop_config.json` on macOS):

```json
{
  "mcpServers": {
    "knowledge-vault": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/path/to/your/domain-intelligence-framework"
      ]
    },
    "research": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-brave-search"
      ],
      "env": {
        "BRAVE_API_KEY": "your-brave-api-key"
      }
    },
    "github": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-github"
      ],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "your-github-token"
      }
    }
  }
}
```

Replace `/path/to/your/domain-intelligence-framework` with your actual local path.

---

## The Custom `domain-intelligence` MCP

The standard filesystem MCP gives Claude raw file access. The custom MCP goes further — it serves the knowledge graph as a **structured, queryable context layer**.

When attached, any Claude session can:
- Ask "what problems did we identify in this domain?" and get a structured answer
- Request the full knowledge pillar taxonomy
- Pull the prioritized opportunity map
- Access the SME's vocabulary for content and positioning work

### Why this matters for business creation

Once a domain engagement is complete, the MCP becomes a persistent co-founder memory. Any downstream work — product scoping, investor pitch, content marketing, hiring briefs — can be done with Claude loaded with the full domain context, without re-running a single interview.

The knowledge vault becomes an **organizational brain** that compounds over time.

### Setup (in progress)

The custom MCP server is currently built as a local Node.js server. See [`domain-intelligence-mcp/`](../domain-intelligence-mcp/) for the source (coming soon).

It exposes the following tools to Claude:

| Tool | Description |
|---|---|
| `get_problem_map` | Returns all identified problems, classified by type and priority |
| `get_knowledge_pillars` | Returns the full pillar taxonomy with SME edge notes |
| `get_gtm_canvas` | Returns the current GTM hypotheses |
| `get_session_history` | Returns a summary of all sessions run to date |
| `query_domain` | Semantic search across all session notes and outputs |

---

## Session Workflow with MCPs Active

```
Before session:
  Claude reads existing vault via filesystem MCP
  → knows what's been covered, what threads to pull

During session (note-taking):
  Session notes saved to /sessions/session-0N.md

After session:
  /synthesize-session skill triggers
  → Claude reads new notes via filesystem MCP
  → writes structured outputs back to vault
  → commits to GitHub via github MCP

For research enrichment:
  /enrich-domain skill triggers
  → Claude queries brave-search MCP with specific research prompts
  → cross-references results against internal problem map
  → writes enriched insight brief to vault
```

---

## Getting a Brave Search API Key

1. Go to [brave.com/search/api](https://brave.com/search/api/)
2. Sign up for a free account (2,000 queries/month free)
3. Copy your API key into the config above
