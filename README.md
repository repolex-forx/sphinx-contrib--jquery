# Repolex Knowledge Graph of sphinx-contrib/jquery

RDF knowledge graph data for [sphinx-contrib/jquery](https://github.com/sphinx-contrib/jquery), parsed by [repolex](https://repolex.ai).

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
lexq download sphinx-contrib/jquery
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f45993d5657e2afb96e4a730b9033673af7ab0ef
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── f45993d5657e2afb96e4a730b9033673af7ab0ef.nq.gz
│   └── repolex
│       └── f45993d5657e2afb96e4a730b9033673af7ab0ef
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c72f0bfbdef1a5796291d24207ebf95bcc31f7f.nq.gz
│   ├── 27b4d11d70f058d4beffb97cf8ebb9acdacaeb12.nq.gz
│   ├── 3a77985ee05ab4d62db12572e08999153f58d160.nq.gz
│   ├── 50e365a9091df909d7d882f540e5e8eaf6c05209.nq.gz
│   ├── 81415803ec2750c82251e896e7eb7b0ac842dac1.nq.gz
│   ├── 825010a37cd22519949de6e9630726c6db6c313b.nq.gz
│   ├── 8d33409d5bb13672bbf55c5ed02ee4d07464f3ea.nq.gz
│   ├── a402bd4541d52f7a6ac80ad4d0c344e55c20352b.nq.gz
│   ├── c4c6022f2982e8dae64cebd6b9a2b59f2547faad.nq.gz
│   ├── da5074b97f7d4da61e2fab2f14e7e31bb7760880.nq.gz
│   ├── e060cd7c8eeee65daa825dd9cee4daf82395c612.nq.gz
│   ├── f6ee9e0444847a504cee0d978e0b800b5f4a4882.nq.gz
│   └── fc6c299b73e792ef288e785c22393a5df9dded4b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── f45993d5657e2afb96e4a730b9033673af7ab0ef.nq.gz
├── filetree
│   └── f45993d5657e2afb96e4a730b9033673af7ab0ef.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 23 files
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

[sphinx-contrib/jquery](https://github.com/sphinx-contrib/jquery)

---
*Parsed on 2026-04-18 by [repolex](https://repolex.ai)*
