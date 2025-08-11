# 03: Text Format and Layout

This guide covers the essential LaTeX commands for formatting text, from changing the style of individual words to controlling the layout of entire blocks.

---

## Font Styles

There are two primary ways to apply font styles: as a command that takes an argument, or as a declaration that switches the style on for all subsequent text within its scope.

- **Argument Form**: Applies a style to a specific piece of text. This is best for short, local changes.

- **Declaration Form**: Acts as a switch. This is useful for styling larger blocks of text inside a group `{...}` or an environment.

- `\textbf{text}` and `\bfseries`: Makes text bold.

- `\textit{text}` and `\itshape`: Makes text italic.

- `\underline{text}`: Underlines text.

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

## Font Sizing

These declarations change the size of text relative to the document’s base font size. 

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

- `\textrm{text}` and `\rmfamily`: Switches to the Roman (serif) family, which is the default.

- `\textsf{text}` and `\sffamily`: Switches to the Sans-serif family.

- `\texttt{text}` and `\ttfamily`: Switches to the Teletype (monospace) family.

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

- `\begin{center}` and `\centering`: Centers each line of text.
  
- `\begin{flushleft}` and `\raggedright`: Aligns text to the left margin, which is the default.
  
- `\begin{flushright}` and `\raggedleft`: Aligns text to the right margin.

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

## Verses

The `verse` environment is specifically designed for poetry.

- `\begin{verse}`: Used for poetry where stanzas are separated by a blank line and line breaks are created with `\\`.

```latex
\begin{verse}
  Roses are red, \\
  Violets are blue.
\end{verse}
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
\documentclass[12pt]{article}
\renewcommand{\familydefault}{\sfdefault}

\begin{document}

This entire document now uses a 12pt sans-serif font as its default.

\end{document}
```
