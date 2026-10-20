# Repolex Knowledge Graph of asottile/markdown-code-blocks

RDF knowledge graph data for [asottile/markdown-code-blocks](https://github.com/asottile/markdown-code-blocks), parsed by [repolex](https://repolex.ai).

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
rlex download asottile/markdown-code-blocks
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b40eb98ccf56567415e92f46a2ab483194e9eedd
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b40eb98ccf56567415e92f46a2ab483194e9eedd
│           └── chunk-001.nq.gz
├── blob
│   ├── 03cc07254a1ce83a5d2891fb3322d82b59b0de14.nq.gz
│   ├── 0c5a37eb0adeb312718e533d0a4fbcbea6880056.nq.gz
│   ├── 0f38a4f4c38383972aaeae3d92f8ed121daa6cd1.nq.gz
│   ├── 1552d96bb1043bed0d30f690915851e275e6ef39.nq.gz
│   ├── 3d93aefb2da505dba9c0114404cfaaeee5ad0d3f.nq.gz
│   ├── 3fdffa121e3b0e62264cdf10bc360c93537670b7.nq.gz
│   ├── 522fbe20b89911bb8d68b4a684a51225dd571764.nq.gz
│   ├── 5370c9485451439199ab7ab9ba30c95d9a046275.nq.gz
│   ├── 997c16478fc31800ee501041a6dcc17cfe241bbe.nq.gz
│   ├── ca1d90ea180858ae143c0e62d920e350d3acc62d.nq.gz
│   ├── e3c45e369338e3a2eb1ed011e48db4bdc4643094.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b40eb98ccf56567415e92f46a2ab483194e9eedd.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 19 files
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

[asottile/markdown-code-blocks](https://github.com/asottile/markdown-code-blocks)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
