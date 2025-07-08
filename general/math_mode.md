# Math Mode in LaTeX

This guide covers both inline and display math modes, common symbols, environments, and best practices.

---

## 1. Entering Math Mode

### Inline Math

Use dollar signs:

```latex
This is inline math: $a^2 + b^2 = c^2$
```

### Display Math

Use \[ ... \] or equation environment:

```latex
\[ a^2 + b^2 = c^2 \]

\begin{equation}
a^2 + b^2 = c^2
\end{equation}
```

Use align, gather, multline, etc., from the amsmath package for multi-line equations.

---

## 2. Superscripts and Subscripts

```latex
a^2 \quad x_i \quad e^{i\pi} + 1 = 0
```

Use curly braces {} to group multiple characters in superscripts or subscripts.

---

## 3. Fractions, Roots, and Stacks

```latex
\frac{a}{b} \quad \sqrt{x} \quad \sqrt[n]{x} \quad \binom{n}{k}
```

---

## 4. Greek Letters

```latex
\alpha \beta \gamma \Delta \pi \theta \Omega
```

- Lowercase: \alpha, \beta, \gamma, …
- Uppercase: \Gamma, \Delta, \Theta, \Omega, …

---

## 5. Common Operators and Relations

### Arithmetic

```latex
+ - \times \div \cdot \pm \mp
```

### Relations

```latex
= < > \leq \geq \neq \approx \equiv
```

### Set Theory & Logic

```latex
\in \notin \subset \supset \cup \cap \forall \exists \neg \land \lor \Rightarrow \Leftrightarrow
```

---

## 6. Functions and Formatting

```latex
\sin x \quad \log x \quad \exp(x) \quad \lim_{x \to 0} f(x)
```

---

## 7. Matrices and Cases

### Matrices

```latex
\begin{bmatrix} a & b \\ c & d \end{bmatrix}
```

Other matrix environments: pmatrix, vmatrix, matrix, etc.

### Piecewise / Cases

```latex
\begin{cases}
x & x \geq 0 \\
-x & x < 0
\end{cases}
```

---

## 8. Aligning Equations (amsmath)

```latex
\begin{align}
a &= b + c \\
d &= e - f
\end{align}
```

Use & to align at the desired symbol (usually =).

---

## 9. Special Symbols

```latex
\infty \nabla \partial \hbar \therefore \because \angle \circ
```

Use \mathbb{R} or \mathcal{A} for Blackboard Bold or Calligraphic fonts.

---

## 10. Best Practices
- Load amsmath when doing any serious math typesetting.
- Use align or equation instead of double-dollar signs ($$...$$).
- Label and reference equations with \label and \ref.
- Use spacing commands like \,, \;, \quad, \! for fine-tuning.

---
