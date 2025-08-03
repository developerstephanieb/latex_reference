# LaTeX Basics

This guide provides an overview of the basic LaTeX syntax needed to write and compile documents.  

---

## Comments

Everything after `%` on the line is ignored.

```latex
% This is a comment
```

---

## Commands and the Document Class

Commands control formatting and behavior. Every LaTeX document begins with the `\documentclass` command.

- **Command**: An instruction that begins with a backslash (`\`). Commands are case-sensitive and may take mandatory arguments in curly braces `{}` or optional arguments in square brackets `[]`.

- `\documentclass[options]{class}`: A command that specifies the type of document to be created.   

  | Class     | Purpose                             |
  | --------- | ----------------------------------- |
  | `article` | For short documents.                |
  | `report`  | For longer documents with chapters. |
  | `book`    | For books.                          |
  | `letter`  | For writing letters.                |

  | Options                  | Description                                        |
  | ------------------------ | -------------------------------------------------- |
  | `10pt`, `11pt`, `12pt`   | Sets the base font size for the document.          |
  | `a4paper`, `letterpaper` | Sets the paper size.                               |
  | `oneside`, `twoside`     | Formats for single-sided or double-sided printing. |
  | `landscape`              | Sets the page orientation to landscape.            |

```latex
% Creates an article with a base font size of 11pt on US letter paper.
\documentclass[11pt, letterpaper]{article}

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

% All visible content goes inside the document environment.
\begin{document}

Content goes here.

\end{document}
```

---

## Whitespace Rules

LaTeX handles whitespace according to specific rules.

- **Spaces and Tabs**: Consecutive spaces or tabs are treated as one.

- **Line Breaks**: A single line break is also treated as a space.

- **Blank Lines**: One or more blank lines signal the end of a paragraph and the start of a new one.

Commands also control spacing and breaks.

- `\\` or `\newline`: Forces a line break.

- `\newpage`: Forces a page break.

- `~`: Inserts a non-breaking space, ensuring that the words it connects are not separated by a line break.

- `\par`: Ends the current paragraph and starts a new one.

- `\noindent`: Prevents indentation at the start of a paragraph.

- `\hspace{length}`: Inserts horizontal space.

- `\vspace{length}`: Inserts vertical space.
  
  | Unit  | Meaning                       |
  | :---: | ----------------------------- |
  |  pt   | Point (1/72 inch)             |
  |  mm   | Millimeter                    |
  |  cm   | Centimeter                    |
  |  in   | Inch                          |
  |  em   | Width of 'M' in current font  |
  |  ex   | Height of 'x' in current font |

```latex
\documentclass{article}
\begin{document}

Multiple   spaces are treated as one.
A single
line break is also just a space.

This text starts a new paragraph because there was a blank line above it.

\noindent This paragraph starts without indentation.

\par
This paragraph was separated using \verb|\par|.

You can force a line break\\without starting a new paragraph.

The text in Section~5 will always stay together.

\hspace{2em}This line begins with extra horizontal space.

\vspace{1em}

This line follows vertical space.

\newpage
This text will start on the second page.

\end{document}
```

---

## Escaping Special Characters

To print special characters, escape them with a backslash (`\`).

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

## Grouping

Curly braces `{...}` groups text and limits the scope of commands.

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
\begin{verbatim}
This is raw text # $ % &
\end{verbatim}

\verb|This is also raw text # $ % &|
```
