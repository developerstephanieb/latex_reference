# 03: Text Format and Layout

This guide covers the essential LaTeX commands for formatting text, from changing the style of individual words to controlling the layout of entire blocks.

---

## Font Styles

These commands change the appearance of text to add emphasis and can be nested inside each other.

- `\textbf{text}`: Makes text bold.

- `\textit{text}`: Makes text italic.

- `\underline{text}`: Underlines text.

```latex
\documentclass{article}

\begin{document}

\textbf{This text is bold.}
\textit{This text is italic.}
\underline{This text is underlined.}

You can also \textbf{\textit{nest them}}.

\end{document}
```

---

## Font Sizing

These commands change the size of text relative to the document’s base font size. Wrap them in braces `{...}` to limit their scope.

- `\tiny`: Smallest available text size.

- `\scriptsize`: Smaller than footnotes; often used for subscripts or annotations.

- `\footnotesize`: Standard size for footnotes.

- `\small`: Slightly smaller than the default.

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

- `\textrm{text}`: Switches to the Roman (serif) family, which is the default.

- `\textsf{text}`: Switches to the Sans-serif family.

- `\texttt{text}`: Switches to the Teletype (monospace) family.

```latex
\documentclass{article}

\begin{document}

\textrm{This is the default Roman (serif) font.}

\textsf{This is a sans-serif font.}

\texttt{This is a teletype (monospace) font, often used for code.}

\end{document}
```

---

## Alignment

These environments control the horizontal alignment of entire blocks of text.

- `\begin{center}`: Centers each line of text.
  
- `\begin{flushleft}`: Aligns text to the left margin.
  
- `\begin{flushright}`: Aligns text to the right margin.

```latex
\documentclass{article}

\begin{document}

\begin{center}
This text is centered.
\end{center}

\begin{flushright}
This text is aligned to the right.
\end{flushright}

\end{document}
```

---

## Blockquotes

These environments are used for block quotes, which are indented from both margins.

- `\begin{quote}`: Used for short quotes.

- `\begin{quotation}`: Used for longer quotes (more than one paragraph), with slightly more indentation.

```latex
\documentclass{article}

\begin{document}

Here is some introductory text for a quote.
\begin{quote}
This is a short quotation, indented from both margins.
\end{quote}

\end{document}
```

---

## Minipage

The `minipage` environment creates a small, self-contained "page" within the document. Its primary use is to place several blocks of content (text, images, tables) side-by-side.

- `\begin{minipage}[pos]{width}`: Creates an inline block of a specified `width` (see [04_lengths_and_dimensions.md](04_lengths_and_dimensions.md) for valid units). The optional `[pos]` argument controls the vertical alignment.

  | `pos` | Description                                                      |
  | :---: | ---------------------------------------------------------------- |
  |  `t`  | **t**op: Aligns the top of the minipage with the baseline.       |
  |  `c`  | **c**enter: Vertically centers the minipage (default).           |
  |  `b`  | **b**ottom: Aligns the bottom of the minipage with the baseline. |

```latex
\documentclass{article}

\begin{document}

\noindent % Prevents indentation for the minipages
\begin{minipage}[t]{0.45\textwidth} % Note the [t] for top alignment
  \textbf{Column 1:} This is the first block of text. It is contained within its own minipage. The content here is longer to show the top alignment.
\end{minipage}
\hfill % Adds flexible space to push the columns apart
\begin{minipage}[t]{0.45\textwidth} % Note the [t] for top alignment
  \textbf{Column 2:} This is the second block of text.
\end{minipage}

\end{document}
```

---

## Global Font Settings

Global font settings can be defined in the preamble to set defaults for the entire document.

- `\documentclass[options]{class}`: Sets the default font size. Common size options are `10pt`, `11pt`, and `12pt`.

- `\renewcommand{\familydefault}{family_code}`: Sets the default font family.

  | `family_code` | Description                               |
  | ------------- | ----------------------------------------- |
  | `\rmdefault`  | Sets the default to Roman (serif).        |
  | `\sfdefault`  | Sets the default to Sans-serif.           |
  | `\ttdefault`  | Sets the default to Monospace (Teletype). |

```latex
% Preamble settings
\documentclass[12pt]{article} % Set base font size to 12pt
\renewcommand{\familydefault}{\sfdefault} % Set default font to sans-serif

\begin{document}

This entire document now uses a 12pt sans-serif font as its default.

\end{document}
```
