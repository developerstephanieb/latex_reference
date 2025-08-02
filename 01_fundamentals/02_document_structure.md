# 02: Document Structure

This guide explains the fundamental structure of a LaTeX document, including its setup, content organization, and project structure.

---

## The Preamble and Body

A LaTeX document is divided into two main parts:

- **Preamble**: Everything before `\begin{document}`. It sets up the document by loading packages, defining metadata, and adjusting formatting.

- **Document Body**: Everything between `\begin{document}` and `\end{document}`. It encloses the content to be typeset.

```latex
% ----- Preamble -----
\documentclass{article}

\begin{document}
% ----- Document Body -----

Content goes here.

\end{document}
```

---

## Metadata

These commands define metadata in the preamble, which `\maketitle` then renders in the document body.

- `\title{text}`: Stores the document's title.

- `\author{text}`: Stores the author's name(s).

- `\date{text}`: Stores a specific date. Use `\today` to dynamically inserts the current date.
 
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
- `\subsection{title}`: Creates a subsection within a section.
- `\subsubsection{title}`: Creates a sub-subsection.
- `\paragraph{title}`: Creates a paragraph heading in-line with the text that follows it. Bolded and unnumbered by default.
- `\subparagraph{title}`: Creates the lowest-level inline heading, also unnumbered.

```latex
\documentclass{article}

\begin{document}

\section{Introduction}  % Top-level section
This is the first main section. It is numbered automatically (e.g., 1).

\subsection{Background}  % Subsection within Introduction
A subsection (e.g., 1.1).

\subsubsection{Historical Context}  % Sub-subsection within Background
A sub-subsection (e.g., 1.1.1).

\paragraph{Key Figures}  % Titled paragraph; inline heading
Text begins on the same line as the title. Typically bolded and not numbered.

\subparagraph{Secondary Contributors}  % Finer inline heading
Nested under the paragraph heading. Also not numbered.

\section*{Acknowledgments}  % Unnumbered section
This section is not numbered because of the asterisk.

\end{document}
```

---

## Table of Contents

The table of contents is dynamically generated and updates with each compile.

- `\tableofcontents`: Inserts a table of contents at that spot, automatically populated from the sectioning commands.

```latex
\documentclass{article}

\begin{document}

\tableofcontents  % Generates the ToC

\section{Main Body}
This section will appear in the ToC.

\subsection{First Point}
A subsection, indented under "Main Body" in the ToC.

\section*{Acknowledgments}  % Unnumbered; not listed in the ToC
This section is not numbered and will not appear in the ToC.

\end{document}
```

---

## Including External Files

For large projects, the document can be split into multiple `.tex` files.

- `\input{filename}`: Directly inserts the content of `filename.tex`. The included file should not have its own preamble or document environment.

- `\include{filename}`: Inserts content of `filename.tex` on a new page, typically for major sections like chapters. To specify which of the `\include` files to compile, use `\includeonly{file1, ...}` in the preamble.

```latex
\documentclass{report}

\title{Analysis of Everything}
\author{The Author}

% Command to only compile specific \include'd files
\includeonly{chapter1}

\begin{document}
\maketitle

\input{introduction} % Inserts introduction.tex here.

\include{chapter1}   % Inserts chapter1.tex on a new page.
\include{chapter2}   % Skipped because it's not listed in \includeonly.

\end{document}
```
