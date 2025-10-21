# 03: Text Format and Layout

LaTeX provides a comprehensive set of tools for controlling the appearance of text, from the style of individual words to the layout and spacing of entire paragraphs.

---

## Global Settings

A document's foundational style is set in the preamble, establishing the default look for all text in the document.

- `\documentclass[<options>]{<class>}`: Sets base font size, paper size, and default font family.

  | `options`                | Description                                                |
  | ------------------------ | ---------------------------------------------------------- |
  | `10pt`, `11pt`, `12pt`   | Sets the base font size for the document.                  |
  | `a4paper`, `letterpaper` | Sets the paper size.                                       |
  | `landscape`              | Sets the page orientation to landscape.                    |
  | `oneside`, `twoside`     | Sets the layout for single-sided or double-sided printing. |
  | `twocolumn`              | Typesets the document in two columns.                      |

- `\renewcommand{\familydefault}{<family_code>}`: Sets the default font family.

  | `family_code` | Description                               |
  | ------------- | ----------------------------------------- |
  | `\rmdefault`  | Sets the default to Roman (serif).        |
  | `\sfdefault`  | Sets the default to Sans-serif.           |
  | `\ttdefault`  | Sets the default to Monospace (Teletype). |

```latex
\documentclass[12pt]{article}
\renewcommand{\familydefault}{\sfdefault}

\begin{document}

This text will be 12pt and sans-serif by default.

\end{document}
```

---

## Font Appearance

In contrast to the global defaults, these font styles apply locally. They are implemented either as a command that takes text as an argument or as a **declaration** that switches the style for all subsequent text within its scope.

- `\textbf{<text>}`, `\bfseries`: Makes text bold.

- `\textit{<text>}`, `\itshape`: Makes text italic.

- `\underline{<text>}`: Underlines text.

- `\textrm{<text>}`, `\rmfamily`: Switches to the Roman (serif) family.

- `\textsf{<text>}`, `\sffamily`: Switches to the Sans-serif family.

- `\texttt{<text>}`, `\ttfamily`: Switches to the Teletype (monospace) family.

- `\tiny`, `\scriptsize`, `\footnotesize`, `\small`, `\normalsize`, `\large`, `\Large`, `\LARGE`, `\huge`, `\Huge`: Declarations that change the text size relative to the document's base font. They range from `\tiny` (smallest) to `\Huge` (largest).

```latex
\documentclass{article}

\begin{document}

\textbf{This text is bold.}

You can also \textbf{\textit{nest them}}.

{
\sffamily\large
This entire sentence is large and sans-serif.
The \texttt{monospace} font is great for code.
}

This text is back to the document default.

\end{document}
```

---

## Paragraph and Block Layout

There are several environments for controlling the alignment and formatting of entire blocks of text, such as paragraphs, quotes, and poetry.

- `center` **environment**, `\centering`: Centers text.
  
- `flushleft` **environment**, `\raggedright`: Aligns text to the left.
  
- `flushright` **environment**, `\raggedleft`: Aligns text to the right.

- `quote` **environment**: For short quotes, single-paragraph quotes.

- `quotation` **environment**: For longer quotations spanning multiple paragraphs.

- `verse` **environment**: For poetry, where line breaks are made with `\\` and stanzas are separated by a blank line.

```latex
\documentclass{article}

\begin{document}

\begin{center}
    This text is centered.
\end{center}

\begin{verse}
  Roses are red, \\
  Violets are blue.
\end{verse}

\end{document}
```

---

## Line Spacing (the `setspace` package)

The vertical distance between lines within a block of text can be adjusted using the `setspace` package.

- `setspace` **package**: Provides tools to control the spacing between lines.

   | `options`        | Description                  |
   | ---------------- | ---------------------------- |
   | `singlespacing`  | Sets single line spacing.    |
   | `onehalfspacing` | Sets one-and-a-half spacing. |
   | `doublespacing`  | Sets double line spacing.    |

- `\setstretch{<factor>}`: Sets a custom line spacing for the entire document.

- `\begin{spacing}{<factor>}`: Applies a custom spacing factor to a specific block of text.

- `\singlespacing`, `\onehalfspacing`, `\doublespacing`: Change the line spacing for all subsequent paragraphs in the document body.

```latex
\documentclass{article}
\usepackage[onehalfspacing]{setspace} % Load the 'setspace' package
\usepackage{lipsum}                   % For dummy text

\begin{document}

\section*{Global Spacing}
\lipsum[1] % This will have 1.25 spacing.

\begin{spacing}{2}
\lipsum[2] % This will be double-spaced.
\end{spacing}

\end{document}
```

---

## Paragraph Spacing (the `parskip` package)

By default, paragraphs are separated with a first-line indent. To switch to a "block" style where paragraphs are separated by vertical space instead, use the `parskip` package. This is preferred over manual adjustments since it automatically manages spacing in other environments, such as lists.

- `parskip` **package**: Switches the paragraph indent to zero and add a vertical space between paragraphs.

  | `options`         | Description                                                                 |
  | ----------------- | --------------------------------------------------------------------------- |
  | `skip=<length>`   | Sets the vertical space between paragraphs to a specified length.           |
  | `indent=<length>` | Sets the paragraph indentation to a specific length instead of removing it. |

```latex
\documentclass{article}
\usepackage[skip=10pt]{parskip} % Load the 'parskip' package
\usepackage{lipsum}             % For dummy text

\begin{document}

\lipsum[1]

\lipsum[2]

\end{document}
```

---

## Special Characters and Symbols

The following commands produce commonly used text symbols.

|     Symbol      | Name                     | Command         |
| :-------------: | ------------------------ | --------------- |
|      $\S$       | Section sign             | `\S`            |
|      $\P$       | Paragraph sign (pilcrow) | `\P`            |
|  $\copyright$   | Copyright sign           | `\copyright`    |
|     $\dag$      | Dagger                   | `\dag`          |
|     $\ddag$     | Double dagger            | `\ddag`         |
|    $\pounds$    | Pounds sterling sign     | `\pounds`       |
| $\textellipsis$ | Ellipsis                 | `\textellipsis` |

```latex
\documentclass{article}

\begin{document}

As stated in \S 5 of the document, the results were conclusive.

The paragraph ends here \P. A dagger can be used for footnotes\dag.

This work is \copyright 2025.

\end{document}
```
