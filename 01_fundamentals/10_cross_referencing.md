# 10: Cross-Referencing

This guide covers LaTeX's cross-referencing system, which creates dynamic links to sections, figures, tables, and equations.

---

## Core Commands

Cross-referencing relies on `\label` to create a marker, and `\ref` or `\pageref` to refer to that marker.

- `\label{marker}`: Assigns a unique `marker` to an element. The `\label` command should be placed immediately after the item it is marking (e.g., after `\caption` or `\section`).

- `\ref{marker}`: Prints the number of the element associated with `marker` (e.g., "3.2", "Figure 1", or "(5)")

- `\pageref{marker}`: Prints the page number where the marker is located.

- `~` (Tilde): Use a non-breaking space (`~`) before a reference to prevent an awkward line break between the text and the number (e.g., `Figure~\ref{fig:my_figure}`).

```latex
\documentclass{article}
\usepackage{graphicx}

\begin{document}

\section{Introduction}
\label{sec:intro}

This is the introduction. Later, we will see a sample figure on page~\pageref{fig:sample}.

\section{Main Content}

As we discussed in Section~\ref{sec:intro}, LaTeX's referencing system is very powerful.
It allows us to refer to figures, like Figure~\ref{fig:sample}, and equations, like Equation~\ref{eq:euler}.

\begin{figure}[h!]
  \centering
  \includegraphics[width=0.5\textwidth]{example-image}
  \caption{A sample image.}
  \label{fig:sample}
\end{figure}

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

```latex
\documentclass{article}
\usepackage{graphicx}
\usepackage{hyperref} % Load the 'hyperref' package

\begin{document}

\section{Introduction}
\label{sec:intro}

This is the introduction. See \autoref{sec:main} for the main content.
The table of contents below will also be hyperlinked.

\tableofcontents

\section{Main Content}
\label{sec:main}

As we discussed in the \autoref{sec:intro}, the links are now active.
You can find more at \url{https://www.latex-project.org/}.

\end{document}
```
