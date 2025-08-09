# 04: Page Layout

This guide covers how to control the page layout of documents, including paper size, orientation, and margins.

---

## The `geometry` Package

For control over margins, paper size, and orientation, load the `geometry` package in the preamble. While some page layout `options` can be set in `\documentclass`, it’s best practice to define all dimensions with `geometry`.

- `\usepackage[options]{geometry}`: Loads the `geometry` package, enabling page layout settings.
  
  | `options`                   | Description                                                         |
  | --------------------------- | ------------------------------------------------------------------- |
  | `a4paper`, `letterpaper`    | Sets the paper size.                                                |
  | `landscape`                 | Sets the page orientation to landscape.                             |
  | `margin=width`              | Sets all four margins (top, bottom, left, right) to the same value. |
  | `left=width`, `right=width` | Sets the left and right margins individually.                       |
  | `top=width`, `bottom=width` | Sets the top and bottom margins individually.                       |
  | `hmargin=width`             | Sets both the left and right margins to the same value.             |
  | `vmargin=width`             | Sets both the top and bottom margins to the same value.             |
  | `headsep=distance`          | Sets the space between the header and the text body.                |
  | `bindingoffset=width`       | Adds extra space to the inner margin for binding.                   |
  | `showframe`                 | Draws visible frames around the margins for debugging layout.       |

```latex
\documentclass{article}

% Load the 'geometry' package last in the preamble
\usepackage[a4paper, margin=1in]{geometry}

\begin{document}

\section{Introduction}

This page has been formatted using the \texttt{geometry} package.
The paper size is A4, and the top, bottom, left, and right margins
are all set to exactly one inch.

\end{document}
```

---

## Headers and Footers

```latex
```

---

## Columns

---

## Subpage Layouts


---

## Margin Notes


---