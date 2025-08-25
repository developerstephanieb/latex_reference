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

Packages are external files that add new features and commands to LaTeX. They must be loaded in the preamble using the `\usepackage` command. The order in which packages are loaded can be important, as some packages depend on others.

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

% Define metadata in preamble
\title{A Study of Document Structure}
\author{A. N. Author}
\date{\today}

\begin{document}

% Typeset title in document body
\maketitle

\end{document}
```

---

## The `titling` Package

The `titling` package allows custom code to be inserted before and after the title, author, and date elements, providing full control over their formatting.

- `\usepackage{titling}`: Loads the `titling` package, enabling the customization commands for the title block.

- `\pretitle{text}`, `\posttitle{text}`: Code to be placed before and after the title.

- `\preauthor{text}`, `\postauthor{text}`: Code to be placed before and after the author.

- `\predate{text}`, `\postdate{text}`: Code to be placed before and after the date.

```latex
\documentclass{article}
\usepackage{titling} % Load the package

% Define the title, author, and date
\title{A Custom Title}
\author{A. N. Author}
\date{\today}

% Customize the layout of \maketitle
\pretitle{\begin{center}\LARGE\bfseries}
\posttitle{\end{center}\vspace{0.5em}}

\preauthor{\begin{center}\large}
\postauthor{\end{center}\vspace{0.5em}}

\predate{\begin{center}\large}
\postdate{\end{center}\hrule}

\begin{document}

% Now produces the custom title block
\maketitle

\section{Introduction}
The title block above has been redesigned using the
\texttt{titling} package. The elements have been
centered the elements, their font sizes changes,
and a horizontal rule was added after the date.

\end{document}
```

---

## Sectioning

These commands format and number section headings. To create an unnumbered heading, add an asterisk (`*`) after the command name.

- `\part`: Creates a new part, the highest-level division in a document.

- `\chapter{title}`: Starts a new chapter (in `report` and `book` classes).

- `\section{title}`: Creates a new top-level section.
  
- `\subsection{title}`: Creates a subsection.
  
- `\subsubsection{title}`: Creates a sub-subsection.
  
- `\paragraph{title}`: Creates a paragraph heading, displayed inline with the text that follows it. 
  
- `\subparagraph{title}`: Creates the lowest-level inline heading.

```latex
\documentclass{article}

\begin{document}

\part{Main Topics}

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

LaTeX controls which sectioning commands are numbered using the `secnumdepth` counter. In the `article` class, the default value is 3, meaning only sections up to `\subsubsection` are numbered. To include numbering for deeper levels, increase the value of `secnumdepth` in the preamble.

- `\setcounter{secnumdepth}{level}`: Sets the maximum depth of numbered sectioning.
  
  | `level` | Deepest Numbered Level |
  | :-----: | ---------------------- |
  |    0    | `\part`                |
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

- `\addcontentsline{type}{level}{title}`:  Manually adds an entry to a specified list. The `{type}` argument determines which list to use (`toc` for Table of Contents, `lof` for List of Figures, `lot` for List of Tables).

- `\setcounter{tocdepth}{level}`: Controls the depth of section levels shown in the TOC.

- `\listoffigures`: Generates a list of all figure captions.

- `\listoftables`: Generates a list of all table captions.

```latex
\documentclass{article}

\begin{document}

\tableofcontents % Generates the ToC
\listoffigures
\listoftables

\section{Main Body}
This section will appear in the ToC.

\subsection{First Point}
A subsection, indented under Main Body in the ToC.

\section*{Acknowledgments} % Unnumbered; not listed in the ToC by default
\addcontentsline{toc}{section}{Acknowledgments} % Manually add the entry to the ToC
This section is unnumbered but will now appear in the ToC.

\end{document}
```

---

## Appendix

The `\appendix` command is used to mark the beginning of the appendices in a document.

- `\appendix`: Marks the start of the appendices. After this, `\section` commands in the `article` class will produce headings like `A`, `B`, and so on.

```latex
\documentclass{article}

\begin{document}

\section{Main Content}
The core of the document goes here.

\appendix % Starts the appendix

\section{Supplemental Details}
This section appears as ``A''.

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
