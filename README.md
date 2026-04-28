# RCFE Title 22 Cheat Sheet

Open-book state exam quick-reference for California Residential Care Facilities for the Elderly (RCFE) administrators. Compiles to a polished, navigable PDF on Overleaf or any standard `pdflatex` toolchain.

## Quick Start (Overleaf)

1. Download or clone this repository.
2. Compress the entire folder into a `.zip`.
3. In Overleaf: **New Project → Upload Project → drop the .zip**.
4. Set the main document to `main.tex` (Overleaf usually auto-detects).
5. Click **Recompile**. Run twice for the table of contents and bookmarks.

## Quick Start (Local)

```bash
pdflatex main.tex
pdflatex main.tex   # second pass for TOC + cross-references
```

Required packages: `geometry`, `xcolor[table]`, `longtable`, `booktabs`,
`tabularx`, `colortbl`, `tcolorbox`, `titlesec`, `titletoc`, `fancyhdr`,
`hyperref`, `bookmark`, `enumitem`, `microtype`, `lmodern`. All ship with
TeX Live and MiKTeX.

## File Architecture

```
main.tex                       Document shell; calls every other file
rcfecheat.sty                  Packages, colors, table envs, commands
config/
  variables.tex                ALL numbers/strings/dates/citations
  metadata.tex                 Branding & palette overrides
sections/
  00-cover.tex                 Cover, disclaimer, TOC, legend
  01-master-timeline.tex       Section 1 -- deadlines & timeframes
  02-critical-values.tex       Section 2 -- temps, dimensions, ratios
  03-shall-vs-may.tex          Section 3 -- mandatory vs permissive
  04-red-flag-penalties.tex    Section 4 -- prohibited acts & fines
  05-citation-index.tex        Bonus -- alphabetical jump table
```

## Editing Conventions

| Want to change... | Edit this file |
|---|---|
| Cover title / author / edition / year | `config/variables.tex` |
| A specific deadline, dollar amount, or temperature | `config/variables.tex` |
| Color palette (navy, gold, crimson) | `rcfecheat.sty` *(top)* or `config/metadata.tex` |
| Table layout, fonts, header/footer | `rcfecheat.sty` |
| Wording of any cell | the section file under `sections/` |

Every recurring number, date, or threshold lives once in `variables.tex`. Update it there and the entire book updates.

## Citation Macros

| Macro | Renders as | Use for |
|---|---|---|
| `\TT{87211}` | **T22 §87211** | Title 22, Division 6, Chapter 8 |
| `\HS{1569.49}` | **H&S §1569.49** | Health & Safety Code §1569 series |
| `\BOTH{87211}{1569.49}` | **T22 §87211 / H&S §1569.49** | Joint citation |
| `\shall`, `\may`, `\shallnot` | colored keywords | Linguistic emphasis |

## Disclaimer

This study aid excerpts language from the California Code of Regulations,
Title 22, Division 6, Chapter 8 and the California Health & Safety Code §1569
series. It is not legal advice and is not affiliated with the California
Department of Social Services or the Community Care Licensing Division.
Always verify against the current published code.
