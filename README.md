# Repolex Knowledge Graph of mattn/go-isatty

RDF knowledge graph data for [mattn/go-isatty](https://github.com/mattn/go-isatty), parsed by [repolex](https://repolex.ai).

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
lexq download mattn/go-isatty
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4237fb15069af3284b50e5d91bcdd5403e584605
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 4237fb15069af3284b50e5d91bcdd5403e584605.nq.gz
│   └── repolex
│       └── 4237fb15069af3284b50e5d91bcdd5403e584605
│           └── chunk-001.nq.gz
├── blob
│   ├── 012162b077c97e96bcb25c4be1a0716a29a35fd6.nq.gz
│   ├── 0337d8cf6dea79e947b8dad03414a63d685bd1f8.nq.gz
│   ├── 0c3acf2dc288ab543e374e72a402003c027ce98f.nq.gz
│   ├── 17d4f90ebcc7ee53452303f1c86d41eca5e13fc5.nq.gz
│   ├── 351ae11a875b1ac5c17b74b247b8a7c3c4716796.nq.gz
│   ├── 38418353e31c8aafc3d22332f5d58a01f5f30246.nq.gz
│   ├── 41edab0766ac2170eda3d191e927775fa5f89733.nq.gz
│   ├── 5ea708f2d7d8bd6745f670faddb6e16182221cc7.nq.gz
│   ├── 65dc692b6b171e95c7e7698674ebaf8524dcd0d6.nq.gz
│   ├── b24a2fadc9cae52f5e0c8d66deacdd0124ca297f.nq.gz
│   ├── bae7f9bb3dc5fe622e13a055e02f3bb136127de6.nq.gz
│   ├── bc1eec1f07ad39c001327d7a102313165640017a.nq.gz
│   ├── c0c8ce8c05de24a03f5e1817499eba72fa39e8c2.nq.gz
│   ├── d0ea68f4082fb7ec5a04baf64e4ec3313120060e.nq.gz
│   ├── e7c8d90053970d64713cc53ae2485d49fd8473f1.nq.gz
│   ├── ec525b0438ab5e083035861da45e656dce51e90c.nq.gz
│   └── fa8f7e7455e2e09c17a30dff9480abfdb6252ba9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4237fb15069af3284b50e5d91bcdd5403e584605.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 26 files
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

[mattn/go-isatty](https://github.com/mattn/go-isatty)

---
*Parsed on 2026-09-16 by [repolex](https://repolex.ai)*
