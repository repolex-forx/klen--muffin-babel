# Repolex Knowledge Graph of klen/muffin-babel

RDF knowledge graph data for [klen/muffin-babel](https://github.com/klen/muffin-babel), parsed by [repolex](https://repolex.ai).

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
rlex download klen/muffin-babel
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 140c6b73b9ec2d1ba09aa6548f31cfb9cb9e5ca0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 140c6b73b9ec2d1ba09aa6548f31cfb9cb9e5ca0
│           └── chunk-001.nq.gz
├── blob
│   ├── 00b2897035484d603496bf7830626e6dde449efc.nq.gz
│   ├── 0a6ee958310ca78a98bf4803c291d5898c7fd5b4.nq.gz
│   ├── 0ce26915dd1b79fe844187601aa64d6695594d48.nq.gz
│   ├── 0d63ad150750ec84cca756c4e67d4334948d1b65.nq.gz
│   ├── 12b5a4fd00604ad17818b422545963a337960258.nq.gz
│   ├── 1514b1b85a2144cd8d827eaf4757eee5f6dfb1d0.nq.gz
│   ├── 179bf5ca1c66562e03c89df1de5fcc0c503b609f.nq.gz
│   ├── 23c5c150f58bdd129447223d88288e859f8cccb1.nq.gz
│   ├── 3f9f6f5a09d3650a3d1a77d910ed84afec3b82a6.nq.gz
│   ├── 4e67594e0cc4935576daa5f38757ecfcdc066b37.nq.gz
│   ├── 5f1d5686f3dc12105665875988bbe0b90d32c2bc.nq.gz
│   ├── 666ce2a519fd8f0c3599a11f968422b82612ca92.nq.gz
│   ├── 78df056a6afd6b2f7c5a8695635380a19f30acd9.nq.gz
│   ├── 7a3f07ab83552f47a8705fa5d22729a324a2f71a.nq.gz
│   ├── 7c3d67d34a95a18756124bb17ecd4c128cd010a2.nq.gz
│   ├── 88cc994aac8c0b74f57bb3e64f2ac2089cdcd870.nq.gz
│   ├── aed518e05a23ff77d127cd80f99d17b3c0e1c0d8.nq.gz
│   ├── ce48f87110f5a00c4f3320f9ed0c8e630cb23daf.nq.gz
│   ├── d73217e4eefbbe8fc97c421ec5362597534b150a.nq.gz
│   ├── db65568211d80147fc4e62083d6cd0ee4afc0141.nq.gz
│   ├── e4d1fc4dc522ca178467df18cd9e1a25d18ea617.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e728d03676c20ba87a39556e60b642f5df17ebde.nq.gz
│   ├── e97b5c1f81f79763aff8736e12d2c7e00cd47b89.nq.gz
│   └── ef23051ba28a3e87238a94de1f097f9bbd894ac8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 140c6b73b9ec2d1ba09aa6548f31cfb9cb9e5ca0.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 32 files
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

[klen/muffin-babel](https://github.com/klen/muffin-babel)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
