# 05: Lengths and Dimensions

This guide covers how LaTeX handles lengths and dimensions, including the various units of measurement and built-in parameters.

---

## Units of Measurement

LaTeX understands both absolute and relative units of length.

- **Absolute Units**: Units that have a fixed, real-world size.
  
  | Unit  | Description              |
  | :---: | ------------------------ |
  | `cm`  | Centimeters              |
  | `mm`  | Millimeters              |
  | `in`  | Inches                   |
  | `pt`  | Points (1 in = 72.27 pt) |

- **Relative Units**: Units that are defined relative to the current font size, making them ideal for creating scalable designs.
  
  | Unit  | Description                                       |
  | :---: | ------------------------------------------------- |
  | `em`  | The width of the letter "M" in the current font.  |
  | `ex`  | The height of the letter "x" in the current font. |

```latex
\documentclass{article}
\begin{document}

This example uses an absolute unit to create a fixed-size gap:
First word \hspace{1cm} Second word.

This example uses a relative unit:
{\large This word \hspace{2em} and this word are further apart.}
\end{document}
```

---

## Common Length Parameters

LaTeX provides several commands that act as variables, holding the current dimensions of various page elements. These are most often used to size images, tables, or other blocks relative to the page layout.

- `\textwidth`: The width of the main text block on the page.

- `\textheight`: The height of the main text block on the page.

- `\linewidth`: The width of the current line. In a single-column layout, this is usually the same as `\textwidth`, but it can be narrower inside environments like lists or multi-column layouts.

- `\parindent`: The amount of horizontal indentation at the beginning of a paragraph.

```latex
\documentclass{article}
\usepackage{graphicx} % Required for \includegraphics

\begin{document}

This image is scaled by 50\% of the total text width.
This ensures it will always be half the width of the text block,
even if the page margins change.

\includegraphics[width=0.5\textwidth]{example-image-a}

\end{document}
```

---

## Modifying Length Parameters

The value of any length parameter can be changed using the following commands, typically placed in the preamble to affect the entire document.

- `\setlength{\command}{length}`: Sets the value of a `length` `\command` to a specific length.

- `\addtolength{\command}{length}`: Adds a `length` to the current value of a length `\command`.

```latex
\documentclass{article}

% Set the paragraph indent to 0pt in the preamble
\setlength{\parindent}{0pt}

\begin{document}

This is the first paragraph. It is not indented, because
the value of the \verb|\parindent| parameter was changed.

This is the second paragraph. It is also not indented.

\end{document}
```
