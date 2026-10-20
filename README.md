# Repolex Knowledge Graph of simonw/actions-latest

RDF knowledge graph data for [simonw/actions-latest](https://github.com/simonw/actions-latest), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/actions-latest
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8d046f2ec645242db08f4eb33c13ca90495d6101
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8d046f2ec645242db08f4eb33c13ca90495d6101
│           └── chunk-001.nq.gz
├── blob
│   ├── 09a33c6b1085ec88ea2354bac7aa1cf43e6b3b79.nq.gz
│   ├── 1fca263f4888ba9a324a9dfb9c41cfebdfc5623f.nq.gz
│   ├── 3846043fa2abc596bb561bcebca9f20547415e20.nq.gz
│   ├── 8d185a02cbb6e222bc33c8541f9385f736651aca.nq.gz
│   ├── 8ee74e76fcec598c9cd444f63b9676739f2f00c8.nq.gz
│   ├── 8fdb1e0df045069314647a81201c34dcfdb5d9e6.nq.gz
│   └── 91c0a51ba2f83e67b86a4444ae9b370365e99d88.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8d046f2ec645242db08f4eb33c13ca90495d6101.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 15 files
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

[simonw/actions-latest](https://github.com/simonw/actions-latest)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
