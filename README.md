# Repolex Knowledge Graph of altair-viz/altair_pandas

RDF knowledge graph data for [altair-viz/altair_pandas](https://github.com/altair-viz/altair_pandas), parsed by [repolex](https://repolex.ai).

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
rlex download altair-viz/altair_pandas
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 506d0b937f1ac047168c88f814c1e3266490a9cc
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 506d0b937f1ac047168c88f814c1e3266490a9cc
│           └── chunk-001.nq.gz
├── blob
│   ├── 059fea414ff156abe30a805e82987ccfb6470f8a.nq.gz
│   ├── 2d7bcce26d02f6a30fd476d3fdd8c7dbf68fc687.nq.gz
│   ├── 5148fe31f1a672fe0541555158917c8256ff125f.nq.gz
│   ├── 5a57e5d06b6ec59091e67744cc8b94dc7303518b.nq.gz
│   ├── 78c686b6c98858a4f1e79491459b0adae7fd9dbe.nq.gz
│   ├── 820df4429d8c9f28d4fd038fc4f6844f6af4a9ec.nq.gz
│   ├── 8f0d6f888628c57c756baecf17deba22902d76cf.nq.gz
│   ├── bad0e33ad1e68a4439d810fcf46f71a450e21407.nq.gz
│   ├── c375abfde5ae32384f401f9624da130f14c71ee4.nq.gz
│   ├── c57bf0d0f4367c79a9a1f89b8fdbe388a2682843.nq.gz
│   ├── cf4b7496129a214bb43009cb904cf0a05cd30853.nq.gz
│   ├── d6f2cc1eb5bc99e21170d3a2769143466f6ddf52.nq.gz
│   ├── e8ea1039ce5d995f0341e29c3db562bea28cd66c.nq.gz
│   ├── e92ab5df68161df80a8f0c466ee6c6e3a3cb1a25.nq.gz
│   ├── ef1e0135c8c76beba3b5f3c0446e6268606554f4.nq.gz
│   ├── f1bf3091f3d839dd257128780da01f20573dd2a6.nq.gz
│   └── ff7ab7326f1274213b3808ebc03c12c17234a8fa.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 506d0b937f1ac047168c88f814c1e3266490a9cc.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[altair-viz/altair_pandas](https://github.com/altair-viz/altair_pandas)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
