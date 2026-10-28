# Repolex Knowledge Graph of Kozea/pygal_maps_world

RDF knowledge graph data for [Kozea/pygal_maps_world](https://github.com/Kozea/pygal_maps_world), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download Kozea/pygal_maps_world
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0658e44fbc5124c2f3a86b75422c69b715b0a516
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0658e44fbc5124c2f3a86b75422c69b715b0a516
│           └── chunk-001.nq.gz
├── blob
│   ├── 31d0c39765866b440e852f4845bd0fef8408513b.nq.gz
│   ├── 5b89ba40334f381d69eec61c30d94ff3294eff33.nq.gz
│   ├── b024ce1c2e209545e640873736bc3c16df9ddca3.nq.gz
│   ├── baf6ad6537e90a39ee69eb3419a2eac1f6761893.nq.gz
│   ├── d6a49eab11952d871180c15a3c96a80626fd658f.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0658e44fbc5124c2f3a86b75422c69b715b0a516.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 14 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[Kozea/pygal_maps_world](https://github.com/Kozea/pygal_maps_world)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
