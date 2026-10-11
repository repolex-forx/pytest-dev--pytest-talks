# Repolex Knowledge Graph of pytest-dev/pytest-talks

RDF knowledge graph data for [pytest-dev/pytest-talks](https://github.com/pytest-dev/pytest-talks), parsed by [repolex](https://repolex.ai).

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
rlex download pytest-dev/pytest-talks
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6eae44166ea4d8411230567a4740deaaf43da984
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6eae44166ea4d8411230567a4740deaaf43da984
│           └── chunk-001.nq.gz
├── blob
│   ├── 012111d37ccdb0419d33ac657e8e07d5dc86884a.nq.gz
│   ├── 0cc38bac5114dae2dc4b600cf3a4a3c49df0e027.nq.gz
│   ├── 14d0a965720ce480de756d6466ba8176e8de9ce5.nq.gz
│   ├── 1eb5d6724d3d67fc78696d83d460f519d769f9c8.nq.gz
│   ├── 201cfe1fea1c2efc0591a0094d329f57f6941acf.nq.gz
│   ├── 29f896a79312c4959c4ccb4a24c5dfd043d3d8de.nq.gz
│   ├── 52abdbf97573969ffe389e22131b82db8cb25af3.nq.gz
│   ├── 566e80712cd47fc3b9f2167aae4e737e2e7f7c60.nq.gz
│   ├── 598dcbc06100e2c6ac5dcbcb7446bd1a15133550.nq.gz
│   ├── 71117fb7f0c324aa8b2a810041c27d3da3ee4ca7.nq.gz
│   ├── 7a89e881a67445733787c20291c644f5b64d518f.nq.gz
│   ├── 88b527a8bc883bd37084dc9e671210d3d81e38ea.nq.gz
│   ├── 9b639e0ba03ef3663a4725e8361a885209c5a83d.nq.gz
│   ├── a234861f9bfada3a7fd116c7851be994de1fa143.nq.gz
│   ├── ab74139c37b1ed59ee8c01a509789947b59e58c9.nq.gz
│   ├── c78b503cc1ac599aa7ec9913ffe991224b65f66a.nq.gz
│   ├── c8bff7c1d0636869fe9cf4f75668a4647fcdf326.nq.gz
│   ├── d7f3d6ccd7db262f2da41663fd9e658ac52ac519.nq.gz
│   ├── daa8c53c2a5a1b6a509b0924f4458d980214cf43.nq.gz
│   ├── e8064a694ca8eff0f2167d29ad13609f9a99a46e.nq.gz
│   ├── f24cee739b25055cbc066070ed0a161c31af8fc6.nq.gz
│   └── f2d83657216ef01fa0b32befd9f4c8a458c069fd.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6eae44166ea4d8411230567a4740deaaf43da984.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 30 files
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

[pytest-dev/pytest-talks](https://github.com/pytest-dev/pytest-talks)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
