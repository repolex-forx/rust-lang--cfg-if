# Repolex Knowledge Graph of rust-lang/cfg-if

RDF knowledge graph data for [rust-lang/cfg-if](https://github.com/rust-lang/cfg-if), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download rust-lang/cfg-if
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3510ca6abea34cbbc702509a4e50ea9709925eda
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 3510ca6abea34cbbc702509a4e50ea9709925eda.nq.gz
│   └── repolex
│       └── 3510ca6abea34cbbc702509a4e50ea9709925eda
│           └── chunk-001.nq.gz
├── blob
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 248e3ccdd9ad6e5487331f3bb39e3db7eb4d9af7.nq.gz
│   ├── 2c7414eb81c1ea4b803b84e87ad890e6cade886a.nq.gz
│   ├── 36e4ff06363a3224304913175080b881f861f60e.nq.gz
│   ├── 39e0ed6602151f235148e6c08413aa7eda5b9038.nq.gz
│   ├── 454e90f0dc891a738e0aa29ca28c1204707dc9eb.nq.gz
│   ├── 55b54ece74c2e9ab1263becc5eef1833315144e2.nq.gz
│   ├── 6a98924eaea247f15cde362682433fe27c305497.nq.gz
│   ├── 7288a62d2535389307ab9b29b2607053bc431433.nq.gz
│   ├── a9d37c560c6ab8d4afbf47eda643e8c42e857716.nq.gz
│   └── d174b6eda69c5da25708c685a3f968002312cddb.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3510ca6abea34cbbc702509a4e50ea9709925eda.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 20 files
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

## Source repository

[rust-lang/cfg-if](https://github.com/rust-lang/cfg-if)

---
*Parsed on 2026-09-07 by [repolex](https://repolex.ai)*
