# Repolex Knowledge Graph of google-deepmind/scalable_agent

RDF knowledge graph data for [google-deepmind/scalable_agent](https://github.com/google-deepmind/scalable_agent), parsed by [repolex](https://repolex.ai).

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
rlex download google-deepmind/scalable_agent
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6c0c8a701990fab9053fb338ede9c915c18fa2b1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6c0c8a701990fab9053fb338ede9c915c18fa2b1
│           └── chunk-001.nq.gz
├── blob
│   ├── 07a3af2009dbd1d29ad9bae91ebb11df7dc25f8f.nq.gz
│   ├── 07fac94878779c2a50a0581378778f3e67375d8c.nq.gz
│   ├── 3db781f0ced54d1ddf1f7a499d98f7ea3619bfe7.nq.gz
│   ├── 496a78d69ac43a90b75eaffd4e7f3d0049fc7638.nq.gz
│   ├── 5233c442c3f2790b651b080887e72283856a4a9b.nq.gz
│   ├── 53c370f0f8291553a6e4ab876c0e9c0932a7cea4.nq.gz
│   ├── 5691a93a30c9c4f377f5a82e79b16fc75ced27a1.nq.gz
│   ├── 7a4a3ea2424c09fbe48d455aed1eaa94d9124835.nq.gz
│   ├── 9e85c0ac0300b781fd8eff59881740610d9f5b44.nq.gz
│   ├── bb70059a4fcfe0f0f760725287d27008f54e98f1.nq.gz
│   ├── df56203af52e048ee49af9294d246bd69aa1bbb7.nq.gz
│   ├── f17df7ad4b5c6a020981430690c2da5c4bca6edc.nq.gz
│   ├── f264e643259f7269eb711171e7df8dff73e8b3ef.nq.gz
│   └── f2a9f773de5261b22cc4f33ddcb283e3b33a297d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6c0c8a701990fab9053fb338ede9c915c18fa2b1.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 22 files
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

[google-deepmind/scalable_agent](https://github.com/google-deepmind/scalable_agent)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
