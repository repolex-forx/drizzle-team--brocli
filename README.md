# Repolex Knowledge Graph of drizzle-team/brocli

RDF knowledge graph data for [drizzle-team/brocli](https://github.com/drizzle-team/brocli), parsed by [repolex](https://repolex.ai).

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
rlex download drizzle-team/brocli
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5bfd06b8e322ce757d29afad56bae7dff3d4f4f8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5bfd06b8e322ce757d29afad56bae7dff3d4f4f8
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c1c01ce322f156366a6382afd264028025cabc7.nq.gz
│   ├── 15440e45ff55dedd43011e8b9a8707d13fe08885.nq.gz
│   ├── 19799f8a7de496c7f3b6b7af79c661bc63ae1b9b.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 3884545aa0754d717c1b8f37df72c14d07c5df3f.nq.gz
│   ├── 38c07366b0311d2a61213c654b49ad4b3cc9c514.nq.gz
│   ├── 4627d6a2c3a5e49d2c494f4dfc1d29193b0ae4ea.nq.gz
│   ├── 4d2f13ee02b99a56bce61e83c4bfdb5ff1a93864.nq.gz
│   ├── 548f2a7123b44c2073eecbd9603e8061fed07910.nq.gz
│   ├── 565a81c577aac29a66026059e6d64e03d9278f62.nq.gz
│   ├── 6ac483608ab1582b94ed12dd7c679db9525628c7.nq.gz
│   ├── 6f09b59592653d7fa6602bf1bb64ed2b7607c2ef.nq.gz
│   ├── 7eb11c3d507ee9d0fa54e99e84253447f1e70d7f.nq.gz
│   ├── 98a398c2e91055cae85b40a8c9903c8186530900.nq.gz
│   ├── a38c58268fddb71cd4f64e52ff6d76425736789e.nq.gz
│   ├── b57ab6b00086f8e4e2e6f90e54618b9e36519ea7.nq.gz
│   ├── cf9ecafecfd8bc796d44ea37b2987c3e4bf8baa1.nq.gz
│   ├── e59179aee4ef644cb2267d987135820fd8037638.nq.gz
│   ├── e60991094f39ae2f64ed4fa50672d223f7c6b4b0.nq.gz
│   ├── fb91bbeca90429647579caaf5052cb544e55a930.nq.gz
│   └── fc8c065029e3d37d879a367a20c2d9700fc1c565.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5bfd06b8e322ce757d29afad56bae7dff3d4f4f8.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[drizzle-team/brocli](https://github.com/drizzle-team/brocli)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
