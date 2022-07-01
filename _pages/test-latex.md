---
layout: single
permalink: /test-latex/
hidden: true
---

### LaTeX snippets (mostly math equations)

Example of inline equation with `$` symbol, $\frac{1}{2} + \frac{1}{3} = \frac{5}{6}$.

Absolute value.
- Correct. method 1.  `\lvert`: $\lvert x \rvert$
- Others. method 2. norm `\lVert`: $\lVert x \rVert$
- Wrong (in some articles) `| . |`: $|x|$

Example of an equation in a new line with `$$` symbol

$$a^2 + b^2 = c^2$$

space at the beginning

$$ a^2 + b^2 = c^2$$

and this one with `\begin{equation}` environment

\begin{equation}
  \sum_{1}^{n} i = \dfrac{n(n+1)}{2}
\end{equation}

An equation with cases

$$f(x)=
\begin{cases}
    \frac{x^2-x}{x}& \text{if } x\geq 1\\
    0              & \text{otherwise}
\end{cases}
$$

Another one

$$f(x)=
\left\{
  \begin{array}{ c l }
    \frac{x^2 - x}{2} & \quad \textrm{if } x \geq 1 \\
    0                 & \quad \textrm{otherwise}
  \end{array}
\right.$$


Matrix using `array`

$$
\left(
  \begin{array}{ c c c }
    1 & 2 & 3 \\
    4 & 5 & 6 \\
  \end{array}
\right)$$
