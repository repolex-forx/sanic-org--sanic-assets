# Repolex Knowledge Graph of sanic-org/sanic-assets

RDF knowledge graph data for [sanic-org/sanic-assets](https://github.com/sanic-org/sanic-assets), parsed by [repolex](https://repolex.ai).

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
rlex download sanic-org/sanic-assets
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 79af646b7948fdfdc3b2f98d8aeedf58eba34b5b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 79af646b7948fdfdc3b2f98d8aeedf58eba34b5b
│           └── chunk-001.nq.gz
├── blob
│   ├── 0012b049a28e1bee05e3b091398d35ea8664e12c.nq.gz
│   ├── 0d3635d11ccf92db339c433a881c0726a245696b.nq.gz
│   ├── 0dfdff3d36fa5fd612a88ba653a6bbe5c9985f81.nq.gz
│   ├── 17d4adaee0a388bd6b02c75f34f0d1ac8a5b0c0b.nq.gz
│   ├── 32195bfa1378be85364143eaf2a779de031c1f8f.nq.gz
│   ├── 5b279c61bcd61712f1c36d309feeb6a803ac6c76.nq.gz
│   ├── 5d54418f2ed5c5f2c9784430421870355ecbe476.nq.gz
│   ├── 650ffcaaeedf5a188fc104d42df134696e67f3a2.nq.gz
│   ├── 709a0bb9d89135e1394df7ae7f4cc68401135886.nq.gz
│   ├── 8a8f88083820aa72e8c21174fa022d2cf6392847.nq.gz
│   ├── 8be21a83e1b9102e96dfba1145bb6101eb908445.nq.gz
│   ├── 962ef91edaa1a07e9a1549b2915bf990089c38ca.nq.gz
│   ├── a01796d6d53290249f5db6ad68e2e76795b5e364.nq.gz
│   ├── a1b5ad95f993ace8b3dce46cec65a16cd3bd5751.nq.gz
│   ├── a32ca8533471eaa4ddb4b9320c56a4265d71a8e6.nq.gz
│   ├── cd566ecbf9943550b0483593e67296005aeb793e.nq.gz
│   ├── d98c7f44fb125fb88618139e3b4a8180dfce0455.nq.gz
│   ├── db54eb877c85803d6f0184f2593a42074e7360d2.nq.gz
│   ├── e9e040cf095b0e67bfe54ff0127d7a4ac56d43fb.nq.gz
│   ├── f56cc941aa651de69bbf12e78dfcd9889c72dd8b.nq.gz
│   └── f95ec2d62ba79ce962e62d6353120b3ecd88cf6a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 79af646b7948fdfdc3b2f98d8aeedf58eba34b5b.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 28 files
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

[sanic-org/sanic-assets](https://github.com/sanic-org/sanic-assets)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
