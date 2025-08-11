# 01: Syntax

This guide provides an overview of the fundamental LaTeX syntax needed to write documents.

---

## Comments

The percent sign (`%`) marks the beginning of a comment. Everything after it on the line is ignored.

```latex
% This is a comment
```

---

## Commands and the Document Class

Commands control formatting and behavior. Every LaTeX document begins with the `\documentclass` command.

- **Command**: An instruction that begins with a backslash (`\`). Commands are case-sensitive and may take mandatory arguments in curly braces `{}` or optional arguments in square brackets `[]`.

- `\documentclass[options]{class}`: A command that specifies the type of document to be created.   

  | `class`   | Purpose                             |
  | --------- | ----------------------------------- |
  | `article` | For short documents.                |
  | `report`  | For longer documents with chapters. |
  | `book`    | For books.                          |
  | `letter`  | For writing letters.                |

  | `options`                | Description                                        |
  | ------------------------ | -------------------------------------------------- |
  | `10pt`, `11pt`, `12pt`   | Sets the base font size for the document.          |
  | `a4paper`, `letterpaper` | Sets the paper size.                               |
  | `landscape`              | Sets the page orientation to landscape.            |
  | `oneside`, `twoside`     | Formats for single-sided or double-sided printing. |
  | `twocolumn`              | Typesets the document in two columns.              |

```latex
\documentclass{article}

\begin{document}

This is a simple document.

\end{document}
```

---

## Environments

Environments define blocks of content with specific formatting behavior.

- **Environment**: A block that applies a formatting style to its content, enclosed by `\begin{name}` and `\end{name}`.

- `\begin{document}`: An environment that encloses all visible content in a LaTeX file.

```latex
\documentclass{article}

\begin{document}

All visible content goes here.

\end{document}
```

---

## Whitespace and Breaks

LaTeX handles whitespace according to specific rules, and provides commands for manual control.

- **Spaces and Tabs**: Multiple consecutive spaces or tabs are treated as a single space.

- **Line Breaks**: A single line break is also treated as a single space.

- **Blank Lines**: One or more blank lines mark the end of a paragraph and the start of a new one.

- `\\` or `\newline`: Forces a line break.

- `\newpage`: Forces a page break.

- `~`: Inserts a non-breaking space, ensuring that the words it connects are not separated by a line break.

- `\noindent`: Prevents the automatic indentation at the start of a paragraph.

- `\hfill`: Adds a flexible horizontal space that expands to fill all available room.

- `\hspace{length}`: Inserts horizontal space using a specified length.

- `\vspace{length}`: Inserts vertical space using a specified length.

```latex
\documentclass{article}

\begin{document}

Multiple   spaces are treated as one.
A single
line break is also just a space.
You can force a line break\\without starting a new paragraph.

This text starts a new paragraph because there was a blank line above it.

\noindent This paragraph starts without indentation.

The text in Section~5 will always stay together.

Left text \hfill Right text.

\hspace{2em}This line begins with extra horizontal space.

\vspace{1em}

This line follows vertical space.

\newpage
This text will start on the second page.

\end{document}
```

---

## Escaping Special Characters

To print special characters, escape them with a backslash (`\`) or use a control word that represents the symbol.

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

```latex
\documentclass{article}

\begin{document}

\$5.00, 100\%, R\&D, and item \#1.

\end{document}
```

---

## Quotation Marks

To produce typographically correct curly quotation marks, use backticks (`` ` ``) for opening quotes and single apostrophes (`'`) for closing quotes. Using the standard double-quote character will result in incorrect, straight quotes.

- Single Quotes: Use a single backtick (`` ` ``) to open and a single apostrophe (`'`) to close.

- Double Quotes: Use two backticks (``` `` ```) to open and two apostrophes (`''`) to close.

```latex
\documentclass{article}

\begin{document}

``This is a double-quoted sentence.''

`This is a single-quoted sentence.'

"This is incorrect." % Avoid using the standard double-quote key

\end{document}
```

---

## Grouping

Curly braces `{...}` groups text and limits the scope of commands applied within them.

```latex
\documentclass{article}

\begin{document}

This is normal sized text.
{\large This text is large.}
This text is back to the normal size.

\end{document}
```

---

## Verbatim

To display text exactly as typed, use verbatim tools. 

- `\begin{verbatim}`: An environment that outputs all enclosed content literally.

- `\verb|text|`: An inline command for literal text.

```latex
\documentclass{article}

\begin{document}

\begin{verbatim}
This is raw text # $ % &
\end{verbatim}

\verb|This is also raw text # $ % &|

\end{document}
```
