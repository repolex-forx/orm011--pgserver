# Repolex Knowledge Graph of orm011/pgserver

RDF knowledge graph data for [orm011/pgserver](https://github.com/orm011/pgserver), parsed by [repolex](https://repolex.ai).

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
lexq download orm011/pgserver
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 64224dc266cc6f257b8f875141388674022f7e9d
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 64224dc266cc6f257b8f875141388674022f7e9d.nq.gz
│   └── repolex
│       └── 64224dc266cc6f257b8f875141388674022f7e9d
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b89002294e9fd646d1a666f17d283095260bbaa.nq.gz
│   ├── 20f91d3718e2d1cad781ec40ec3033e175d1a237.nq.gz
│   ├── 24ba7383cfc68a5a0fe3a13627fe2c6bf4061a5d.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 4a2dfc3edf1132e09ad9df45d0b053695de02a5b.nq.gz
│   ├── 6b99ffb37fcf50be93e991963f7c0e9107108801.nq.gz
│   ├── 844d42ebc4bcee9551ca80497608f4b730d3e536.nq.gz
│   ├── 9ae32b9847e886d70e413e0b550e6d098424a387.nq.gz
│   ├── a268561d831e419e0d2e21dc8508ce7ada21dc8e.nq.gz
│   ├── a70c5dd52e6654e215a2e4c9c30dfbd701b55aee.nq.gz
│   ├── a862386a4c319a49afd2f08b0b9c2c79363449aa.nq.gz
│   ├── c3e48be772e28286c646c5730134f400f2587a09.nq.gz
│   ├── c7e554dbfd9fbebea2238526dac7f861757e1141.nq.gz
│   ├── cf759a9791898df8d049c2c0eaae78eb21c8cafb.nq.gz
│   ├── d6517d168f31a469d750ba02d73339abb22abd6a.nq.gz
│   ├── d6f8b133a49e37e89c2e9267af54230cf9b9224b.nq.gz
│   ├── e318f1d58efd3bfb08a82a0db58ac860c7d656ce.nq.gz
│   ├── e40faace03dade41d7ec825b349d93f1f1c1f8c0.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e7e95b4ea0668b419f8b94d643c57d62a0e90a9e.nq.gz
│   └── fa052ed3a3b684defd342d4bc359618afacb9db8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 64224dc266cc6f257b8f875141388674022f7e9d.nq.gz
├── filetree
│   └── 64224dc266cc6f257b8f875141388674022f7e9d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 31 files
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

[orm011/pgserver](https://github.com/orm011/pgserver)

---
*Parsed on 2026-04-10 by [repolex](https://repolex.ai)*
