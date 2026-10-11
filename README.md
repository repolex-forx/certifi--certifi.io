# Repolex Knowledge Graph of certifi/certifi.io

RDF knowledge graph data for [certifi/certifi.io](https://github.com/certifi/certifi.io), parsed by [repolex](https://repolex.ai).

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
rlex download certifi/certifi.io
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 545cdb27aeda0c30555537498d2186084d2c2653
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 545cdb27aeda0c30555537498d2186084d2c2653
│           └── chunk-001.nq.gz
├── blob
│   ├── 25dd8725992b10e178ce45e7f74ab4b7720015ff.nq.gz
│   ├── 2806c164989aa9137a6c1860716ae9abccef75ad.nq.gz
│   ├── 378eac25d311703f3f2cd456d8036da525cd0366.nq.gz
│   ├── 3aadfcf6d200402600c11b6d736e708702366951.nq.gz
│   ├── 3da44597ecb09c178f94bacf2abc63b4647887bb.nq.gz
│   ├── 59aed91f195baa6521e1ad205f3522d7fcde1312.nq.gz
│   ├── 5ad257080e9e932ac43cdad61abe539373523248.nq.gz
│   ├── 7587956ef0dfe26f5f648251bc7a9904af51ec14.nq.gz
│   ├── 9b8bc03d265015642ccf8d464797ff6d0a39dc93.nq.gz
│   ├── b1a8751373494d9c06637f2723fd4e3f19873019.nq.gz
│   ├── c56c93165f6c7c3458c1bd4c84ba7d1e778c594a.nq.gz
│   └── faffea176a1ece16667f0fc2174491e70c6c7875.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 545cdb27aeda0c30555537498d2186084d2c2653.nq.gz
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

[certifi/certifi.io](https://github.com/certifi/certifi.io)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
