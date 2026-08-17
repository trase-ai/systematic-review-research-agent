# Systematic Review Research Agent

## Rationale

Systematic literature reviews (SLRs) are the backbone of rigorous social science research, yet they demand painstaking manual effort: searching dozens of databases, classifying heterogeneous sources, assessing credibility, and synthesizing findings into actionable themes. This agent automates that pipeline while preserving academic integrity. It follows PRISMA-aligned practices, prioritizes exhaustive breadth-first collection before quality filtering, and produces a tagged, analysis-ready CSV so researchers can move from raw sources to thematic synthesis in minutes rather than weeks.

---

## Summary

A graduate-level social science agent that conducts systematic literature reviews following PRISMA guidelines. Given a research topic, it exhaustively searches academic databases, government sources, grey literature, and preprint servers; verifies and scores every source for reliability; identifies recurring themes; and outputs a tagged, pipe-separated CSV ready for import into Excel or pandas.

---

## Workflow

1. **Source Collection** — Exhaustive search across academic databases, government/intergovernmental bodies, reputable news, grey literature, and preprint servers.
2. **Verification & Accuracy Scoring** — Every source is classified by publication type and assigned a 1–10 reliability score with justification.
3. **Thematic Synthesis** — Recurring themes are identified across all sources and each source is tagged with relevant themes.
4. **CSV Output** — Produces a tagged, pipe-separated CSV with columns: `title`, `authors`, `year`, `url`, `publication_type`, `journal_or_outlet`, `reliability_score`, `reliability_notes`, `themes`.

## Configuration

| Setting | Value |
|---------|-------|
| Provider | Anaconda Desktop |
| Model | `gemma-4-E4B-it-Q4_K_M.gguf` |
| Temperature | 0.7 |
| Web Search | DuckDuckGo MCP |

## Usage

```bash
pixi run serve
```

## Files

| File | Role |
|------|------|
| `agent.yaml` | Core agent definition, system prompt, and workflow |
| `manifest.json` | Studio metadata and versioning |
| `pixi.toml` | Python workspace and dependency config |
| `tools/mcp.json` | MCP tool bindings (web search) |
| `.plugins.json` | Plugin manifest |

## Requirements

- Python >= 3.11
- Anaconda Agent Runtime
- DuckDuckGo MCP Server
