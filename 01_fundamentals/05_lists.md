# 05: Lists

This guide covers the standard LaTeX environments used to create itemized, numbered, and descriptive lists.

---

## List Environments

LaTeX provides three main environments for creating lists. Each `\item` command marks a new entry in the list, and these environments can be nested within each other to create complex outlines.

- `\begin{itemize}`: Creates a bulleted (unordered) list. The bullet style changes automatically for each level of nesting.

- `\begin{enumerate}`: Creates a numbered (ordered) list. The numbering format (e.g., `1`., `a)`, `i`.) changes automatically for each level of nesting.

- `\begin{description}`: Creates a descriptive list, ideal for glossaries or definitions. Each item is labeled with a term provided in `\item[term]`, which is displayed in bold.

```latex
\documentclass{article}
\begin{document}

\section*{Bulleted List}
\begin{itemize}
  \item First top-level item.
  \item Second top-level item.
    \begin{itemize}
      \item A nested item.
      \item Another nested item.
    \end{itemize}
\end{itemize}

\section*{Numbered List}
\begin{enumerate}
  \item First step.
  \item Second step.
    \begin{enumerate}
      \item Sub-step A.
      \item Sub-step B.
    \end{enumerate}
  \item Final step.
\end{enumerate}

\section*{Descriptive List}
\begin{description}
  \item[Command] An instruction that begins with a backslash.
  \item[Environment] A block that applies a specific format to its content.
\end{description}

\end{document}
```
