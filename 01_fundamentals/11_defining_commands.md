# 11: Defining Commands

This guide covers how to create custom commands and modify existing ones. 

---

## Creating New Commands

The `\newcommand` command defines a custom shortcut for a longer piece of code or text.

- `\newcommand{\name}[num]{definition}`: Creates a new command called `\name` that can accept `num` arguments. Inside the definition, refer to the arguments using `#1`, `#2`, and so on. The name must begin with `\` and not already exist.

```latex
\documentclass{article}

% Define a new command
\newcommand{\lr}{LaTeX Reference}

% Define \defineterm to take two arguments
% #1 will be the term (bold), #2 will be the definition (italic)
\newcommand{\defineterm}[2]{\noindent\textbf{#1}: \textit{#2}\\}

\begin{document}

Welcome to the \lr{} guide!

\defineterm{Syntax}{The fundamental rules of a language.}

\end{document}
```

---

## Modifying Existing Commands

The `\renewcommand` command modifies the behavior of an existing command. It enables customization of default behaviors, but should be used with caution, as redefining core commands can have unintended consequences.

- `\renewcommand{\name}[num]{new_definition}`: Redefines the existing command `\name` to have a `new_definition`.

```latex
\documentclass{article}

% Redefine the label for the first-level enumerate environment
% \theenumi is a counter that stores the current item number
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

The `\newenvironment` command defines a new custom environment.

- `\newenvironment{name}[num]{before}{after}`: Creates a new environment called `name` that can accept `num` arguments, executing `{before}` at `\begin{name}` and `{after}` at `\end{name}`.

```latex
\documentclass{article}
\usepackage{xcolor} % For text color

% Define a new 'warning' environment
\newenvironment{warning}
  {\begin{quote}\color{red}\bfseries Warning: } % Code to execute at the beginning
  {\end{quote}} % Code to execute at the end

\begin{document}

\begin{warning}
    This is an warning.
\end{warning}

\end{document}
```

---

## Modifying Existing Environments

The `\renewenvironment` command modifies an existing environment.

- `\renewenvironment{name}[num]{before}{after}`: Redefines the existing environment name.

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
