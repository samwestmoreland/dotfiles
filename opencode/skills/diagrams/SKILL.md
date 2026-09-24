---
name: diagrams
description: Generate diagrams when the user asks to draw, diagram, or visualise something.
---

# Diagrams

## HARD RULE: SINGLE-LINE LABELS ONLY - NO EXCEPTIONS

**Never use `<br>`, `<br/>`, `\n`, or any other line-break attempt in node or edge labels.**
Both render as literal characters in the ASCII output, not line breaks. There is no
multi-line label syntax that works in this renderer. If a label is too long: shorten
it, use abbreviations, or split the content across two separate nodes.

## Workflow

1. Generate valid Mermaid syntax for the requested diagram
2. Output it in a fenced code block (` ```mermaid `)

## Diagram type selection

| Use case | Mermaid type |
|---|---|
| Step-by-step flows, DNS/auth/request paths | `flowchart LR` |
| Decision trees, branching logic | `flowchart TD` |
| Component/infrastructure overview | `flowchart LR` with subgraphs for zones |
| State machines | `stateDiagram-v2` |
| Entity relationships | `erDiagram` |
| Wide diagrams that need narrowing | `flowchart TD` (rotate to vertical) |

## Controlling diagram width

Wide `flowchart LR` diagrams often exceed terminal width and wrap badly.
Two tools to fix this:

### 1. Switch direction to TD (top-down)

`flowchart TD` stacks nodes vertically. Use when the flow is naturally sequential
and you want a narrow tall diagram instead of a wide flat one. Note: there is a known
bug (lukilabs/beautiful-mermaid#83) where TD/TB can silently flip to horizontal on
some graph shapes - if it happens, simplify the graph structure.

### 2. Shorten labels aggressively

Every character counts. Drop articles, use abbreviations (`GCP NLB` not
`Google Cloud internal passthrough Network Load Balancer`), omit obvious context.

## Tips for clean layout

- Keep node labels short and single-line - no `\n`, no `<br/>`, no HTML
- Use subgraphs to group components by cloud/zone (`subgraph GCP` / `subgraph AWS`)
- Avoid back-arrows (cycles) in flowcharts - terminate at the final result instead
- Use `%%` comments to label distinct sections or paths
- Edge labels must also be single-line
