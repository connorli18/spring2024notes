# Introduction

In this class: rings, fields

- Insolvability of $\geq 5$ equations in radicals
- Fundamental theorem of algebra

## Review

**Definition:** Recall that a **group** is a set $G$ with operations $o : G \times G \to G$ (multiplication) and $( \cdot )^{-1} : G \times G \to G$ such that:

1. If $f, g, h \in G$, then $(fg)h = f(gh)$
2. There exists a unit $e \in G$ such that $e \circ g = g \circ e = g$ and $g \circ g^{-1} = g^{-1} \circ g = e$

**Examples:**

1. $(\Z, +), e = 0, (\cdot)^{-1} = -(\cdot)$
2. $D_n = $ dihedral group - group of symmetries of a regular $n$-gon
    - $e = $ identity transformation
3. $GL_n(\R) = n \times n$ matrices with determinant $\neq 0$
    - $e = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}$

**Definition:** $G$ is an **abelian group** if $g \circ h = h \circ g$ (commutativity).

4. $n \times n$ matrices with respect to addition is an abelian group

## Rings

**Definition:** A **ring** $R$ is a set with two operations **addition** and **multiplication** $(+, \cdot)$ such that

1. $(R, +)$ is an abelian group
2. $\cdot$ is associative: $a(bc) = (ab)c$
3. **Distributivity:** $a(b + c) = ab + ac$ and $(a + b)c = ab + ac$

**Definition:** $R$ is a ring with **unit** if there exists $1 \in R$ such that $1 \cdot a = a \cdot 1 = a$ for any $a$ in the ring.

- Unit with respect to addition $+$ is usually denoted by $0$
- Unit with respect to multiplication $\times$ is usually denoted by $1$

**Definition:** $R$ is a **commutative ring** if $ab = ba$ for all $a, b \in R$

In this class, we mostly work with commutative rings with unit, so "ring" will mean this.

**Examples:**

0. The "zero ring" $R = \{0\}$. All the operations are trivial: $0 + 0 = 0 \cdot 0 = 0$. In this case, $1 = 0$.

**Exercise:** if $R$ is a ring such that $1 = 0$, then $R$ is the "zero ring".

1. $(\Z, +, \cdot)$ is a ring
2. ($\text{Mat}_{n \times n}(\R), +, \cdot)$ is a non-commutative ring with unit $1 = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}$
3. **Polynomial ring** $(R[x], +, \cdot)$ with coefficients in $R$, where $R$ is another ring (not necessarily commutative). $x$ is a formal variable. Elements are of the form

$$
\sum_{i=0}^N a_i x^i \leftrightarrow (a_0, a_1, \ldots, a_N) \quad a_i \in R
$$

$+$ is component-wise. Multiplication is as follows:
$$
\qty(\sum_{i=0}^N a_ix^i) \cdot \qty(\sum_{j=0}^M b_jx^j) = \sum_{k=0}^{N + M} \qty(\sum_{i+j = k} a_ib_j) x^k
$$

4. $\Q, \R, \C$ are rings

### Subrings

**Definition:** A **subring** of $R$ is a subset closed under $+, \cdot$ and containing $1$. We write $R' \leq R$ if $R'$ is a subring of $R$.
$$
\Z \leq R_1 \leq \Q \leq R_2 \leq \R \leq \C
$$
Let's construct $R_1$ by adding $1/2$ to $\Z$.

If $n \in \Z$, then $n + 1/2 \in \Z + 1/2$, so $R$ must contain all half-integers.
$$
n \cdot \frac{1}{2} \in \Z \cup \qty(\Z + \frac{1}{2})
$$
Also, $1/2 \cdot 1/2 = 1/4 \leadsto 1/2^k$ must be in $R$, so $n/2^k$ must be in $R$.

**Definition:**
$$
\Z\qty[\frac{1}{2}] = \left\{\frac{n}{2^k} : n \in Z, k \in \Z_{\geq 0}\right\}
$$
is the minimal subring of $\Q$ containing $1/2$.

**Proof:** $1 \in \Z[1/2] \implies \Z \subset \Z[1/2]$. You can keep multiplying by $1/2$ to get the $1/2^k$ factor. Finally, check that it is a ring:
$$
\frac{n}{2^k} + \frac{m}{2^p} = \frac{2^pn + 2^km}{2^{k+p}} \quad \frac{n}{2^k} \cdot \frac{m}{2^p} = \frac{nm}{2^{kp}}
$$
More generally, $\Z[1/n] \leq \Q$ is the minimal subring of $\Q$ containing $1/n$, where
$$
\Z\qty[\frac{1}{n}] = \left\{\frac{m}{n^k} : m \in \Z, k \in \Z_{\geq 0}\right\}
$$
**Exercise:** prove that minimal subring containing $1/n$ and $1/m$ is $\Z[1/nm]$.

-----

There exists $\R_3 \leq \C$ such that $R_3 \not\leq \R$.

**Example:** The **Gaussian integers** $\Z[i] = \{a + ib : a, b \in \Z\}$. Check this is a ring:
$$
(a + ib) + (c + id) = (a + c) + i(b + d) \\
(a + ib)(c + id) = (ac - bd) + i(ad + bc)
$$

-----

$$
R_2 = \Q(\sqrt{2}) = \{a + b\sqrt{2} : a, b \in \Q\}
$$

Check it's closed under multiplication:
$$
(a + b\sqrt{2})(c + d\sqrt{2}) = (ac + 2bd) + (ad + bc)\sqrt{2}
$$
**Proposition:** any nonzero element in $\Q(\sqrt{2})$ has an inverse in this ring:
$$
\frac{1}{a + b\sqrt{2}}
= \frac{1}{a + b\sqrt{2}} \cdot \frac{a - b\sqrt{2}}{a - b\sqrt{2}}
= \frac{a - b\sqrt{2}}{a^2 - 2b^2}
= \frac{a}{a^2 - 2b^2} - \frac{b}{a^2 - 2b^2}\sqrt{2}
\in \Q(\sqrt{2})
$$
**Definition:** A ring $R$ is called a **field** if every nonzero $a \in R$ has a multiplicative inverse.

