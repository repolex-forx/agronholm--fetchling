# Repolex Knowledge Graph of agronholm/fetchling

RDF knowledge graph data for [agronholm/fetchling](https://github.com/agronholm/fetchling), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/fetchling
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0389e6766c4310bfcf42e8d117f824b64422f1fa
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0389e6766c4310bfcf42e8d117f824b64422f1fa
│           └── chunk-001.nq.gz
├── blob
│   ├── 02e1dcbad95e49f62bf58c5f25fe033f6218e0ac.nq.gz
│   ├── 0651577bb3bb14337de2cc1de500bc5626cd0d67.nq.gz
│   ├── 0788885686b165038b920375181685f4772b9e7c.nq.gz
│   ├── 0af623fd503730fe75f5d617c2cac383d568b126.nq.gz
│   ├── 1289ba08a50ca475ff9b5f4fc4211c24a32c60e3.nq.gz
│   ├── 1508ace0e4370633ccaf5b34749d6a67dfc24568.nq.gz
│   ├── 1abf559c83e36540e0c35455605ca886cf61cb4c.nq.gz
│   ├── 1c727006ce1c5169926f32ced41580d06628c251.nq.gz
│   ├── 1e57ebcc8feec205e9539eda1666cd78de92edd7.nq.gz
│   ├── 3238132562cb3520b65d786c940ae30842cf4d38.nq.gz
│   ├── 37d9709d0a544cd4db0cd07241cc76a06f99fb82.nq.gz
│   ├── 3c1382b71f2cb7a599b8eef83d28c4eaba37dbe3.nq.gz
│   ├── 45a2f73673edab66a13ab5de206142341e996f10.nq.gz
│   ├── 50ccfc2442a094bf70948f07165fc71156755f02.nq.gz
│   ├── 577025603a1ffaef0635319814be48910ce5acf6.nq.gz
│   ├── 5e0a220c968e23f82909ed2bbb9cd2d16b70bd47.nq.gz
│   ├── 602f2b12019664b7b5b2758f3337710af4c565cb.nq.gz
│   ├── 669f3c388d176aaa696ca8faec3e2abf53cba73d.nq.gz
│   ├── 68db9420afaa803b58c845e1a20989ddb42b33cc.nq.gz
│   ├── 732b618be34328bea8dcf56dea208f5b7e39a40c.nq.gz
│   ├── 80c29f331c6b60732261a996aea019c835c9385c.nq.gz
│   ├── 8259e11a60c27895d7202969c6f1ffdbf40b80e5.nq.gz
│   ├── 866644440f7a5053b4cfd7e2a509778d62669208.nq.gz
│   ├── 9392b19ec65f14db6da7d2821eb001f3460ceab7.nq.gz
│   ├── 97f22f15ce0adda88bbe93e73b9ff47a9968a9ed.nq.gz
│   ├── 9ee3d3d122593a4fcb9988c2bf61cc13f2f4a923.nq.gz
│   ├── a73dda9e6a9836247980c152ad2b6f9f3bfa629f.nq.gz
│   ├── bb686b0adbd5e4fa0ec6defad12add03f51967b1.nq.gz
│   ├── d11aeab257da32b32eb54f4efa113455c0693f26.nq.gz
│   ├── d4fa132c573fe06c8ad5afab63b0f726db3231ef.nq.gz
│   ├── d738b9cd855be34a087eeedfd6c0316d48d0ef13.nq.gz
│   ├── e2ab7d4bf7408002e769287b9c760aaf9e1747b3.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ea311ca01ff1d9df6742f4534a3708a73038e572.nq.gz
│   ├── eba0f12ffbec22adcaed55e757ec3ec68549e8e5.nq.gz
│   ├── ecb1e8b48dea16f3494431206d75c85b8321ade6.nq.gz
│   └── efba5fcbfb37883d3069e71995cd94924d8d4e0a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0389e6766c4310bfcf42e8d117f824b64422f1fa.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 44 files
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

[agronholm/fetchling](https://github.com/agronholm/fetchling)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
