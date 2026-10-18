# Repolex Knowledge Graph of jaraco/inflect

RDF knowledge graph data for [jaraco/inflect](https://github.com/jaraco/inflect), parsed by [repolex](https://repolex.ai).

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
rlex download jaraco/inflect
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0aa3f7a951616101bb67dedc385163e74a3f05e7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0aa3f7a951616101bb67dedc385163e74a3f05e7
│           └── chunk-001.nq.gz
├── blob
│   ├── 1f2aa7533b0423a8eb943f6f4ec02498e39581a0.nq.gz
│   ├── 2375c3ab955e679e33fcede72c756085ffb6b129.nq.gz
│   ├── 2e3f4dd791a6372b427d618eb0baa8c4dc58e5f0.nq.gz
│   ├── 304196f81e11a168c9894f966e4a617ebf4ed53c.nq.gz
│   ├── 41566f3cc347c0e4c001934bbe9012bd1918a8b3.nq.gz
│   ├── 44f0fc36624d848e335e3d4caf6f2dbc5020eaf2.nq.gz
│   ├── 48233d9e8bde6ecd3f52cf7112a302bc8fe3b395.nq.gz
│   ├── 54c9000ec94341dd65c2053251b85b124017b9b5.nq.gz
│   ├── 54cc8303b22089e12053e552d4e6cb852a865b8a.nq.gz
│   ├── 54f99acbfac68c2be8283174ea64f1730a795e49.nq.gz
│   ├── 577e87a793a20e413f7321f4f17ec1eba2ea1962.nq.gz
│   ├── 5bdc232005af9be104a00437ae9bc64417a4c1cc.nq.gz
│   ├── 5c05f9e27d57a4b7a3c3a9fdfecf8cddb8be499f.nq.gz
│   ├── 6b36d026cbcba9935b492f87ac034c07e57848b7.nq.gz
│   ├── 700235be57c1b2872455c0be5333f59cf568e252.nq.gz
│   ├── 7102c30766bce59cbce09aaa120f2bb5a1e5b841.nq.gz
│   ├── 724370638fc188317bbc7dc868f1a571995fd796.nq.gz
│   ├── 7fc25089e0e5f573523a40a3620ae15401e90124.nq.gz
│   ├── 88787f1da7c50c6d800fcf6aab38f7ad2559f0c6.nq.gz
│   ├── 93523925a62bc590934720e90c5db189d180e16a.nq.gz
│   ├── 9a0f3bce1395ae3819030b822e5d9076c85068ea.nq.gz
│   ├── 9baf47da52848e8db3a6c773a5f51a628929c0a8.nq.gz
│   ├── 9fca2db28e54f2cc0cecf77dc54ef23c7b7c80cb.nq.gz
│   ├── a46c710da0b19dda24a23d13845b52c15efcc2db.nq.gz
│   ├── a62559cb853e532888f78dab009675b87a883df1.nq.gz
│   ├── ae74795f9a5b17ab08df9d799e7d4a26bdedb4cd.nq.gz
│   ├── b34fd79ef19717516a45bb0f647783d04f6fcd71.nq.gz
│   ├── c1f01908890e6d675b4c0482eb5b30842b8d9acd.nq.gz
│   ├── ca7eada9fd491a76ee6dea46e304d3e23ffdf126.nq.gz
│   ├── d226e149623898a43f35ab57295bb82004dc7d8d.nq.gz
│   ├── d490103f0ec2f2ddfbe9a95536b942e296a032cd.nq.gz
│   ├── d7fadafa23493c51ad0ff4896432ffb6ea703a01.nq.gz
│   ├── d968f97d22b665ba7c013abebc2c92bc33bd0019.nq.gz
│   ├── dc058b5fc89aa6a613a786ae79cde596217b0409.nq.gz
│   ├── e05a3d4a2ab888e32952006d8cd380864368db5f.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── efcb8cbc2043faa7caf4f92fc7488bd6914c934c.nq.gz
│   ├── f167883c829dd0c3d6f56303aa9b17d8ca64b3df.nq.gz
│   └── f38327ed22fc1395f381341dc048bb16b0baf342.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0aa3f7a951616101bb67dedc385163e74a3f05e7.nq.gz
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

[jaraco/inflect](https://github.com/jaraco/inflect)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
