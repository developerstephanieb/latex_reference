# LaTeX Math Mode

This guide provides an overview of math mode, a special environment where text is interpreted as a mathematical formula.


---

## Table of Contents

[Entering Math Mode](#entering-math-mode)  
[Fundamental Constructs](#fundamental-constructs)  
[Common Symbols and Functions](#common-symbols-and-functions)  
[Essential Math Packages](#essential-math-packages)  

---

## Entering Math Mode

For inline math, enclose the expression in single dollar signs `$...$`. For display math, which centers the formula on its own line, use `\[ ... \]`.

```latex
This equation is written inline: $E = mc^2$

This equation is shown using display math:
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
| square roots | `\sqrt{...}`                    | `$\sqrt{2}$`    |   $\sqrt{4}$    |
| n-th roots   | `\sqrt[n]{...}`                 | `$\sqrt[3]{x}$` |  $\sqrt[3]{8}$  |

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

## Essential Math Packages

### amsmath

For more advanced mathematical typesetting, load the `amsmath` package by adding `\usepackage{amsmath}` to the preamble.

This package provides several useful environments:

* **`equation`**: Use this for a single, numbered equation.

    ```latex
    \begin{equation}
      e^{i\pi} + 1 = 0 \label{eq:euler}
    \end{equation}
    ```

* **`align`**: Use this to align multiple equations. The `&` character specifies the alignment point, typically the equals sign.

    ```latex
    \begin{align}
      f(x) &= (x+y)(x-y) \\
           &= x^2 - xy + yx - y^2 \\
           &= x^2 - y^2
    \end{align}
    ```

* **Matrix Environments**: `amsmath` offers several environments for creating matrices, including **`pmatrix`** (parentheses), **`bmatrix`** (brackets), and **`vmatrix`** (vertical bars).

    ```latex
    \[
      A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}
    \]
    ```

* **`cases`**: This environment is perfect for defining piecewise functions.

    ```latex
    \[
      f(x) =
      \begin{cases}
        -x, & \text{if } x < 0 \\
        x,  & \text{if } x \geq 0
      \end{cases}
    \]
    ```

And additional commands:

| Name               | Command                    | Example                        |      Rendered Output      |
| ------------------ | -------------------------- | ------------------------------ | :-----------------------: |
| text in math       | `\text{...}`               | `$\text{speed} = 30$`          |    $\text{speed} = 30$    |
| box around content | `\boxed{...}`              | `$\boxed{E=mc^2}$`             |     $\boxed{E=mc^2}$      |
| dots               | `\dots`,`\cdots`, `\vdots` | `$\dots`,`$\cdots`, `$\vdots$` | $\dots$ $\cdots$ $\vdots$ |
| double integral    | `\iint`                    | `$\iint xy\,dx\,dy$`           |    $\iint xy\,dx\,dy$     |
| triple integral    | `\iiint`                   | `$\iiint z\,dx\,dy\,dz$`       |  $\iiint z\,dx\,dy\,dz$   |

### amssymb

For additional mathematical symbols, load the `amssymb` package by adding `\usepackage{amssymb}` to the preamble.

This package provides a number of extra symbols:

|                                       Symbol                                       | Name       | Command                                                                            |
| :--------------------------------------------------------------------------------: | ---------- | :--------------------------------------------------------------------------------- |
|                                    $\therefore$                                    | therefore  | `\therefore`                                                                       |
|                                     $\because$                                     | because    | `\because`                                                                         |
| $\mathbb{C}$, $\mathbb{R}$, $\mathbb{Q}$, $\mathbb{Z}$, $\mathbb{N}$, $\mathbb{I}$ | number set | `\mathbb{C}`, `\mathbb{R}`, `\mathbb{Q}`, `\mathbb{Z}`, `\mathbb{N}`, `\mathbb{I}` |
