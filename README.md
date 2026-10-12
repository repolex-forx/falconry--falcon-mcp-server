# Repolex Knowledge Graph of falconry/falcon-mcp-server

RDF knowledge graph data for [falconry/falcon-mcp-server](https://github.com/falconry/falcon-mcp-server), parsed by [repolex](https://repolex.ai).

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
rlex download falconry/falcon-mcp-server
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3cafe80225232845be8937af76f1dc6d6d99a3df
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3cafe80225232845be8937af76f1dc6d6d99a3df
│           └── chunk-001.nq.gz
├── blob
│   ├── 02d7443f3e15b2521ca46f6d11e00c4266134da9.nq.gz
│   ├── 0cee395fe2bab6a0eb281aaf2921a19b20f140d3.nq.gz
│   ├── 0d5bae39f80b35f52f0b8da4f793bfca1348d415.nq.gz
│   ├── 1202dae209c24d3739b290594e0b327c4647ba2c.nq.gz
│   ├── 16d8fb02975a2211fdd4e5e371020b31239189a5.nq.gz
│   ├── 1a09eb70700cc5ea91ca60a19d76f619d9f0d2b1.nq.gz
│   ├── 26e40096fdd185582ece73136153eaf86a8f8f24.nq.gz
│   ├── 3825f840dd89175cb4e8a66482eddf3d1cd42e48.nq.gz
│   ├── 3ad4dc1224480cfb8ef2a3997b6d3ada2a23655c.nq.gz
│   ├── 492660eff59aeafa6f15e029a45cef5b371a80b2.nq.gz
│   ├── 4c0d0c3c9a737d9af5747fdb73ea2e4b19f7bb09.nq.gz
│   ├── 580f87ed14ab2df2ab30fa6b85b0968ee004ecb7.nq.gz
│   ├── 622ec79a04e48f4ae7407654d0307ed21c4c0a9e.nq.gz
│   ├── 67cdc4f766710f301d9b91c8966453520600cb85.nq.gz
│   ├── 7c690e0807924289be738a931bead02091c81c63.nq.gz
│   ├── 7cf5229c641022d01c0f0e3253bc706ecdda15fc.nq.gz
│   ├── 80734c1e20d7fa1c4ff0dbc430fe576d97b9487f.nq.gz
│   ├── 900ca82320c6069d3aa80b3a06d741ad7aa35adf.nq.gz
│   ├── 918fadfe0ee1fc00120465d1e7de9eeddde7f43d.nq.gz
│   ├── 9f232c02364928e4bbb44e34eb03b2551a3fa32e.nq.gz
│   ├── 9ff9f0dd845c00a5f6d3a9960075163f8f71d60a.nq.gz
│   ├── ab79fca2e0ac8fdee5855425d2345406e4e12bd4.nq.gz
│   ├── af9090cd23518d3a0e462b5d68b3861f46f37f52.nq.gz
│   ├── b784afc5c74bd69cbd1bf0acb144fca351971894.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ea60a0c717f673f3a1f799c85b2a2322fc489355.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3cafe80225232845be8937af76f1dc6d6d99a3df.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 32 files
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

[falconry/falcon-mcp-server](https://github.com/falconry/falcon-mcp-server)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
