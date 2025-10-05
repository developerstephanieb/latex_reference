# 11: Defining Commands

This guide covers how to create custom commands and modify existing ones. 

---

## Creating New Commands

Use `\newcommand` or `\providecommand` to define a custom shortcut for a longer piece of code or text.

- `\newcommand{\<name>}[<num>]{<definition>}`: Creates a new command that must not already exist. It can accept `num` arguments, which can then be referred to in the definition as `#1`, `#2`, and so on.

- `\providecommand{\<name>}[<num>]{<definition>}`: A "safe" version that defines a command only if it doesn't already exist. 

```latex
\documentclass{article}

% Define \defineterm to take two arguments
% #1 will be the term (bold), #2 will be the definition (italic)
\newcommand{\defineterm}[2]{\noindent\textbf{#1}: \textit{#2}\\}

% This command will be created because it doesn't exist
\newcommand{\lr}{LaTeX Reference}

% This command will do nothing because \section already exists
\providecommand{\section}{...}

\begin{document}

Welcome to the \lr{} guide!

\defineterm{Syntax}{The fundamental rules of a language.}

\end{document}
```

---

## Modifying Commands

While `\newcommand` creates new commands, `\renewcommand` handles existing ones.

- `\renewcommand{\<cmd>}[<num>]{<new_definition>}`: Redefines an existing command. LaTeX will show an error if the command doesn't already exist.

```latex
\documentclass{article}

% Redefine the label for the first-level enumerate environment
\renewcommand{\labelenumi}{Step \theenumi:}

\begin{document}

\begin{enumerate}
    \item This is the first item.  % Will be labeled "Step 1:"
    \item This is the second item. % Will be labeled "Step 2:"
\end{enumerate}

\end{document}
```

---

## Creating New Environments

Use `\newenvironment` to define a new custom environment.

- `\newenvironment{<name>}[<num>]{<before>}{<after>}`: Creates a new environment that must not already exist. It executes `{<before>}` at `\begin{<name>}` and `{<after>}` at `\end{<name>}`.

```latex
\documentclass{article}
\usepackage{xcolor} % For text color

% Define a new 'warning' environment
\newenvironment{warning}
  {\begin{quote}\color{red}\bfseries Warning: } % Code to execute at the beginning
  {\end{quote}}                                 % Code to execute at the end

\begin{document}

\begin{warning}
    This is an warning.
\end{warning}

\end{document}
```

---

## Modifying Existing Environments

Just as `\renewcommand` alters commands, `\renewenvironment` changes how existing environments work.

- `\renewenvironment{<name>}[<num>]{<before>}{<after>}`: Redefines an existing environment. LaTeX will show an error if the environment doesn't already exist.

```latex
\documentclass{article}

% Redefine the 'quote' environment to center the text and make it italic.
\renewenvironment{quote}
  {\begin{center}\itshape}  % At the beginning, start centering and turn on italics.
  {\end{center}}            % At the end, stop centering.

\begin{document}

Here is some introductory text.
\begin{quote}
    This quoted text will now be centered and italic because the
    environment was redefined.
\end{quote}

\end{document}
```
