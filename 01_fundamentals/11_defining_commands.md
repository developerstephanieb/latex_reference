# 11: Defining Commands

This guide covers how to create your own custom commands and modify existing ones. 

---

## Creating New Commands

The `\newcommand` command defines a custom command as a shortcut for a longer piece of code or text.

- `\newcommand{\name}{definition}`: Creates a new command called `\name`. When `\name` is used, LaTeX will replace it with the definition. The command name must start with a backslash (`\`) and must not already be defined.

```latex
\documentclass{article}

% Define a new command \lr for "LaTeX Reference" in the preamble
\newcommand{\lr}{LaTeX Reference}

\begin{document}

Welcome to the \lr{} guide!

\end{document}
```

---

## Commands with Arguments

Custom commands can also accept arguments for dynamic output.

- `\newcommand{\name}[num]{definition}`: Creates a new command that accepts `num` arguments. Inside the definition, refer to the arguments using `#1`, `#2`, and so on.

```latex
\documentclass{article}

% Define \highlight to take one argument (#1)
\newcommand{\highlight}[1]{\textbf{\textit{#1}}}

% Define \defineterm to take two arguments
% #1 will be the term (bold), #2 will be the definition (italic)
\newcommand{\defineterm}[2]{\noindent\textbf{#1}: \textit{#2}\\}

\begin{document}

This is normal text, but we want to \highlight{emphasize this part}.

\defineterm{Syntax}{The fundamental rules of a language.}

\end{document}
```

---

## Modifying Existing Commands

The `\renewcommand` command modifies the behavior of an existing command. It enables customization of default behaviors, but should be used with caution, as redefining core commands can have unintended consequences.

- `\renewcommand{\name}{new_definition}`: Redefines the existing command `\name` to have a `new_definition`.

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
