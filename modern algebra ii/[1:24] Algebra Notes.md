# [1/24] Algebra II

### Last Time

**Definition:** A function $f: R \rightarrow S$ (where $R,S$ are rings) is called a homomorphism if 

- $f$ is a homomorphism of abelian groups (preserves addition and sends $f(0) \mapsto 0$)

$$
f(a +_R b) = f(a) +_S f(b)
$$

- Preserves $\circ$ such that $f(ab) = f(a)f(b)$

- $f(1_R) = 1_s$​ 

- $\Im(f) \leq S$ 

**Example:** $f: R \rightarrow S$  where $S \neq \{0\}$. The example $f(x) = 0 \in S$ for all $R$ satisfies principles $1$ and $2$, but not principle $3$, which means that it is not a homomorphism.

**Polynomials:** Let $R$ be a ring, then the polynomial ring with coefficients $\in \mathbb{R}$ is
$$
R[x] = \sum_{i=0}^n a_ix^i ,\quad a_i \in \mathbb{R}
$$

### Rings (Polynomials)

**Definition:** Degree of $f \in R[x]$ is a number $\deg(f)$ and the index of the highest non-zero coefficient $\deg(1 + 2x - x^2) = 2$ if $f \neq 0$ and undefined/$-\infty$  for $f = 0$. 

- <u>Note</u>: $1 + 2x - x^2 \in \mathbb{Z}[x]$​ 
- <u>Note:</u> $f = 1$ has $\deg(f) = 0$ 

**Proposition:** Degree of $f$ and degree of $g$ relationship(s)

- $\deg(f + g) \leq \max(\;\deg(f),\deg(g)\;)$​ 

$$
f(x) = x ,\quad g(x) = -x
$$

- $\deg(f \cdot g) \leq \deg(f) + \deg(g)$ 

$$
f,g \in \mathbb{Z}\backslash4\mathbb{Z} \implies f(x) = g(x) = 2x \implies f(x) \cdot g(x) = 0
$$

**Definition:** Given a ring $R$, $R[x]$ is also a ring. We can define the following ring $\left(R[x]\right)[y]$.

- $R[x,y] = \left(R[x]\right)[y] =  \left(R[y]\right)[x]$

$$
R[x,y] := \sum_{i,j} a_{ij} x^iy^j
$$

**Definition:** Given a ring $R$, we can define the ring of functions.
$$
\{f: R \rightarrow R\} := R^R
$$
**Corollary:** $f,g \in R^R$ 

- $(f+g)(r) := f(r) + g(r)$ 
- $(f \cdot g)(r) := f(r) \cdot g(r)$ 
- $0$ is the function $f(r) = 0$, $\forall \;r$ 
- $1$ is the function $f(r) = 1$, $\forall \; r$​ 

---

### Evaluation Function

**Definition:** We define the evaluation function "at $r$": 
$$
\text{ev}_r : R[x] \rightarrow R \implies \text{ev}_r\left(\sum_{i=0}^n a_ix^i\right) = \sum_{i=0}^n a_ir^i
$$

$$

$$

<u>Execise</u>: Check if this evaluation function is a homomorphism.

**Definition:**  The function $\text{ev}$ maps elements of $R$ to evaluation of the function $\in R[x]$. 
$$
\begin{align*}
\text{ev}: R[x] &\rightarrow R^R\\
f &\rightarrow \left(r \rightarrow \text{ev}_r f = \text{``}f(r)\text{''}\right)
\end{align*}
$$
**Example:** For the function $\text{ev}_r$ ,
$$
\begin{align*}
\mathbb{Z}[x] &\longrightarrow^{\text{ev}_3} \mathbb{Z} \\
1+2x &\longrightarrow 1+2 \cdot 3 = 7
\end{align*}
$$
**Example:** For the function $\text{ev}$,
$$
\begin{align*}
\mathbb{Z}[x] &\longrightarrow \mathbb{Z}^\mathbb{Z}\\
1+2x &\longrightarrow (n \rightarrow 1+2n)
\end{align*}
$$
**Example:** First, we have that $R = \mathbb{Z}\backslash 2\mathbb{Z}$ . Now define $f,g \in R[x]$ where $f = 1 + x^2$ and $g = 1 + x$ where $f \neq g$. We can define the following.
$$
\text{ev}(f), \text{ev}(g): R \rightarrow R
$$

| x    | f(x) | g(x) |
| ---- | ---- | ---- |
| 0    | 1    | 1    |
| 1    | 0    | 0    |

- $\text{ev}_0(f) = f(0) = 1 + 0^2 = 1$
- $\text{ev}_0 (g) = g(0) = 1 + 0 = 1$ 
-  $\text{ev}_1 (f) = f(1) = 1 + 1^2 = 0$ 
-  $\text{ev}_1 (g) = g(1) = 1 + 1 = 0$ 

**Remark:** The homomorphism $\text{ev}: R[x] \rightarrow R^R$ is (in general) neither injective nor surjective. 

**Definition:** Let $R \subset S$ and $f \in R[x] \subset S[x]$. Given $s \in S \backslash R$, we can define the $\text{ev}_s: R[x] \rightarrow S$.  The subring $\Im(\text{ev}_s) \leq S$ is denoted $R[s]$.
$$
R[s] = \left\{\sum_{i=0}^n a_is^i \;|\; a_i \in R\right\}
$$
**Remark:** $\mathbb{Z}[i], \mathbb{Q}[\sqrt{2}] = \mathbb{Q}\left(\sqrt{2}\right), $ $\mathbb{Z}\left[\frac{1}{n}\right]$ examples from last class determine $R[s]$ 

**Definition:** $r \in R$ is called a root of $f \in R[x]$ if $\text{ev}_r (f) = f(r) = 0 \in R$. If $R \subset S$, we say that $s \in S$ is a root of $f \in R[x]$ if $\text{ev}_s(f) = 0 \in S$. 

**Definition:** A homomorphism $f: R \rightarrow S$ is called an isomophism if $f$ is bijective on the sets.

---

### Integral Domains & Fraction Fields

**Definition:** We say $r \neq 0 \in R$ is a zero-divisor if $\exists \;s \neq 0 \in R$ such that $r \cdot s = 0$. 

**Example:** $R = \mathbb{Z}\backslash 6\mathbb{Z}$. We have that $2, 3$ are zero-divisors in $R$ since $2 \cdot 3 = 6 \text{ mod } 6 = 0$. 

**Definition:** Ring $R$ is called an (integral) domain if it does not have zero divisors.

**Example:** 

- $\mathbb{Z}$ is an integral domain

- If $S$ is a domain, then any subring $R \leq S$ is also a domain.

- Any field $F$ is a domain

  - **Proof:** Assume $r \cdot s = 0$ and $r,s \neq 0$. $F$ is a field, which implies that $\exists \;r^{-1} \in F$ such that $r^{-1}r = 1 \implies r^{-1}(r s) = s \implies s = 0$, which is a contradiction.

- If $R$ is a domain, then so is $R[x]$. 

  - **Proof:** Let $f,g \in R[x]$ and $\deg(f), \deg(g) \geq 0$. 

  $$
  f = a_nx^n + \text{lower order terms} \quad \quad g = b_mx^m + \text{lower order terms}
  $$

  $$
  f \cdot g = a_nb_m x^{n+m} + \text{lower order terms}
  $$

  ​	Since $R$ is a domain, $a_nb_m \neq 0 \implies fg \neq 0$. 

**Corollary:** If $R$ is a domain, then $\deg(f \cdot g) = \deg(f) + \deg(g)$. 

**Theorem:** $R$ is a domain $\implies$ cancellation law holds in $R$, that is for all $r \neq 0, a, b$, $ra = rb \implies a = b$. 

- <u>(Non) Example</u>: Let $R = \mathbb{Z}\backslash 6\mathbb{Z}$. 

$$
2 \cdot 3 = 2 \cdot 0 \implies 3 \neq 0
$$

**Proof:** Assume $ra = rb$  and $r \neq 0$. 
$$
\begin{align*}
ra - rb &= 0\\
r(a - b) &= 0\\
\implies (a-b) &= 0 \implies a = b
\end{align*}
$$
Now, assume $R$ is not a domain. We know that $r \cdot s = 0$ where $r, s \neq 0$ and can show the following contradiction.
$$
0 = s \cdot 0 \implies r \cdot s = 0 \implies r = 0
$$
**Theorem:** If $R$ is finite and is a domain, then it is a field.

**Proof:** Take $r \neq 0 \in R$. Since $r$ is finite, there exists $n,m$ such that $n < m$ and $r^n = r^m$. This means that $r^m = r^n r^{m-n}$. By the cancellation law, $1 = r^k = r \cdot r^{k-1} = r^{-1}$.  