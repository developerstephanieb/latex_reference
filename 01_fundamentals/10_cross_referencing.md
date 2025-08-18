# 10: Cross-Referencing

This guide covers LaTeX's cross-referencing system, which creates dynamic links to sections, figures, tables, and equations.

---

## Core Commands

Cross-referencing relies on `\label` to create a marker, and `\ref` or `\pageref` to refer to that marker.

- `\label{marker}`: Assigns a unique `marker` to an element. The `\label` command should be placed immediately after the item it is marking (e.g., after `\caption` or `\section`). It is best practice to use prefixes to identify the type of element being labeled.
  | Prefix | Element Type | Example                    |
  | ------ | ------------ | -------------------------- |
  | `sec:` | Section      | `\label{sec:introduction}` |
  | `fig:` | Figure       | `\label{fig:flowchart}`    |
  | `tab:` | Table        | `\label{tab:results}`      |
  | `eq:`  | Equation     | `\label{eq:euler}`         |

- `\ref{marker}`: Prints the number of the element associated with `marker` (e.g., "3.2", "1", or "(5)")

- `\pageref{marker}`: Prints the page number where the marker is located.

- `~` (Tilde): Use a non-breaking space (`~`) before a reference to prevent a line break between the text and the number (e.g., `Figure~\ref{fig:my_figure}`).

```latex
\documentclass{article}

\begin{document}

\section{Introduction}
\label{sec:intro}

This is the introduction.

\section{Main Content}

As discussed in Section~\ref{sec:intro}, LaTeX's referencing system allows referencing to equations like Equation~\ref{eq:euler}.

\begin{equation}
    e^{i\pi} + 1 = 0
    \label{eq:euler}
\end{equation}

\end{document}
```

---

## The "Compile Twice" Rule

For references to resolve correctly, LaTeX requires compiling the document at least twice. If any labels are added, removed, or reordered, the document must be compiled twice more for the changes to be reflected.

1. **First Compilation**: LaTeX reads the document and stores all the `\label` markers and their corresponding numbers in an auxiliary (`.aux`) file. At this stage, any `\ref` commands will appear as question marks (`??`) in the output because the references have not yet been resolved.

2. **Second Compilation**: LaTeX reads the `.aux` file and replaces each `\ref` and `\pageref` with the correct value.

---

## The `hyperref` Package

Use the `hyperref` package for clickable references and automatic labels.

- `\usepackage{hyperref}`: Loads the `hyperref` package, making all references clickable hyperlinks in the PDF output.
  
- `\autoref{marker}`: Automatically creates a complete reference, including the name (e.g., "Figure 2", "Section 4.1", "Equation (3)"), all as a single hyperlink.

- `\url{address}`: A command for typesetting URLs, which will also be made clickable.

- `\href{address}{text}`: Creates a hyperlink where the `text` is the clickable part that points to the specified `address`.

```latex
\documentclass{article}
\usepackage{hyperref} % Load the 'hyperref' package

\begin{document}

\section{Introduction}
\label{sec:intro}

This is the introduction. See \autoref{sec:main} for the main content.
The table of contents below will also be hyperlinked.

\tableofcontents

\section{Main Content}
\label{sec:main}

As discussed in the \autoref{sec:intro}, the links are now active.
You can visit the \href{https://www.latex-project.org/}{LaTeX Project website} 
for details.

\end{document}
```

---

## The `cleveref` Package

The standard workflow is to use both `hyperref` and `cleveref` together.

- `\usepackage{cleveref}`: Loads the `cleveref` package, which automatically determines the reference type and can intelligently handle multiple references at once. 

- `\cref{marker1, marker2, ...}`: Automatically produces the correct label name (e.g., "figure", "section", "equation") and number. The capitalized version `\Cref` capitalizes the label name.

```latex
\documentclass{article}
\usepackage{hyperref}
\usepackage{cleveref} % Load 'cleveref' after 'hyperref'

\begin{document}

\section{Introduction}
\label{sec:intro}

This is the introduction. See \cref{sec:main} for more details.
We will also look at \cref{eq:euler,eq:pythagorean}.

\section{Main Content}
\label{sec:main}

Here are two important equations:
\begin{equation}
    e^{i\pi} + 1 = 0
    \label{eq:euler}
\end{equation}

\begin{equation}
    a^2 + b^2 = c^2
    \label{eq:pythagorean}
\end{equation}

\end{document}
```
