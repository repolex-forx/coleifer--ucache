# Repolex Knowledge Graph of coleifer/ucache

RDF knowledge graph data for [coleifer/ucache](https://github.com/coleifer/ucache), parsed by [repolex](https://repolex.ai).

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
rlex download coleifer/ucache
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 19a87f84a49597cd03191aa2e56abd62ee8831de
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 19a87f84a49597cd03191aa2e56abd62ee8831de
│           └── chunk-001.nq.gz
├── blob
│   ├── 1189a5cf3f73bfa7778963cd581447490f934c28.nq.gz
│   ├── 31d51d3ae4e5ce407c87671a6f01720258f053fd.nq.gz
│   ├── 4770af518c0cbbcef3c4f63d64c0c43f6c19742d.nq.gz
│   ├── 591a6b88d654bed1dc62643a3de3054b46f492cc.nq.gz
│   ├── 5f381be62b117bb6b9a9ef53cbbb9c6b0e8fbb5d.nq.gz
│   ├── 961b383ac95c70c0154a7dd2bd12c4975ac47735.nq.gz
│   ├── 9869b332fee04ab1ddd3ac2c8661f8cf8c955c26.nq.gz
│   ├── c752ab3ead2e7be324e5cafb5e1d53135c16af13.nq.gz
│   └── cf08dc60f8c139ec5d5bbf890587c23058d91db8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 19a87f84a49597cd03191aa2e56abd62ee8831de.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
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

[coleifer/ucache](https://github.com/coleifer/ucache)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
