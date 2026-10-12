# Repolex Knowledge Graph of pyca/bcrypt

RDF knowledge graph data for [pyca/bcrypt](https://github.com/pyca/bcrypt), parsed by [repolex](https://repolex.ai).

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
rlex download pyca/bcrypt
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0e84f64b2885b18f0e29843169619952233f8867
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0e84f64b2885b18f0e29843169619952233f8867
│           └── chunk-001.nq.gz
├── blob
│   ├── 00063d2adedc5eeda59ee6302d8096fdf660b0e5.nq.gz
│   ├── 028f8e476fd84cc7dd9df7f7887ddfefa16541a4.nq.gz
│   ├── 048903d60c351e561d951c92b77c46241156f8b4.nq.gz
│   ├── 11069edd79019f7dafbe3138841cf289209270dd.nq.gz
│   ├── 12e4a2ef403317a97b32005dcd6de1232a93a548.nq.gz
│   ├── 20e02d1a2760b05ef9569f011724ddaa7fec4585.nq.gz
│   ├── 2512cc22b8802007a2521c81dc8623f2af2f83fc.nq.gz
│   ├── 2b6051dbe05d9e8807430e859b55acfd9a22d707.nq.gz
│   ├── 3a790dbb80b3dba2841506ed172bbd8756b13e77.nq.gz
│   ├── 3f2960d76d501fc6747f02d3766a0ef890b02b27.nq.gz
│   ├── 4b1cd65e731eebc2646f3b27ca0192ecda6ca3e4.nq.gz
│   ├── 4bdbdc91985642ef70bf650d0e777f30b20ab5cb.nq.gz
│   ├── 58688d637ce3c4f1c596758665bd814517da6b13.nq.gz
│   ├── 61233af09c467fda4f9dd4359c4faebdb25e8a58.nq.gz
│   ├── 69bc7081efbef662337d2fbb4daeac3d8e44b9ad.nq.gz
│   ├── 6f9ff7837a2ea6872de717c34d562fe5754a6aa0.nq.gz
│   ├── 7cd166585bbbefec563109d8c25cd6c02fc40279.nq.gz
│   ├── 81a92fd42513254ea6580d66df6006a0a887be21.nq.gz
│   ├── c0e9c007b1c83c75378e748e74a9ed11231edbd7.nq.gz
│   ├── c995bcb5d41df70af603a4b24fb527642239fcb6.nq.gz
│   ├── e40d10de31656412db55a9a1bc83af71e491c49f.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ebfc29fc1a67c55dce0d7afb1b41c4b29e5cb346.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0e84f64b2885b18f0e29843169619952233f8867.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[pyca/bcrypt](https://github.com/pyca/bcrypt)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
