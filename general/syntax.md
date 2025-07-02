# LaTeX Syntax Overview

This guide provides a concise overview of the basic LaTeX syntax needed to write and compile documents effectively.

---

## 1. Repository Structure

```latex
\documentclass{article} % or book, report, etc.
\begin{document}
Hello, world!
\end{document}
```

- `\documentclass{...}` specifies the document type.
- Everything to be rendered goes inside `\begin{document} ... \end{document}`.

---

## 2. Commands

LaTeX commands start with a backslash (`\`) followed by the command name.

```latex
\title{Title}
\author{Author Name}
\date{\today}                   % Sets the date + insert's today's date
\maketitle                      % Prints the title, author, and date

\section{Top-level Section}
\subsection{Subsection}
\subsubsection{Sub-subsection}

\textbf{Bold text}
\textit{Italic text}
\underline{Underlined text}
\emph{Emphasize}
```

- Commands may have:
  - **Required arguments** in `{...}`
  - **Optional arguments** in `[...]`

---

## 3. Comments

```latex
% This is a comment
```

- Everything after `%` on a line is ignored.

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

Curly braces `{}` group text or scope command effects.

```latex
{\bfseries This text is bold.}
```

---

## 6. Whitespace Rules and Line Breaks

- Multiple spaces are treated as one.
- Empty lines start new paragraphs.
- `~` for a non-breaking space.
- `\\` for a line break.
- `\newline` to force a line break.
- `\newpage` to start a new page.

---

## 7. Verbatim

Use the `verbatim` environment or `\verb|...|` to include raw text.

```latex
\begin{verbatim}
This is raw text # $ % &
\end{verbatim}
```

---

## 8. Input and Output

* Use `\input{file}` to include other `.tex` files.
* Use `\includegraphics{image}` (requires `graphicx`) for images.

---

## 9. Compiling

Use a LaTeX compiler like `pdflatex`:

```bash
pdflatex filename.tex
```

---

Next: Learn more about [Environments](./environments.md) and [Math Mode](./math-mode.md).
