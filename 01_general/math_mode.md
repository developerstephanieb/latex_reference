# LaTeX Math Mode

This guide provides an overview of math mode, a special environment where text is interpreted as a mathematical formula.

---
## Table of Contents
- [LaTeX Math Mode](#latex-math-mode)
  - [Table of Contents](#table-of-contents)
  - [1. Entering Math Mode](#1-entering-math-mode)
    - [Inline Math](#inline-math)
    - [Display Math](#display-math)
  - [2. Fundamental Constructs](#2-fundamental-constructs)
  - [3. Common Symbols and Functions](#3-common-symbols-and-functions)
    - [General](#general)
    - [Greek Letters](#greek-letters)
    - [Operators and Relations](#operators-and-relations)
    - [Functions](#functions)
    - [Calculus](#calculus)
    - [Set Theory](#set-theory)
    - [Logic Symbols](#logic-symbols)
    - [Accents](#accents)
  - [4. Essential Math Packages](#4-essential-math-packages)
    - [amsmath](#amsmath)
      - [Key Environments](#key-environments)
      - [Additional Commands](#additional-commands)
    - [amssymb](#amssymb)
      - [Additional Symbols](#additional-symbols)

---

## 1. Entering Math Mode

### Inline Math

For formulas within a line of text, use single dollar signs `$...$`.

```latex
The equation for energy is $a^2 + b^2 = c^2$.
```

### Display Math

For formulas that should be centered on their own line, use `\[ ... \]`.

```latex
The equation for energy is:
\[
    a^2 + b^2 = c^2
\]
```

---

## 2. Fundamental Constructs

Inside math mode, characters and commands take on new roles.

**Note**: Superscripts and subscripts containing more than one character must be grouped using curly braces `{}` (e.g., `x^{10}`).

| Name         | Command                         | Example Code    | Rendered Output |
| ------------ | ------------------------------- | --------------- | :-------------: |
| superscripts | `^`                             | `$x^2$`         |      $x^2$      |
| subscripts   | `_`                             | `$a_1$`         |      $a_1$      |
| fractions    | `\frac{numerator}{denominator}` | `$\frac{1}{2}$` |  $\frac{1}{2}$  |
| square roots | `\sqrt{...}`                    | `$\sqrt{2}$`    |   $\sqrt{4}$    |
| n-th roots   | `\sqrt[n]{...}`                 | `$\sqrt[3]{x}$` |  $\sqrt[3]{8}$  |

---

## 3. Common Symbols and Functions

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

**Note**: Capitalizing the command yields the uppercase letter.

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

Use these commands to ensure function names are typeset in an upright (roman) font instead of italics (which are reserved for variables), and to ensure correct spacing.

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
| limit     | `\lim_{var \to }`     | `$\lim_{x \to \infty}$`  | $\lim_{x \to \infty}$  |

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

## 4. Essential Math Packages

### amsmath
For more advanced mathematical typesetting, load the `amsmath` package by adding `\usepackage{amsmath}` to the preamble.

#### Key Environments

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

#### Additional Commands

| Name               | Command                    | Example                        |      Rendered Output      |
| ------------------ | -------------------------- | ------------------------------ | :-----------------------: |
| text in math       | `\text{...}`               | `$\text{speed} = 30$`          |    $\text{speed} = 30$    |
| box around content | `\boxed{...}`              | `$\boxed{E=mc^2}$`             |     $\boxed{E=mc^2}$      |
| dots               | `\dots`,`\cdots`, `\vdots` | `$\dots`,`$\cdots`, `$\vdots$` | $\dots$ $\cdots$ $\vdots$ |
| double integral    | `\iint`                    | `$\iint xy\,dx\,dy$`           |    $\iint xy\,dx\,dy$     |
| triple integral    | `\iiint`                   | `$\iiint z\,dx\,dy\,dz$`       |  $\iiint z\,dx\,dy\,dz$   |

### amssymb

For additional mathematical symbols, load the `amssymb` package by adding `\usepackage{amssymb}` to the preamble.

#### Additional Symbols

|                                       Symbol                                       | Name       | Command                                                                            |
| :--------------------------------------------------------------------------------: | ---------- | :--------------------------------------------------------------------------------- |
|                                    $\therefore$                                    | therefore  | `\therefore`                                                                       |
|                                     $\because$                                     | because    | `\because`                                                                         |
| $\mathbb{C}$, $\mathbb{R}$, $\mathbb{Q}$, $\mathbb{Z}$, $\mathbb{N}$, $\mathbb{I}$ | number set | `\mathbb{C}`, `\mathbb{R}`, `\mathbb{Q}`, `\mathbb{Z}`, `\mathbb{N}`, `\mathbb{I}` |

