# 04: Lengths and Dimensions

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

---

## Common Length Parameters

LaTeX provides several commands that act as variables, holding the current dimensions of various page elements. These are most often used to size images, tables, or other blocks relative to the page layout.

- `\textwidth`: The width of the main text block on the page.

- `\textheight`: The height of the main text block on the page.

- `\linewidth`: The width of the current line. In a single-column layout, this is usually the same as `\textwidth`, but it can be narrower inside environments like lists or multi-column layouts.

```latex
\documentclass{article}
\usepackage{graphicx} % Required for \includegraphics

\begin{document}

The total width of the text on this page is stored in the \verb|\textwidth| command.

We can add horizontal space, like this \hspace{1cm} gap, using absolute units.

Below is an image that has been scaled to 50\% of the total text width using a relative parameter.

\includegraphics[width=0.5\textwidth]{example-image}

This ensures the image will always be half the width of the text block,
even if the page margins change.

\end{document}
```
