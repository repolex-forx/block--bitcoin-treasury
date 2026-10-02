# Repolex Knowledge Graph of block/bitcoin-treasury

RDF knowledge graph data for [block/bitcoin-treasury](https://github.com/block/bitcoin-treasury), parsed by [repolex](https://repolex.ai).

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
rlex download block/bitcoin-treasury
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6b199a06efc87493eb3848ffc8bdc37688220c09
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 6b199a06efc87493eb3848ffc8bdc37688220c09.nq.gz
│   └── repolex
│       └── 6b199a06efc87493eb3848ffc8bdc37688220c09
│           └── chunk-001.nq.gz
├── blob
│   ├── 1a69fd2a450afc3bf47e08b22c149190df0ffdb4.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2b9bf312712299779c2823c4f9e254908907d363.nq.gz
│   ├── 2c9f222fe799b7c6c70c3f3a3804ca45ed402e89.nq.gz
│   ├── 2e11ed7d0f3c0a85612eff26faca880452fd2c01.nq.gz
│   ├── 36bb29d2da25bc2526e56f5ba8babc3658ba1ff4.nq.gz
│   ├── 43c70a4d8c2b5f2b556bc050219e7b24780fb315.nq.gz
│   ├── 44970edcc031faa2bdc755bcf796e7b5bccdf89d.nq.gz
│   ├── 581545133e34d1ac86f7e86f499ba2caae75a276.nq.gz
│   ├── 61d26fa8b744d6565630ea23ef206c69b0a8d47c.nq.gz
│   ├── 626c3d3a21ed92b7fef5dc6930f5ad03fac11f51.nq.gz
│   ├── 718d6fea4835ec2d246af9800eddb7ffb276240c.nq.gz
│   ├── 79ca6db7ad493eafa157f07696c46b916a4b441d.nq.gz
│   ├── 8b2d9a4b38f68f62355d3f6810873cbc8d86bc4a.nq.gz
│   ├── 9cdcfd06a3bcb9b60ac06ed60aee4fd133579c03.nq.gz
│   ├── a2ad9ba2c892d64212faaea7be18f7c920ff32f5.nq.gz
│   ├── ac8552c386e2c98dbde02ac3fb11a51b2765dde4.nq.gz
│   ├── af2b210aa9065f514bcdc13c95b260c7bdf49747.nq.gz
│   ├── bfe57c035a25fc3ccc122f8c52bfdb4f9f5246f8.nq.gz
│   ├── c17576b044554cac56c37c1fa5e085cb0a56f3f4.nq.gz
│   ├── c7e1b2d5aa6a22f59a8cea0f29798eb10b64f76a.nq.gz
│   ├── dbeb87cc5da3840cfb9d430244cf69df279b16e5.nq.gz
│   ├── de9f476c491630223a3c6019b57347126168c8ba.nq.gz
│   ├── e25cf767b98397088c37e7ec63a60ab65d233389.nq.gz
│   ├── ea57098aaa769db8f136a63b28ad5287a094774c.nq.gz
│   └── fd45c4f95dcf8ba7776b5883b6de0c2397ea418e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 6b199a06efc87493eb3848ffc8bdc37688220c09.nq.gz
├── filetree
│   └── 6b199a06efc87493eb3848ffc8bdc37688220c09.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 36 files
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

[block/bitcoin-treasury](https://github.com/block/bitcoin-treasury)

---
*Parsed on 2026-10-02 by [repolex](https://repolex.ai)*
