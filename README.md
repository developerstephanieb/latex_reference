# LaTeX Reference

A structured collection of LaTeX syntax, packages, templates, and practical examples.

---

## Repository Structure

```
latex_reference/
├── 01_fundamentals/
│   ├── 01_syntax.md
│   ├── 02_document_structure.md 
│   ├── 03_text_formatting.md
│   └── 
├── 02_packages/
│   ├── amsmath.md
│   ├── amssymb.md
│   ├── geometry.md
│   ├── graphicx.md
│   ├── hyperref.md
│   ├── listings.md
│   ├── xcolor.md
│   └── tikz.md
├── 03_templates/
│   ├── article/
│   └── resume/
├── .gitignore 
└── README.md
```

latex_reference/
├── 01_fundamentals/
│   ├── 01_document_structure.md
│   ├── 02_text_formatting.md
│   ├── 03_floats_tables_figures.md
│   ├── 04_math_mode.md
│   └── 05_cross_referencing.md
├── 02_packages/
│   ├── 01_geometry.md
│   ├── 02_graphicx.md
│   ├── 03_amsmath_amssymb.md
│   ├── 04_hyperref.md
│   ├── 05_listings.md
│   ├── 06_xcolor.md
│   └── 07_tikz.md
├── 03_templates/
│   ├── article/
│   ├── resume/
│   └── beamer_presentation/
├── .gitignore
└── README.md

## Compiling

To compile a `.tex` file locally:

```bash
pdflatex filename.tex
```

Or use [Overleaf](https://www.overleaf.com/) to compile online.
