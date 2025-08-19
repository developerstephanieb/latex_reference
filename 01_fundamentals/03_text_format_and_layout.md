# 03: Text Format and Layout

This guide covers the essential LaTeX commands for formatting text, from changing the style of individual words to controlling the layout of entire blocks.

---

## Font Styles

There are two primary ways to apply font styles: as a command that takes an argument, or as a declaration that switches the style on for all subsequent text within its scope.

- **Argument Form**: Applies a style to a specific piece of text. 

- **Declaration Form**: Applies a style to all following text inside a group `{}` or an environment.

- `\textbf{text}`, `\bfseries`: Makes text bold.

- `\textit{text}`, `\itshape`: Makes text italic.

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

- `\textrm{text}`, `\rmfamily`: Switches to the Roman (serif) family, which is the default.

- `\textsf{text}`, `\sffamily`: Switches to the Sans-serif family.

- `\texttt{text}`, `\ttfamily`: Switches to the Teletype (monospace) family.

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

- `\usepackage{setspace}`: Loads the `setspace` package, enabling declarations for common spacing presets and an environment for custom spacing.

- `\setstretch{factor}`: Sets a custom line spacing for the entire document.

- `\begin{spacing}{factor}`: An environment that applies a custom spacing factor to a specific block of text.

- `\singlespacing`, `\onehalfspacing`, `\doublespacing`: Declarations that change the line spacing for all subsequent paragraphs in the document body.

```latex
\documentclass{article}
\usepackage{setspace} % Load the 'setspace' package
\usepackage{lipsum}   % For dummy text

\setstretch{1.25}

\begin{document}

\section*{Global Spacing}
\lipsum[1] % This will have 1.25 spacing.

\section*{Local Spacing}
\doublespacing
\lipsum[2] % This will be double-spaced.

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

- `\documentclass[options]{class}`: Sets the default font size. Common size [options] are `10pt`, `11pt`, and `12pt`.

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
