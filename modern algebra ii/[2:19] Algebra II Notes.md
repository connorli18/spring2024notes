# [2/19] Algebra II Notes

### Last Time

- $I \subset R$ is a prime ideal if $I \neq R$ and if $r \cdot s \in I \implies r \text{ or } s \in I \implies R/I$ is a domain
- $I \subset R$ is a maximal ideal if $I \neq R$ and if $I \subset J \subset R \implies J = I \text{ or } J = R \iff R/I$ is a field.  
  - Any maximal ideal is prime!
- $f \in F[x]$ is called irreducible if $\deg(f) > 0$ and if $f = gh \implies g \text{ or } h \in F$ (a constant).

**Proposition:** The following are equivalent.

1. $f$ is irreducible
2. $(f)$ is prime
3. $(f)$ is maximal
4. $F[x]/(f)$ is a field

<u>Example</u>: Let $f = x^2 + x + 1 \in \mathbb{F}_2[x]$. We can say $f$ is irreducible because $f(0) = 1$ and $f(1) = 1$, we know that $f$ must have a root to be reducible.

This means that $\mathbb{F}_2[x]/(f)$ is a field called $\mathbb{F}_4$. ($x^2 + x + 1 \implies x^2 = -1(x+1) = x+1)$ 
$$
\mathbb{F}_4 = \left\{0,\;1,\;x,\;x+1\right\}
$$
We can check the multiplication properties:

- $x \cdot (x+1) = x^2 + x = 1$
- $x^2 = x+1$
- $(x+1)^2 = x^2 + 1 =x$

<u>Example (Part 2)</u>: $f = x^2 + x + 1 \in \mathbb{F}_4[x]$. 

Let's rename $x \rightarrow \alpha$ in $\mathbb{F}_4$. 
$$
\mathbb{F_4}[\alpha]/(\alpha^2 + \alpha + 1)
$$
Notice that $f$ was irreducible in $\mathbb{F}_2$, but $f$ has a a root in $\mathbb{F}_4$. 
$$
f(\alpha) = \alpha^2 + \alpha + 1 = 0 \in \mathbb{F}_4
$$
In fact, we have the expression.
$$
f = (x+\alpha)(x+\alpha+1) \in \mathbb{F}_4[x]
$$
**Remark:** The notation $\mathbb{F}_4 \neq \mathbb{Z}/4\mathbb{Z}$.

---

### Field Extensions

**Definition:** We say $E$ is a field extension of $F$ if $F \leq$ E (a subfield of $E$).

<u>Example</u>: $\mathbb{F}_4$ is a field extension of $\mathbb{F}_2$. 

**Proposition:** Let $f \in F[x]$ be a non-constant polynomial. There exists a field extension $F \leq E$ such that $F$ has a root in $E$. In other words, $\exists\;\alpha \in E$ such that $f(\alpha) = 0$. 

**Proof:** Consider an irreducible polynomial $p(x) \in F[x]$ such that $p|f$, then $F[\alpha]/(p(x))$ (where $\alpha$ is a formal variable) is a field $E$. 

By construction $p(x) \in E[x]$ is reducible, namely $p(\alpha) = 0 \in E$. Now, $f = hp$ for some $h \in F[x] \implies f(\alpha) = h(\alpha) \cdot p(\alpha) = 0$. This means that $h$ is a root of $f$. 

**Theorem (Kronecher):** Let $f \in F[x]$ be a polynomial of $\deg > 0$, then there exists a field extension $F \leq E$ such that $f$ <u>splits</u>: 
$$
f = c(x-\alpha_1)\cdots(x-\alpha_n), \text{ where } n = \deg(f), \;\{c,\alpha_1,\dots,\alpha_n\} \in E
$$
**Proof:** We use the previous proposition and induction!

1. If $\deg (f) = 1$, then we are done.
2. Otherwise, by the proposition $\exists\; F \leq E$  , $\alpha_1 \in E_1$ such that $f(\alpha_1) = 0 \implies f = (x-\alpha_1) f_1$.
3. Apply the induction step to $f_1 \in E_1[x]$ of $\deg(f) -1$. 

---

### Vector Spaces

**Definition:** For a field $F$, the vector space over $F$ or $F$-vector space is a set $V$ with two operations.

- ''$+$'': $V \times V \rightarrow V$ such that $V$ is an abelian group
- ''$\circ$'': $F \times V \rightarrow V$ such that (scalar multiplication)
  - Associativity: $(a \cdot b) \cdot \bar{v} = a \cdot (b \cdot \bar{v})$ 
  - Distributivity: $(a + b)\bar{v} = a\bar{v} + b\bar{v}$, $a(\bar{v} + \bar{w}) = a\bar{v} + a\bar{w}$
  - Identity: $1\cdot \bar{v} = \bar{v}$ 

**Remark:** If $F \leq E$ is a field extension $\implies E$ is a vector space over $F$.

<u>Example(s)</u>: 

- $\{0\}$ is a $F$-vector space
- $F^n = \{(f_1, \dots, f_n) : f_i \in F\}$,  is an $F$​-vector space.

----

**Definition (Linear Independence):** $\bar{v}_1, \dots \bar{v}_n \in V$ are called linearly independent if $f_1 \bar{v}_1 + \cdots + f_n \bar{v}_n = 0 \implies f_1, \dots f_n = 0$. 

**Definition (Basis):** $\{\bar{v}_1, \dots \bar{v}_n\}$ form a basis of $V$ if $\bar{v}_1, \dots \bar{v}_n$ are linearl independent and span $V$ (form any element of $V$ through linearly combination).

**Proposition:** If $V$ has a basis, then the <u>number</u> of elements in any other basis of $V$ is the same. 

- The "<u>number</u>" is defined at the $\text{dim}_F V$

---

**Definition:** The dimension of a field extension $E$ over $F$ as an $F$-vector space is called <u>the degree</u> of extension and denoted by
$$
[E:F] := \dim_F E
$$
**Proposition:** Let $f \in F[x]$ be an irreducible polynomial. 
$$
\left[F[x]/(f) : F\right] = \deg f
$$
 **Proof:** Let $h \in F[x]$. By long division, $\exists! \; g,r \in F[x]$ such that $h = g\cdot f + r$, such that $\deg(r) < \deg(f)$. This implies that there is a bijection (isomorphism of abelian groups) between $F[x]/(f)$ and $\{a_0 + a_1x + \dots + a_{n-1}x^{n-1} : a_i \in F\}$, $n = \deg(f)$. 

Then, $\{1,x,\dots,x^{n-1}\}$ form a basis of $F[x]/(f) \implies \dim_F E = [E:F] = n$. 

<u>Examples</u>:

- $[F:F] = 1$
- $[\mathbb{C}: \mathbb{R}] = 2$, basis will be $\{1,i\}$ since $a + ib \in \mathbb{C}$
- $[\mathbb{R}: \mathbb{Q}] = \infty$ 
- $[\mathbb{F}_4:\mathbb{F}_2] = 2$ 

**Theorem:** Any finite field $F$ has $p^n$ elements for a prime $p$ and integer $n \in \mathbb{Z}^+$. 

**Proof:** If $F$ is finite $\implies \text{char}\;F = p > 0$ (by definition $\mathbb{F}_p \leq F$​). 

- $\text{char} \;F$, characteristic of $F$ is $p$, each element has order $p$ 

