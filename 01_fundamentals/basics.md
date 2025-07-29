# LaTeX Basics

This guide provides an overview of the basic LaTeX syntax needed to write and compile documents.

---

## Table of Contents

[Basic Document Structure](#basic-document-structure)   
[Commands](#commands)   
[Comments](#comments)    
[Special Characters](#special-characters)    
[Grouping](#grouping)    
[Whitespace Rules](#whitespace-rules)   
[Entering Math Mode](#entering-math-mode)   
[Environments](#environments)   
[Verbatism](#verbatim)   
[External Files](#external-files)   
[Images](#images)   
[Compiling](#compiling)   

---

## Basic Document Structure

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

## Commands

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

## Comments

Everything after `%` on a line is ignored.

```latex
% This is a comment
```

---

## Special Characters

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

## Grouping

Curly braces `{...}` group text or scope command effects.

```latex
% Scoped command
{\bfseries This text will be bold}, but this will not.

% Unscoped command
\bfseries This text will be bold, and so will this.
```

---

## Whitespace Rules

- **Multiple spaces or line breaks** are treated as one.
- **New Paragraphs**: Blank lines start new paragraphs.
- **Line Breaks**:
  - Use `\\` or `\newline` for a line break.
  - Use `~` for a non-breaking space to keep words together (e.g. `Dr.~John~Doe`).
  - Use `\newpage` to start a new page.

---

## Entering Math Mode

## Entering Math Mode

For inline math, enclose the expression in single dollar signs `$...$`. For display math, which centers the formula on its own line, use `\[ ... \]`.

```latex
This equation is written inline: $E = mc^2$

This equation is shown using display math:
\[
    F = ma
\]
```

---

## Environments

Use `\begin{environment} ... \end{environment}` to structure and format blocks of content.

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

## Verbatim

Use the `verbatim` environment or `\verb|...|` to include raw text.

```latex
\begin{verbatim}
This is raw text # $ % &
\end{verbatim}

\verb|This is also raw text # $ % &|
```

---

## External Files

Use `\input{...}` to include other `.tex` files.

**Note**: Included file should **not** have its own `\documentclass` or `\begin{document}`.

```latex
\input{chapter1}  % Loads chapter1.tex
```

---

## Images

Use `\includegraphics{...}` from the `graphicx` package to insert images.
- Supports .png, .jpg, and .pdf
- Optional arguments like `width`, `height`, `scale`, and `angle` control the image’s appearance.

```latex
\usepackage{graphicx} % Add this in the preamble

\includegraphics[width=0.5\textwidth, angle=10]{image.png}
```

---

## Compiling

Use a LaTeX compiler like `pdflatex`:

```bash
pdflatex filename.tex
```

Or use [Overleaf](https://www.overleaf.com/) to compile online.
