# LaTeX Syntax Overview

This guide provides an overview of the basic LaTeX syntax needed to write and compile documents effectively.

---

## 1. Basic Document Structure

A LaTeX document has two main parts:
1. **Preamble**: Where you specify the document type using `\documentclass{...}`, load packages, and set styles.
2. **Document body**: Where you write the content to be rendered, enclosed by `\begin{document} ... \end{document}`

```latex
% Preamble
\documentclass{article}

% Document Body
\begin{document}
Hello, world!
\end{document}
```

---

## 2. Commands

Commands start with a backslash `\`, are case-sensitive, and can take arguments:
- **Required arguments** are enclosed in curly braces `{...}`.
- **Optional arguments** are enclosed in square braces `[...]`.

```latex
\section{A New Top-Level Section}
\subsection{A New Subsection}
\subsubsection{A New Sub-Subsection}

\textbf{This text will be bold}
\textit{This text will be italic}
\underline{This text will be underlined}
\emph{This text will be emphasized}
```

---

## 3. Comments

Everything after `%` on a line is ignored.

```latex
% This is a comment
```

---

## 4. Special Characters

To print the following characters, escape them with a backslash:

| Character | Code                 |
| --------: | :------------------- |
|       `#` | `\#`                 |
|       `$` | `\$`                 |
|       `%` | `\%`                 |
|       `&` | `\&`                 |
|       `_` | `\_`                 |
|       `{` | `\{`                 |
|       `}` | `\}`                 |
|       `~` | `\textasciitilde{}`  |
|       `^` | `\textasciicircum{}` |
|       `\` | `\textbackslash{}`   |

---

## 5. Grouping

Curly braces `{...}` group text or scope command effects.

```latex
% Scoped command
{\bfseries This text will be bold}, but this will not.

% Unscoped command
\bfseries This text will be bold, and so will this.
```

---

## 6. Whitespace Rules

- **Multiple spaces or line breaks** are treated as one.
- **New Paragraphs**: Blank lines start new paragraphs.
- **Line Breaks**:
  - Use `\\` or `\newline` for a line break.
  - Use `~` for a non-breaking space to keep words together (e.g. `Dr.~John~Doe`).
  - Use `\newpage` to start a new page.

---

## 7. Math

### Inline Math
For formulas within a line of text, use single dollar signs `$...$`.

```latex
The equation for energy is $E = mc^2$.
```

### Display Math
For formulas that get their own line, use `\[ ... \]`.

```latex
The equation for energy is
\[
    E = mc^2
\]
```

---

## 8. Environments

Use `\begin{name} ... \end{name}` to structure and format blocks of content.

```latex
% Itemized list environment
\begin{itemize}
  \item First item
  \item Second item
\end{itemize}

% Centered text environment
\begin{center}
  This text will be centered.
\end{center}
```

---

## 9. Verbatim

Use the `verbatim` environment or `\verb|...|` to include raw text.

```latex
\begin{verbatim}
This is raw text # $ % &
\end{verbatim}
```

---

## 10. Including External Content

### Other Files
Use `\input{...}` to include other `.tex` files.

```latex
\input{chapter1}  % Loads chapter1.tex
```

-  Included file should not have its own \documentclass or \begin{document}.

### Images

Use `\includegraphics{...}` from the `graphicx` package to insert images.
It's best practice to wrap it in a **figure** environment to add a caption and enable cross-referencing.

```latex
\usepackage{graphicx} % Add this in the preamble

\includegraphics[width=0.5\textwidth, angle=10]{image.png}
```

- Supports .png, .jpg, and .pdf
- Optional arguments like `width`, `height`, `scale`, and `angle` control the image’s appearance.

---

## 11. Compiling

Use a LaTeX compiler like `pdflatex`:

```bash
pdflatex filename.tex
```

---

Next: Learn more about [Environments](./environments.md) and [Math Mode](./math_mode.md).
