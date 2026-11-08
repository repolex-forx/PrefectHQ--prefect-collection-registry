# Repolex Knowledge Graph of PrefectHQ/prefect-collection-registry

RDF knowledge graph data for [PrefectHQ/prefect-collection-registry](https://github.com/PrefectHQ/prefect-collection-registry), parsed by [repolex](https://repolex.ai).

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
rlex download PrefectHQ/prefect-collection-registry
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6be8519e91835916a26eab58c54c766dd3de59f1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6be8519e91835916a26eab58c54c766dd3de59f1
│           └── chunk-001.nq.gz
├── blob
│   ├── 094f128ef25a37d581dbcee3606eba6b8eb81e2d.nq.gz
│   ├── 0d958a4cff8a9474811c0e77356d5c44ca55b2b6.nq.gz
│   ├── 0e165339c47f76d953187968f2603324c8a357b5.nq.gz
│   ├── 0fc52d09923a80ead8d99014dfb92920267efa99.nq.gz
│   ├── 11c677a3c24ef99c5068ea51cddde117f95db3f2.nq.gz
│   ├── 19873523161e8e236b0676d6920218755064c149.nq.gz
│   ├── 25a0085d629ae2574df9645e9ba55bee6b9df4c2.nq.gz
│   ├── 26ab9383a53b0b19abeb1bb700c1793ffa4076d5.nq.gz
│   ├── 2f94d3c7848c474733154a787fb7791ea18188ec.nq.gz
│   ├── 31836665cbb251c90f8124452b54606aecb98c19.nq.gz
│   ├── 494eb97b30ee9d6f9116d038df250fe7aa7fc1e9.nq.gz
│   ├── 570ab1baf64b4b4b928532a0654901da85deaae3.nq.gz
│   ├── 5ce381d1379512e975d0ed85e837937f180fdf8a.nq.gz
│   ├── 608a894e68a444ad1a398c671d86cf5cded08c3a.nq.gz
│   ├── 6e574d7e996e86951f5f5645f345273fdaccef38.nq.gz
│   ├── 79eae695d17946d2693f88eddb22f576d972bf02.nq.gz
│   ├── 8b8e82ee2c0cd67b5894847c7c16d31c680a07d0.nq.gz
│   ├── 93fd4c7f724a9f69c333c733fbffbce35cf94233.nq.gz
│   ├── 9f255f86ba3e26393c39700f18902554477c76f5.nq.gz
│   ├── a04a0862c2606e2922af6e83e570c072ed490da5.nq.gz
│   ├── a85f9130a53cd9aa8b6e7d238719e992dee2efa9.nq.gz
│   ├── b33cdf736a3ef80ee6243b3a0bda3bd33f578fc1.nq.gz
│   ├── bb9ad3505c75f7a068df85615bc8a5552df45cc8.nq.gz
│   ├── c80b172fc4404ae357f5a29a9e27e407337030ee.nq.gz
│   ├── d7dbfd37544c261d31ad43ebc4c4db294fc83e40.nq.gz
│   ├── e3331e28a9d9d756bf34640c65c6405d29e9dc7c.nq.gz
│   ├── e61aebaf4d8923ff8926144c5e980d6a968b63af.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f4d783dadccd78ed1d88365aa44d997aca5aea25.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6be8519e91835916a26eab58c54c766dd3de59f1.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 37 files
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

[PrefectHQ/prefect-collection-registry](https://github.com/PrefectHQ/prefect-collection-registry)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
