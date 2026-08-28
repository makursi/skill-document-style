# document-style

An Agent skill that **proofreads** Chinese technical documentation against a Chinese technical writing style guide: **audit** (per-violation report), **revise** (corrected full text), **update** (edit files in place).

## Key Features

- One rule set across 6 modules: titles, text & spacing, paragraphs, numbers, punctuation, document structure & filenames
- Every rule carries an ID, a severity (error / warning / suggestion), correct & incorrect examples, and a check hint
- Per-document exception list (`style-exceptions` frontmatter or verbal) for explicit exemptions
- User-invoked: `/skill:document-style`

## Rules Source & Credits

The writing conventions come from [makursi/document-style-guide](https://github.com/makursi/document-style-guide), a fork of [ruanyf/document-style-guide](https://github.com/ruanyf/document-style-guide) (public domain). The 12 external guides it references are documented in `references/provenance.md`.
