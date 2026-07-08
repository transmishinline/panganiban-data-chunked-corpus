# Panganiban Data — Chunked Corpus

Retrieval-ready chunks of the writings and speeches of former Philippine Chief
Justice Artemio V. Panganiban ("CJP"), split for RAG.

## Layout
| Folder | Source | Docs | Chunks |
|--------|--------|------|--------|
| `columns/`   | Inquirer "With Due Respect" columns | 785 | 13,087 |
| `speeches/`  | Speeches & addresses | 153 | 3,440 |
| `books/`     | Book chapters (incl. *The Bio-Age Dawns on the Judiciary*) | 109 | 4,112 |
| `biography/` | Biographical chapters | 35 | 939 |

## Chunk format
- Each file is a single chunk of **< 400 characters** (1 token = 1 character), split at sentence boundaries.
- Filename: `{code}_c{NNN}.md`, chunk number **resets per document** (e.g. `CA034_c000.md`, `CA034_c001.md`).
- The underscore stands in for `::` (Windows can't use `:` in filenames); the canonical chunk ID is `CA034::c000`.
- Each folder has `_chunk_manifest.csv` mapping `chunk_id, filename, source_doc, chunk_index, chars`.

Document codes: `C{theme}###` columns, `S{theme}###` speeches, `B{theme}###` books, `GC###` biography (theme A-E).
