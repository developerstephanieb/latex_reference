# LaTeX Reference

A structured collection of LaTeX syntax, packages, templates, and practical examples.

---

## Folder Structure

```
latex-reference/
├── general/
│   ├── syntax.md
│   ├── environments.md
│   ├── document-structure.md
│   └── math-mode.md
├── packages/
│   ├── amsmath.md
│   ├── tikz.md
│   ├── listings.md
│   ├── geometry.md
│   └── graphicx.md
├── examples/
│   ├── resume.tex
│   ├── report.tex
│   ├── presentation-beamer.tex
│   └── cv.tex
├── templates/
│   ├── resume-template.tex
│   ├── beamer-template.tex
│   └── article-template.tex
└── tips-and-tricks/
    ├── symbols.md
    ├── spacing.md
    ├── tables.md
    ├── figures.md
    └── troubleshooting.md
```

### `syntax.md` – *Core Syntax & Fundamentals*

Covers basic LaTeX syntax and usage rules.

**Includes:**
- What is LaTeX (brief intro)
- Commands (`\command{}`, optional arguments `[]`)
- Comments (`%`)
- Escaping special characters
- Grouping with `{}` and scoping
- Whitespace, line breaking (`\\`, `\newline`, `~`)
- Verbatim environments (`\verb|...|`, `verbatim`)
- Compiling (e.g. `pdflatex`, `xelatex`, `latexmk`)

### `document-structure.md` – *Document Layout and Content Organization*

Explains how LaTeX documents are built and organized.

**Includes:**
- Document class and preamble setup
- `\begin{document}` / `\end{document}`
- Sections and headings (`\section`, `\subsection`, etc.)
- Paragraphs, spacing, and breaking pages
- Lists (`itemize`, `enumerate`, `description`)
- Basic tables (`tabular`)
- Figures (basic insertion and captioning)
- Cross-referencing (`\label`, `\ref`)
- Including external files (`\input`, `\include`)

### `environments.md` – *Environments Overview*

Covers formal environments used in LaTeX.

**Includes:**
- What environments are and their syntax
- Common environments:
  - Lists: `itemize`, `enumerate`
  - Tables: `tabular`
  - Code: `verbatim`
  - Formatting: `quote`, `center`
  - Figures and tables
  - Math: `equation`, `align`, `cases`
- Floating environments (`figure`, `table`)
- Defining custom environments (`\newenvironment`)

### `math-mode.md` – *Mathematical Typesetting*

Details how to typeset math in LaTeX.

**Includes:**
- Inline (`$...$`) and display math (`$begin:math:display$...$end:math:display$`, `equation`)
- Subscripts (`_`) and superscripts (`^`)
- Common symbols and operators
- Greek letters and math functions (`\sin`, `\log`, etc.)
- Fractions, roots, sums, integrals
- Matrices, piecewise functions, alignments
- `amsmath` environment usage

---

## Sections

- `general/`: Core LaTeX syntax and document fundamentals
- `packages/`: Cheat sheets and usage examples for popular packages
- `examples/`: Full LaTeX source files demonstrating real use cases
- `templates/`: Minimal templates ready to use
- `tips-and-tricks/`: Common issues, formatting shortcuts, and symbol references

---

## Compiling

To compile a `.tex` file locally:

```bash
pdflatex filename.tex
```

Or use [Overleaf](https://www.overleaf.com/) to compile online.
