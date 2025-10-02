# 03: Text Format and Layout

This guide covers the essential LaTeX commands for formatting text, from changing the style of individual words to controlling the layout of entire blocks.

---

## Font Styles

There are two primary ways to apply font styles: as a command that takes an argument, or as a declaration that switches the style for all subsequent text within its scope.

- **Argument Form**: Applies a style to a specific piece of text. 

- **Declaration Form**: Applies a style to all following text inside a group `{}` or an environment.

- `\textbf{<text>}`, `\bfseries`: Makes text bold.

- `\textit{<text>}`, `\itshape`: Makes text italic.

- `\underline{<text>}`: Underlines text.

```latex
\documentclass{article}

\begin{document}

\textbf{This text is bold.}

{\itshape This entire sentence is in italics.}

\underline{This text is underlined.}

You can also \textbf{\textit{nest them}}.

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

---

## Font Sizing

These declarations change the size of text relative to the document’s base font size. 

- `\tiny`: Smallest available text size.

- `\scriptsize`: Smaller than footnotes; often used for subscripts or annotations.

- `\footnotesize`: Standard size for footnotes.

- `\small`: Slightly smaller than the default.

- `\normalsize`: Default document font size.

- `\large`, `\Large`, `\LARGE`: Progressively larger sizes above the default.

- `\huge`, `\Huge`: Very large and largest text sizes, respectively.

```latex
\documentclass{article}

\begin{document}

{\small This is smaller than the default.}

This is the normal, default text size.

{\Large This is larger than the default.}

{\Huge This is one of the largest sizes available.}

\end{document}
```

---

## Font Families

These commands switch between the three main font families available in LaTeX.

- `\textrm{<text>}`, `\rmfamily`: Switches to the Roman (serif) family, which is the default.

- `\textsf{<text>}`, `\sffamily`: Switches to the Sans-serif family.

- `\texttt{<text>}`, `\ttfamily`: Switches to the Teletype (monospace) family.

```latex
\documentclass{article}

\begin{document}

\textrm{This is the default Roman (serif) font.}

{\sffamily This entire paragraph is in sans-serif font.}

\texttt{This is a teletype (monospace) font, often used for code.}

\end{document}
```

---

## Alignment

These environments and declarations control the horizontal alignment of entire blocks of text.

- `\begin{center}`, `\centering`: Centers each line of text.
  
- `\begin{flushleft}`, `\raggedright`: Aligns text to the left margin, which is the default.
  
- `\begin{flushright}`, `\raggedleft`: Aligns text to the right margin.

```latex
\documentclass{article}

\begin{document}

\begin{center}
    This text is centered.
\end{center}

{
\raggedleft
This text is aligned to the right.\\
Every line is right-aligned.\par  % <-- paragraph terminator is required
}

\end{document}
```

---

## Line Spacing

Use the `setspace` package to control the spacing between lines in a paragraph.

- `\usepackage[<spacing>]{setspace}`: Loads the `setspace` package, enabling declarations for common spacing presets and an environment for custom spacing.

   | `spacing`        | Description                  |
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

## Paragraph Indent and Spacing

By default, paragraphs are separated with a first-line indent. The `parskip` package creates a "block" style in which paragraphs are separated by space instead of an indent. This is preferred over manual adjustments since it automatically handles spacing in other environments, like lists.

- `\usepackage[<options>]{parskip}`: Load the `parskip` package to set the paragraph indent to zero and add a vertical space between paragraphs.

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

## Blockquotes and Verses

These environments are for formatting blocks of quoted prose or poetry and are indented from both margins.

- `\begin{quote}`: Used for short quotes.

- `\begin{quotation}`: Used for longer quotes (more than one paragraph), with slightly more indentation.

- `\begin{verse}`: Used for poetry where stanzas are separated by a blank line and line breaks are created with `\\`.

```latex
\documentclass{article}

\begin{document}

\begin{quote}
This is a short quotation, indented from both margins.
\end{quote}

\begin{verse}
  Roses are red, \\
  Violets are blue.
\end{verse}

\end{document}
```

---

## Global Font Settings

Global font settings can be defined in the preamble to set defaults for the entire document.

- `\documentclass[<options>]{<class}>`: Sets the default font size. Common size `options` are `10pt`, `11pt`, and `12pt`.

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

This entire document now uses a 12pt sans-serif font as its default.

\end{document}
```
