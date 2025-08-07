# 02: Document Structure

This guide explains the fundamental structure of a LaTeX document, including its setup, content organization, and project structure.

---

## The Preamble and Body

A LaTeX document is divided into two main parts:

- **Preamble**: Everything before `\begin{document}`. It sets up the document by specifying the document class, loading packages, and defining metadata.

- **Document Body**: Everything between `\begin{document}` and `\end{document}`. It encloses all content to be typeset.

```latex
% ----- Preamble -----
\documentclass{article}

\begin{document}

% ----- Document Body -----
Content goes here.

\end{document}
```

---

## Loading Packages

Packages are external files that add new features and commands to LaTeX. They must be loaded in the preamble using the `\usepackage` command.

- `\usepackage[options]{package_name}`: Loads a package, with optional settings.

```latex
\documentclass{article}

\usepackage{amsmath}  % Load the 'amsmath' package in the preamble

\usepackage{graphicx} % Load the 'graphicx package in the preamble

\begin{document}
% The commands from amsmath and graphicx are now available.
\end{document}
```

---

## Metadata

These commands define metadata in the preamble, which `\maketitle` then renders in the document body.

- `\title{text}`: Stores the document's title.

- `\author{text}`: Stores the author's name(s).

- `\date{text}`: Stores a specific date. Use `\today` to dynamically insert the current date.
 
- `\maketitle`: Typesets the stored title, author, and date information. 

```latex
\documentclass{article}

% --- Define Metadata in Preamble ---
\title{A Study of Document Structure}
\author{A. N. Author}
\date{\today}

\begin{document}

% --- Typeset Title in Document Body ---
\maketitle

\end{document}
```

---

## Sectioning

These commands format and number section headings. To create an unnumbered heading, add an asterisk (`*`) after the command name.

- `\section{title}`: Creates a new top-level section.
  
- `\subsection{title}`: Creates a subsection.
  
- `\subsubsection{title}`: Creates a sub-subsection.
  
- `\paragraph{title}`: Creates a paragraph heading in-line with the text that follows it. 
  
- `\subparagraph{title}`: Creates the lowest-level inline heading.

```latex
\documentclass{article}

\begin{document}

\section{Introduction}
This is the first main section. It is numbered automatically (e.g., 1).

\subsection{Background}
A subsection (e.g., 1.1).

\subsubsection{Historical Context}
A sub-subsection (e.g., 1.1.1).

\paragraph{Key Figures}
Text begins on the same line as the title.

\subparagraph{Secondary Contributors}
Nested under the paragraph heading.

\section*{Acknowledgments}
This section is not numbered because of the asterisk.

\end{document}
```

---

## Customizing Numbering Depth

LaTeX controls which sectioning commands are numbered using the `secnumdepth` counter. In the `article` class, the default value is `3`, meaning only sections up to `\subsubsection` are numbered. To include numbering for `\paragraph` and `\subparagraph`, increase the value of `secnumdepth` in the preamble.

- `\setcounter{secnumdepth}{level}`: Sets the maximum depth of numbered sectioning.
  
  | `level` | Deepest Numbered Level |
  | :-----: | ---------------------- |
  |    1    | `\section`             |
  |    2    | `\subsection`          |
  |    3    | `\subsubsection`       |
  |    4    | `\paragraph`           |
  |    5    | `\subparagraph`        |

```latex
\documentclass{article}
\setcounter{secnumdepth}{5}

\begin{document}

Sections up to subparagraph are now numbered.

\end{document}
```

---

## Table of Contents

The table of contents updates automatically, but requires two compilations: first to gather headings, then to render the table.

- `\tableofcontents`: Directly inserts a table of contents, automatically populated from numbered sectioning commands.

```latex
\documentclass{article}

\begin{document}

\tableofcontents % Generates the ToC

\section{Main Body}
This section will appear in the ToC.

\subsection{First Point}
A subsection, indented under Main Body in the ToC.

\section*{Acknowledgments} % Unnumbered; not listed in the ToC
This section is unnumbered and will not appear in the ToC.

\end{document}
```

---

## Appendix

This commands changes how top-level sections are labeled.

- `\appendix`: Marks the start of the appendices. After this command, `\section` commands will produce headings like `Appendix A`, `Appendix B`, and so on.

```latex
\documentclass{article}

\begin{document}

\section{Main Content}
The core of the document goes here.

\appendix % Starts the appendix

\section{Supplemental Details}
This section appears as ``Appendix A''.

\end{document}
```

---

## Including External Files

For large projects, the content can be split into multiple `.tex` files. The external files should not contain their own preamble or document environment.

- `\input{filename}`: Directly inserts the content of `filename.tex`.

- `\include{filename}`: Inserts content of `filename.tex` on a new page, typically for major sections like chapters. To specify which of the `\include` files to compile, use `\includeonly{file1, ...}` in the preamble.

```latex
\documentclass{report}

% Command to only compile specific \include'd files
\includeonly{chapter1}

\begin{document}

\input{introduction} % Inserts introduction.tex here.
\include{chapter1}   % Inserts chapter1.tex on a new page.
\include{chapter2}   % Skipped because it's not listed in \includeonly.

\end{document}
```
