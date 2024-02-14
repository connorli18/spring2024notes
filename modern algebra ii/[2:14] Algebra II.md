# [2/14] Algebra II

#### Prime & Maximal Ideals

**Definition:** Let $R$ be a ring. We say that a <u>proper</u> ideal $I \subset R$ and $I \neq R$ is prime if for any $r \cdot s \in I$ , then either $r \in I$ or $s \in I$​. 

- $I$ is proper
- For any $r \cdot s \in I \implies r \in I \text{ or } s \in I$ 

**Remark:** If $n,m \in \mathbb{Z}$, $p$ is prime, and $p | nm$, this implies that $p | n$ or $p|m$. 

<u>Examples</u>: 

1. $(n) \subset \mathbb{Z}$ is prime iff $n$ is a prime number
2. $(0) = \{0\} \subset R$ is prime iff $R$​ is an integral domain (no zero divisors)

**Theorem:** $I \subset R$ is a prime ideal $\Leftrightarrow$ $R/I$ is an integral domain.

**Proof:** $[0] \in R/I$ is basically the ideal itself $I$. We know that $I$ is prime iff $r \cdot s \in I$.
$$
r\cdot s \in I \implies [r] \cdot [s] \in I \implies [r][s] = 0
$$
 Thus, we have that either $r \in I$ or $s \in I$, which is equivalent to $[r] = [0]$ or $[s] = [0]$. 

---

<u>Goal</u>: Prime ideals in $F[x]$ where $F$ is a field.

**Definition:** We say $f \in F[x]$ is irreducible if $\deg(f) > 0$ and if $f = gh \implies $ either $g$ is a constant or $h$ is a constant (also write this $g \in F^*$ or $h \in F^*$).

<u>Example 1</u>: If $\deg(f) = 1$, then $f$ is irreducible. 

- If $f = gh \implies \deg(f) = 1 \implies \deg(g) + \deg(h) \implies \deg(h) = 0 \text{ or } \deg(g) = 0$

<u>Example 2</u>: $\deg(f) = 2$. Then $f$ is *reducible* (not irreducible) iff $f$ has a root.

- Let $f = gh$. This means $\deg(f) = 2 = \deg(g) + \deg(h)$

| $\deg(g)$ | $\deg(h)$ | Reducible?  |
| --------- | --------- | ----------- |
| 2         | 0         | Irreducible |
| 1         | 1         | *See Below  |
| 0         | 2         | Irreducible |

- Consider the case where $\deg(g) = \deg(h) = 1$. If $f$ is reducible $\implies f = (x- r )\cdot h$ where $r \in F \implies r$ is a root of $f$. This means that it is reducible.

<u>Example 3</u>: Let $\deg(f) = 3$. If $f$ is reducible, then it has a linear factor $\implies f$  has a root.

<u>Example 4</u>: $(x^2 + 1)^2 \subset \mathbb{Q}[x]$ is reducible but has no root in $\mathbb{Q}$. 

---

**Theorem:**   Let $f \in F[x]$ be an irreducible polynomial $\implies (f)$ is prime (and other way around where $(f)$ is prime $\implies$ $f$ is irreducible). 

**Lemma:** (*Euclid's Lemma*) If $f$ is irreducible and $f$ divides $g \cdot h$, then either $f | g$  or $g \in (f)$ OR $f |h $ or $h \in (f)$

**Proof (Lemma):** Assume $f \cancel{|} g$ also that $g \neq (f)$. Now, there exists some $k$ in the principal ideal domain $F[x]$ such that $(f,g) = (k) \implies k |f $. This implies that $k$ is a constant. 

Now, we know $\exists \;r,s$  such that $1 = r\cdot f + s \cdot g$. Multiplying both sides by $h$, we have
$$
h = r \cdot \underbrace{f}_{\in (f)} \cdot h + s \cdot \underbrace{g \cdot h}_{\in (f)} \implies h \in (f)
$$
<u>Example 1</u>: $x^2 + 1$ is a irreducible in $\mathbb{R}[x] \implies x^2 + 1$ generates a prime ideal.
$$
\mathbb{R}[x]/(x^2 + 1) \cong \mathbb{C}
$$
<u>Example 2</u>: $x^2$ is reducibe in any $R[x]$ 
$$
\R[x]/(x^2) \text{ is never a domain}
$$

---

**Definition**: A proper ideal $I \subset R$ is called <u>maximal</u> if any ideal that contains $I$ has to be $R$. 
$$
I \leq J \leq R \implies J = I \text{ or } J = R
$$
**Theorem:** $I \subset R$ is maximal $\iff R/I$ is a field.

**Corollary:** Any maximal ideal if also prime.
$$
R/I \text{ is a field} \implies R/I \text{ is a domain}
$$
**Proof (Theorem):** $S$ is a field iff its only ideals in $S$ are $(0)$ and $S$. We need to show that the only ideals in $R/I$ for a maximal ideal are $\{0\}$ and $R/I$. 

**Lemma:** (*Correspondence Lemma*) There is a bijection between $I \subset J \subset R$ and $J' \subset R/I$ where ideals $J$ contain $I$. 

**Proof (Lemma):** Consider the ring homomorphism $R \rightarrow^{\psi} R/I$. 
$$
J \rightarrow \psi(J) \quad \quad \text{ and } \quad \quad J' \rightarrow \psi^{-1}(J')
$$
The bijection is defined above where $\psi^{-1}$ is the set-theoretic preimage. 

- <u>Exercise</u>: Show that this is well-defined and is a bijection.

**Proof (Theorem) continued:** Let's continue the proof of the theorem. Since $I \subset R$ is maximal $\iff I \subset J \subset R \implies J$ is either $I$ or $R$. By the correspondence lemma, the only ideals in $R/I$ are $\psi(I) = (0)$ and $\psi(R) = R/I$ $\iff R/I$ is a field. 

<u>Example 1</u>: When is $(p)\subset \mathbb{Z}$ maximial?
$$
\mathbb{Z}/p\mathbb{Z} = \mathbb{F}_p \text{ is a field} \implies \text{every } (p) \text{ is maximal}
$$
<u>Example 2</u>: Let $f \in F[x]$ be an irreducible polynomial. When is $(f)$ maximal? Always!

**Proposition:** If $f \in F[x]$ is an irreducible polynomial, then $(f)$ is always maximal!

**Proof:** Let's show that $R = F[x]/(f)$ is a field. Let $[g] \neq [0] \in R$.
$$
g \notin (f) \implies (g,f) = (1) = F[x] \implies r,s \in F[x] \text{ such that } rg + \underbrace{sf}_{\in (f)} = 1
$$
This implies that $[r][g] = [1] \implies [r] = [g]^{-1}$. This completes our proof.

**Corollary:** $(f) \subset F[x]$ is prime$\iff (f)$  is maximal$\iff f$ is irreducible $\iff F[x]/(f)$ is a field.