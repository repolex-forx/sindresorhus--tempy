# Repolex Knowledge Graph of sindresorhus/tempy

RDF knowledge graph data for [sindresorhus/tempy](https://github.com/sindresorhus/tempy), parsed by [repolex](https://repolex.ai).

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
rlex download sindresorhus/tempy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6c0f2ccdfabc37ce002d8c073457bc447c089d20
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 6c0f2ccdfabc37ce002d8c073457bc447c089d20.nq.gz
│   └── repolex
│       └── 6c0f2ccdfabc37ce002d8c073457bc447c089d20
│           └── chunk-001.nq.gz
├── blob
│   ├── 1c6314a31833395fd5ff016a6506bdd51860657c.nq.gz
│   ├── 239ecff1372358a22aa99dcbb375fdad7abba817.nq.gz
│   ├── 3c3eb6132c753fa179875ddfcfef9e8d1f0e62d5.nq.gz
│   ├── 3fc6ceca55d7da80faa2f15633ec55a9f6fd2d18.nq.gz
│   ├── 41094bd6a1dc71cf3df49f08a84452c7568d4abd.nq.gz
│   ├── 43c97e719a5a824700932f72e6e7e6748ce45d01.nq.gz
│   ├── 4ed73739abd8c4a924fe5ed7c87a79bb66ef47d6.nq.gz
│   ├── 5358dc50b2883157fca0fa4a12d2bb18acb093ee.nq.gz
│   ├── 6313b56c57848efce05faa7aa7e901ccfc2886ea.nq.gz
│   ├── ce4645fd83d56a441c409e5e8add451220c0f457.nq.gz
│   ├── ebc02ecd0a796f56d366d843fad3891b2cf90f5e.nq.gz
│   └── fa7ceba3eb4a9657a9db7f3ffca4e4e97a9019de.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 6c0f2ccdfabc37ce002d8c073457bc447c089d20.nq.gz
├── filetree
│   └── 6c0f2ccdfabc37ce002d8c073457bc447c089d20.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 22 files
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

[sindresorhus/tempy](https://github.com/sindresorhus/tempy)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
