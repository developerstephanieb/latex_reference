# 09: Math Mode

This guide provides an overview of math mode, the specialized environment for typesetting mathematical formulas and equations.

---

## Entering Math Mode

LaTeX provides two primary modes for typesetting mathematics.

- **Inline Mode**: For formulas that appear within a line of text. Wrap the expression by opening and closing with a single dollar sign (`$...$`) or use `\(...\)`.

- **Display Mode**: For formulas that are set apart from the text on their own line and centered. Wrap the expression with `\[...\]`.

```latex
This equation is written inline: $E = mc^2$

This equation is written in display mode:
\[
    F = ma
\]
```

---

## Fundamental Constructs

Superscripts and subscripts containing more than one character must be grouped using curly braces `{}`.

| Name         | Command                         | Example Code    | Rendered Output |
| ------------ | ------------------------------- | --------------- | :-------------: |
| Superscripts | `^`                             | `$x^{10}$`      |    $x^{10}$     |
| Subscripts   | `_`                             | `$a_1$`         |      $a_1$      |
| Fractions    | `\frac{numerator}{denominator}` | `$\frac{1}{2}$` |  $\frac{1}{2}$  |
| Square roots | `\sqrt[n]{radicand}`            | `$\sqrt[3]{x}$` |  $\sqrt[3]{x}$  |

---

## Common Symbols

Math mode supports a wide range of symbols beyond standard letters and numbers, most requiring specific commands.

### General

|   Symbol    | Name               | Command     |
| :---------: | ------------------ | ----------- |
|  $\infty$   | Infinity           | `\infty`    |
| $\partial$  | Partial derivative | `\partial`  |
|  $^\circ$   | Degree             | `^\circ`    |
|  $\angle$   | Angle              | `\angle`    |
|   $\perp$   | Perpendicular      | `\perp`     |
| $\parallel$ | Parallel           | `\parallel` |

### Greek Letters

|       Symbol       | Name    | Command            |
| :----------------: | ------- | ------------------ |
|      $\alpha$      | alpha   | `\alpha`           |
|      $\beta$       | beta    | `\beta`            |
| $\gamma$, $\Gamma$ | gamma   | `\gamma`, `\Gamma` |
| $\delta$, $\Delta$ | delta   | `\delta`, `\Delta` |
|     $\epsilon$     | epsilon | `\epsilon`         |
| $\theta$, $\Theta$ | theta   | `\theta`, `\Theta` |
|      $\kappa$      | kappa   | `\kappa`           |
|     $\lambda$      | lambda  | `\lambda`          |
|       $\mu$        | mu      | `\mu`              |
|    $\pi$, $\Pi$    | pi      | `\pi`, `\Pi`       |
|       $\rho$       | rho     | `\rho`             |
| $\sigma$, $\Sigma$ | sigma   | `\sigma`, `\Sigma` |
|   $\phi$, $\Phi$   | phi     | `\phi`, `\Phi`     |
|       $\chi$       | chi     | `\chi`             |
| $\omega$, $\Omega$ | omega   | `\omega`, `\Omega` |

### Operators and Relations

|  Symbol   | Name                  | Command   |
| :-------: | --------------------- | --------- |
| $\times$  | Multiplication        | `\times`  |
|  $\div$   | Division              | `\div`    |
|   $\pm$   | Plus-minus            | `\pm`     |
|  $\cdot$  | Dot product           | `\cdot`   |
|  $\leq$   | Less than or equal    | `\leq`    |
|  $\geq$   | Greater than or equal | `\geq`    |
|  $\neq$   | Not equal             | `\neq`    |
| $\approx$ | Approximately         | `\approx` |
| $\equiv$  | Equivalent            | `\equiv`  |

### Functions

These commands typeset function names upright (roman) and with proper spacing, distinguishing them from variables.

|             Symbol              | Name                         | Command                         |
| :-----------------------------: | ---------------------------- | ------------------------------- |
|          $\log$, $\ln$          | Logarithm, natural logarithm | `\log`, `\ln`                   |
|     $\sin$, $\cos$, $\tan$      | Trig functions               | `\sin`, `\cos`, `\tan`          |
|             $\exp$              | Exponential                  | `\exp`                          |
| $\arcsin$, $\arccos$, $\arctan$ | Inverse trig functions       | `\arcsin`, `\arccos`, `\arctan` |
|    $\sinh$, $\cosh$, $\tanh$    | Hyperbolic                   | `\sinh`, `\cosh`, `\tanh`       |

### Calculus

| Name      | Command               | Example                  |    Rendered Output     |
| --------- | --------------------- | ------------------------ | :--------------------: |
| Integral  | `\int_{start}^{end}`  | `$\int_{0}^{1} x^2\,dx$` | $\int_{0}^{1} x^2\,dx$ |
| Summation | `\sum_{start}^{end}`  | `$\sum_{i=1}^{n} i$`     |   $\sum_{i=1}^{n} i$   |
| Product   | `\prod_{start}^{end}` | `$\prod_{i=1}^{n} i$`    |  $\prod_{i=1}^{n} i$   |
| Limit     | `\lim_{var \to val}`  | `$\lim_{x \to \infty}$`  | $\lim_{x \to \infty}$  |

### Set Theory

|         Symbol         | Name                          | Command                |
| :--------------------: | ----------------------------- | ---------------------- |
|    $\in$, $\notin$     | Element of, not an element of | `\in`, `\notin`        |
| $\subset$, $\subseteq$ | Proper subset, subset         | `\subset`, `\subseteq` |
| $\supset$, $\supseteq$ | Proper superset, superset     | `\supset`, `\supseteq` |
|     $\cup$, $\cap$     | Union, intersection           | `\cup`, `\cap`         |
|      $\emptyset$       | Empty set                     | `\emptyset`            |

### Logic Symbols

|      Symbol       | Name                 | Command           |
| :---------------: | -------------------- | ----------------- |
|      $\neg$       | Negation (not)       | `\neg`            |
|  $\land$, $\lor$  | And, or              | `\land`, `\lor`   |
|   $\rightarrow$   | Implies              | `\rightarrow`     |
| $\Leftrightarrow$ | If and only if (iff) | `\Leftrightarrow` |
|     $\forall$     | For all              | `\forall`         |
|     $\exists$     | There exists         | `\exists`         |

### Accents

|   Symbol    | Name         | Command     |
| :---------: | ------------ | ----------- |
|  $\hat{x}$  | Hat          | `\hat{x}`   |
|  $\bar{y}$  | Bar          | `\bar{y}`   |
| $\tilde{z}$ | Tilde        | `\tilde{z}` |
|  $\dot{t}$  | Dot          | `\dot{t}`   |
|  $\vec{v}$  | Vector arrow | `\vec{v}`   |


---

## The `equation` Environment

For numbered equations that can be referenced, use the `equation` environment.

- `\begin{equation}`: Begins a display math environment that will be automatically numbered.

- `\label{marker}`: Assigns a unique `marker` to the equation.

- `\ref{marker}`: Prints the equation number associated with `marker`.

```latex
\documentclass{article}

\begin{document}

As shown in Equation~\ref{eq:pythagorean}, the relationship is fundamental.

\begin{equation}
  a^2 + b^2 = c^2
  \label{eq:pythagorean}
\end{equation}

\end{document}
```

---

## The `amsmath` Package

For environments for multi-line equations and matrices, load the `amsmath` package in the preamble.

- `\usepackage{amsmath}`: Loads the `amsmath` package, enabling advanced mathematical typesetting.

- `\begin{align}`: For aligning multiple equations. The `&` character specifies the alignment point, typically the equals sign.

- **Matrix Environments**: `\begin{pmatrix}` for parentheses, `\begin{bmatrix}` for brackets, and `\begin{vmatrix}` for vertical bars.

- `\begin{cases}`: For defining piecewise functions.

- Additional commands:

  | Name               | Command                    | Example                        |      Rendered Output      |
  | ------------------ | -------------------------- | ------------------------------ | :-----------------------: |
  | text in math       | `\text{text}`              | `$\text{speed} = 30$`          |    $\text{speed} = 30$    |
  | box around content | `\boxed{text}`             | `$\boxed{E=mc^2}$`             |     $\boxed{E=mc^2}$      |
  | dots               | `\dots`,`\cdots`, `\vdots` | `$\dots`,`$\cdots`, `$\vdots$` | $\dots$ $\cdots$ $\vdots$ |
  | double integral    | `\iint`                    | `$\iint xy\,dx\,dy$`           |    $\iint xy\,dx\,dy$     |
  | triple integral    | `\iiint`                   | `$\iiint z\,dx\,dy\,dz$`       |  $\iiint z\,dx\,dy\,dz$   |

```latex
\documentclass{article}
\usepackage{amsmath} % Load the 'amsmath' package

\begin{document}

This is an equation aligned at the equals sign.
\begin{align}
    f(x) & = (x+y)(x-y)          \\
         & = x^2 - xy + yx - y^2 \\
         & = x^2 - y^2
\end{align}

This is a matrix enclosed in parentheses.
\[
    A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}
\]

This is a piecewise function.
\[
    f(x) =
    \begin{cases}
        -x, & \text{if } x < 0    \\
        x,  & \text{if } x \geq 0
    \end{cases}
\]

\end{document}
```

---

## The `amssymb` Package

For additional mathematical symbols, load the `amssymb` package in the preamble.

- `\usepackage{amssymb}`: Loads the `amssymb` package, enabling additional mathematical symbols.

- Additional symbols:

  |                                       Symbol                                       | Name       | Command                                                                            |
  | :--------------------------------------------------------------------------------: | ---------- | :--------------------------------------------------------------------------------- |
  |                                    $\therefore$                                    | therefore  | `\therefore`                                                                       |
  |                                     $\because$                                     | because    | `\because`                                                                         |
  | $\mathbb{C}$, $\mathbb{R}$, $\mathbb{Q}$, $\mathbb{Z}$, $\mathbb{N}$, $\mathbb{I}$ | number set | `\mathbb{C}`, `\mathbb{R}`, `\mathbb{Q}`, `\mathbb{Z}`, `\mathbb{N}`, `\mathbb{I}` |

```latex
\documentclass{article}
\usepackage{amssymb} % Load the 'amssymb' package

\begin{document}

The set of real numbers is denoted by $\mathbb{R}$.

\end{document}
```
