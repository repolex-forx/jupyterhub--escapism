# Repolex Knowledge Graph of jupyterhub/escapism

RDF knowledge graph data for [jupyterhub/escapism](https://github.com/jupyterhub/escapism), parsed by [repolex](https://repolex.ai).

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
rlex download jupyterhub/escapism
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ae458c5ad90e66d42c5e55e97e1b72e128cf0b99
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ae458c5ad90e66d42c5e55e97e1b72e128cf0b99
│           └── chunk-001.nq.gz
├── blob
│   ├── 30366e93404d73e90807e550c8c607cedbdcad19.nq.gz
│   ├── 3e2174d257a94eb5b19238efcdc5c3203150c7ef.nq.gz
│   ├── 7d91a7a3a4fb7da008f2ee54f4caa8ac0d245f57.nq.gz
│   ├── 7ef44f5bb66f33e143be731f88070d3e257f78bc.nq.gz
│   ├── 944f38bdf10fd16aa8a47ebca30ccd0dfa90bc8a.nq.gz
│   ├── 9c3f03cf1e44c6dd8faa644c55fa6f7555886765.nq.gz
│   ├── a8b867d7c5b474e3a261894bdbc0c14dca77df31.nq.gz
│   ├── b0dfe8b9ace20583206d01b93b917d7a0628da4c.nq.gz
│   ├── b4d84262d479597add61b589d4103fcf184866a3.nq.gz
│   ├── b6b5b9f280191611504993775ba784b134e8abaa.nq.gz
│   ├── e45ef1fd5e32f39d8603a6556f65d260dc6b152a.nq.gz
│   └── e8e76ee1ed7e23132272a80caa3ff4afdedc6dbc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ae458c5ad90e66d42c5e55e97e1b72e128cf0b99.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 20 files
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

[jupyterhub/escapism](https://github.com/jupyterhub/escapism)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
