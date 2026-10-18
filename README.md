# Repolex Knowledge Graph of spulec/freezegun

RDF knowledge graph data for [spulec/freezegun](https://github.com/spulec/freezegun), parsed by [repolex](https://repolex.ai).

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
rlex download spulec/freezegun
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 92d61b3f5c31942a1039713574487bdcfcdbbfff
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 92d61b3f5c31942a1039713574487bdcfcdbbfff
│           └── chunk-001.nq.gz
├── blob
│   ├── 09c9c1c7501f4132627c774604ed4b4ebe8d5785.nq.gz
│   ├── 140919746c66f65e8d7104f91551e35acdf2ed57.nq.gz
│   ├── 1669ba2d392530d49fcde2fce2ef823dd8b8c082.nq.gz
│   ├── 16e2dfa5c69e52f13408e036a358aa1496c0b47d.nq.gz
│   ├── 17ec7d95fadf8679250daa6f1d8e3d9165be1ce2.nq.gz
│   ├── 1d4570b1313dabd34177a446eb43526034c0280c.nq.gz
│   ├── 202ff8454bbc87f61c744537982f6ba0ed60df2f.nq.gz
│   ├── 33d10b14c11aaea366088e95b0765000504178db.nq.gz
│   ├── 34cdbcbafa4e702a50f63594fed657b93456c30f.nq.gz
│   ├── 36afa4276cc118612cd7cf93d136d361c20470ec.nq.gz
│   ├── 3877d062d3d6a727a2fc34151e3250b2e128ed41.nq.gz
│   ├── 3e15413ed2ab6733ab4da07b3bea280b1ff8c1d2.nq.gz
│   ├── 41d30711dc63dc604e5255fbdf36acfc1f887865.nq.gz
│   ├── 474f1ebaa7b26566237616ba12fe513ac76399ff.nq.gz
│   ├── 4fd676a6263aa3cdb25ccfbe15246695acf2b3bf.nq.gz
│   ├── 5ba9f40f8de4c23f230325cb16578b63d3771a12.nq.gz
│   ├── 5bdfcd6954b2be1de32f2d049de15dd7d7eace1c.nq.gz
│   ├── 63045d8948a4b3ea2f6d128a53ffa8cd4d2e3098.nq.gz
│   ├── 6385fe28ad9755f64886551d8be2ae9900a35055.nq.gz
│   ├── 6ca35fc4d580d9b8eaea85a2b8241ca455959765.nq.gz
│   ├── 6e8c2659c3897a70feede9a1d95ae472501ed452.nq.gz
│   ├── 81ad2715946abf32fb20c685194cd5326930d080.nq.gz
│   ├── 87742d60eb6000283a0bd6924eaa2edb818611be.nq.gz
│   ├── 89a52fd25c78c78d784fd37f0363b00bd316f8f0.nq.gz
│   ├── 8a0f67eaeaccb7dff546b0002508da8241e02575.nq.gz
│   ├── 90a85e7149454f173dd595bdeb884340cc01e6f6.nq.gz
│   ├── 9d1a4eb9091572b3e9b7d65373300cfab768e50c.nq.gz
│   ├── a726f3aa96e0cca321aad3334925d9372400a340.nq.gz
│   ├── b18793f6e12cbaf3330f05ba24acf39a8182c2e0.nq.gz
│   ├── c18136a23f1cbfd5c2a155a581304ce7ae67893f.nq.gz
│   ├── c82334553632d12caf96bd3d3d332d9683d2635c.nq.gz
│   ├── cef498e007c644f230b2612938cb9f36e470ab27.nq.gz
│   ├── d5c83536988ecd64f918a9f244ebb0776f6d50e4.nq.gz
│   ├── d687925a721b74564fbf4ecc6f9210791fe51103.nq.gz
│   ├── da9c516dd744b6c88dd8c91f58f7bcf8f7e8341b.nq.gz
│   ├── dbdada35614b027fc92797f0b7786df97a7b34ea.nq.gz
│   ├── df1a3546f8db9f034ad64d666e2ad24de5da2f2d.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fc2cf98b230591fb5c5a65e5604196050a81cbc0.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 92d61b3f5c31942a1039713574487bdcfcdbbfff.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 47 files
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

[spulec/freezegun](https://github.com/spulec/freezegun)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
