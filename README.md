# Repolex Knowledge Graph of tox-dev/tox-report

RDF knowledge graph data for [tox-dev/tox-report](https://github.com/tox-dev/tox-report), parsed by [repolex](https://repolex.ai).

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
rlex download tox-dev/tox-report
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 344d0f299c4a615db3e7ca33dc7ce421e4fe7a1a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 344d0f299c4a615db3e7ca33dc7ce421e4fe7a1a
│           └── chunk-001.nq.gz
├── blob
│   ├── 1d943c2bd206684dc804ff8fdf660c77cfd38f05.nq.gz
│   ├── 200c30d3fe5d5142693fe27f7f9bc817c4265b47.nq.gz
│   ├── 24f7577b2b98f3d6de3923f12abace8c206e9657.nq.gz
│   ├── 354fb450141422d6c3d9dcc9bb55c82ae4d70e66.nq.gz
│   ├── 3da4a7226a1cf78fe3e0aca1094a921ea311ebe9.nq.gz
│   ├── 3eb4735c836fa75d1f9ef896e4dfe82529342b77.nq.gz
│   ├── 5b21283ab7694937d0ef78e0721a1a149e006f58.nq.gz
│   ├── 69cb76019a474330e99666f147ecb85e44de1ce6.nq.gz
│   ├── 71a74225783d13a478e522fb194671f19d2d176b.nq.gz
│   ├── 7232cf796bf58299229a7ba616ac4a7f60fe0cd2.nq.gz
│   ├── a203ea820c0d822b3fab67597c1810ec1b250906.nq.gz
│   ├── a444debdfcf6f65fc44e4e18bbb10573e61aa5cb.nq.gz
│   ├── ac0c4d2174d56715379ee51fda619b885b23b175.nq.gz
│   ├── be695ae7dd07a1681beebaa2b0ddb7323ebc03ac.nq.gz
│   ├── c40553b8a665de77b60b98737ba7c1477e9f26b2.nq.gz
│   ├── c60aaab37aa0a29c71da05bb38c8a3a30744e5ff.nq.gz
│   ├── e2a0e460589b5ac8e25c2960719d09ee9bc5ea73.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eb06e34829e889ba887615d7ef70d98443e591cc.nq.gz
│   └── f58dd6b3d988e5b18a1d0e383b40775f1b954423.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 344d0f299c4a615db3e7ca33dc7ce421e4fe7a1a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[tox-dev/tox-report](https://github.com/tox-dev/tox-report)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
