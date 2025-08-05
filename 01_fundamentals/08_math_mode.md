# 08: Math Mode

This guide provides an overview of math mode, the specialized environment for typesetting mathematical formulas and equations.

---

## Entering Math Mode

LaTeX provides two primary modes for typesetting mathematics.

- **Inline Mode**: For formulas that appear within a line of text. Use a single dollar sign (`$`) to open and close the environment.

- **Display Mode**: For formulas that are set apart from the text on their own line and centered. Use double dollar signs (`$$`) or the `\[ ... \]` environment to open and close.

```latex
This equation is written inline: $E = mc^2$

This equation is written in display mode:
\[
    F = ma
\]
```

---

## Fundamental Constructs

Inside math mode, characters and commands take on new roles.

*Note*: Superscripts and subscripts containing more than one character must be grouped using curly braces `{}` (e.g., `x^{10}`).

| Name         | Command                         | Example Code    | Rendered Output |
| ------------ | ------------------------------- | --------------- | :-------------: |
| superscripts | `^`                             | `$x^2$`         |      $x^2$      |
| subscripts   | `_`                             | `$a_1$`         |      $a_1$      |
| fractions    | `\frac{numerator}{denominator}` | `$\frac{1}{2}$` |  $\frac{1}{2}$  |
| square roots | `\sqrt[n]{radicand}`            | `$\sqrt[3]{x}$` |  $\sqrt[3]{x}$  |

---

## Common Symbols and Functions

### General

|   Symbol    | Name               | Command     |
| :---------: | ------------------ | ----------- |
|  $\infty$   | infinity           | `\infty`    |
| $\partial$  | partial derivative | `\partial`  |
|  $^\circ$   | degree             | `^\circ`    |
|  $\angle$   | angle              | `\angle`    |
|   $\perp$   | perpendicular      | `\perp`     |
| $\parallel$ | parallel           | `\parallel` |

### Greek Letters

*Note*: Capitalizing the command yields the uppercase letter.

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
| $\times$  | multiplication        | `\times`  |
|  $\div$   | division              | `\div`    |
|   $\pm$   | plus-minus            | `\pm`     |
|  $\cdot$  | dot product           | `\cdot`   |
|  $\leq$   | less than or equal    | `\leq`    |
|  $\geq$   | greater than or equal | `\geq`    |
|  $\neq$   | not equal             | `\neq`    |
| $\approx$ | approximately         | `\approx` |
| $\equiv$  | equivalent            | `\equiv`  |

### Functions

*Note*: Use these commands to typeset function names upright (roman) and with proper spacing. This distinguishes them from variables, which are italicized by default.

|             Symbol              | Name                         | Command                         |
| :-----------------------------: | ---------------------------- | ------------------------------- |
|          $\log$, $\ln$          | logarithm, natural logarithm | `\log`, `\ln`                   |
|     $\sin$, $\cos$, $\tan$      | trig functions               | `\sin`, `\cos`, `\tan`          |
|             $\exp$              | exponential                  | `\exp`                          |
| $\arcsin$, $\arccos$, $\arctan$ | arc                          | `\arcsin`, `\arccos`, `\arctan` |
|    $\sinh$, $\cosh$, $\tanh$    | hyperbolic                   | `\sinh`, `\cosh`, `\tanh`       |

### Calculus

| Name      | Command               | Example                  |    Rendered Output     |
| --------- | --------------------- | ------------------------ | :--------------------: |
| integral  | `\int_{start}^{end}`  | `$\int_{0}^{1} x^2\,dx$` | $\int_{0}^{1} x^2\,dx$ |
| summation | `\sum_{start}^{end}`  | `$\sum_{i=1}^{n} i$`     |   $\sum_{i=1}^{n} i$   |
| product   | `\prod_{start}^{end}` | `$\prod_{i=1}^{n} i$`    |  $\prod_{i=1}^{n} i$   |
| limit     | `\lim_{var \to val}`  | `$\lim_{x \to \infty}$`  | $\lim_{x \to \infty}$  |

### Set Theory

|         Symbol         | Name                          | Command                |
| :--------------------: | ----------------------------- | ---------------------- |
|    $\in$, $\notin$     | element of, not an element of | `\in`, `\notin`        |
| $\subset$, $\subseteq$ | proper subset, subset         | `\subset`, `\subseteq` |
| $\supset$, $\supseteq$ | proper superset, superset     | `\supset`, `\supseteq` |
|     $\cup$, $\cap$     | union, intersection           | `\cup`, `\cap`         |
|      $\emptyset$       | empty set                     | `\emptyset`            |

### Logic Symbols

|      Symbol       | Name                 | Command           |
| :---------------: | -------------------- | ----------------- |
|      $\neg$       | negation (not)       | `\neg`            |
|  $\land$, $\lor$  | and, or              | `\land`, `\lor`   |
|   $\rightarrow$   | implies              | `\rightarrow`     |
| $\Leftrightarrow$ | if and only if (iff) | `\Leftrightarrow` |
|     $\forall$     | for all              | `\forall`         |
|     $\exists$     | there exists         | `\exists`         |

### Accents

|  Symbol   | Name         | Command   |
| :-------: | ------------ | --------- |
| $\hat{x}$ | hat          | `\hat{x}` |
| $\bar{y}$ | bar          | `\bar{y}` |
| $\vec{v}$ | vector arrow | `\vec{v}` |

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
