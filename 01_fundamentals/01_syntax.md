# 01: Syntax

The **syntax** of a LaTeX document is the set of rules governing how commands, environments, and text must be written to produce a correctly formatted document.

---

## Core Components

**Commands** issue instructions, **environments** contain blocks of content, and **comments** are used for notes within the source code.

- **Comment** (`%`): The percent sign marks the start of a comment. Any text following it on the same line is ignored by the compiler.

- **Command** (`\`): An instruction that begins with a backslash. Commands are case-sensitive and may take mandatory arguments in curly braces `{}` or optional arguments in square brackets `[]`.

- **Environment** (`\begin{<name>}` & `\end{<name>}`): A block that applies specific formatting to its content. 

```latex
% This is a comment.
\documentclass{article}

\begin{document} % Marks the beginning of the document

Hello, LaTeX!    % This text will appear in the final PDF.

\end{document}   % Marks the end of the document
```

---

## Whitespace and Line Breaks

LaTeX interprets whitespace according to specific rules and provides commands for manual spacing control.

- **Spaces and Tabs**: Multiple consecutive spaces or tabs are treated as a single space.

- **Line Breaks**: A single line break is also treated as a single space.

- **Blank Lines**: One or more blank lines mark the end of a paragraph and the start of a new one.

- `\\` or `\newline`: Forces a line break.

- `~`: Inserts a non-breaking space, ensuring that the words it connects are not separated by a line break.

- `\noindent`: Prevents the automatic indentation at the start of a paragraph.

- `\hfill`: Inserts horizontal space that expands to fill the available width.

- `\hspace{<length>}`: Inserts horizontal space of a specified length.

- `\vspace{<length>}`: Inserts vertical space of a specified length.

```latex
\documentclass{article}

\begin{document}

Multiple   spaces are treated as one.
A single
line break is also just a space.

This text starts a new paragraph because there was a blank line above it.

\noindent This paragraph starts without indentation.

The text in Section~5 will always stay together.

Left text \hfill Right text.

\end{document}
```

---

## Special Characters and Grouping

Certain characters have special meaning in LaTeX. This section covers how to print these reserved characters literally, create typographically correct quotation marks, and group content.

- **Escaped Characters**: To display a special character, prefix it with a backslash.

  | Character | Code                 |
  | :-------: | :------------------- |
  |    `#`    | `\#`                 |
  |    `$`    | `\$`                 |
  |    `%`    | `\%`                 |
  |    `&`    | `\&`                 |
  |    `_`    | `\_`                 |
  |    `{`    | `\{`                 |
  |    `}`    | `\}`                 |
  |    `~`    | `\textasciitilde{}`  |
  |    `^`    | `\textasciicircum{}` |
  |    `\`    | `\textbackslash{}`   |

- **Quotation Marks**: Typographically correct quotes are created using backticks
  (`` ` ``) for opening quotes and apostrophes (`'`) for closing quotes.

- **Grouping** (`{...}`): Curly braces limit a command's scope.

```latex
\documentclass{article}

\begin{document}

\$5.00, 100\%, R\&D, and item \#1.

``This is a double-quoted sentence.''

`This is a single-quoted sentence.'

{\large This text is large.}

\end{document}
```

---

## Verbatim Text

Verbatim tools render text exactly as it is typed, ignoring LaTeX commands and preserving all whitespace and line breaks. 

- `verbatim` **environment**: Outputs all enclosed content literally.

- `\verb|<text>|`: An inline command for literal text.

```latex
\documentclass{article}

\begin{document}

\begin{verbatim}
This is raw text # $ % &
\end{verbatim}

\verb|This is also raw text # $ % &|

\end{document}
```
