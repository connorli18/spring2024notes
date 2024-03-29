# [2/5] Algebra II Notes

### Ideals

**Definition:** $I \subset R$ is called an <u>ideal</u> if 

- $I$ is an abelian subgroup
- Absorbs multiplication $\forall r \in R$  and $a \in I$,  $r \cdot a \in I$ 

**Proposition:** Let $f: R \rightarrow S$ be a ring homomorphism, then $\text{Ker}(f) = \{r \in R: f(r) = 0\}$ is an ideal in $R$. 

<u>Example</u>: $n\mathbb{Z} \subset \mathbb{Z}$ is an ideal and the kernel of $\mathbb{Z} \rightarrow \mathbb{Z}\backslash n\mathbb{Z}$​

-----

**Definition:** A principal ideal generated by $r \in R$ 
$$
(r) = rR = \{r \cdot a, a \in \mathbb{R}\}
$$

- Addition: $r \cdot a + r \cdot b = r(a + b)$ 
- Multiplication: $b \cdot (r \cdot a) = r \cdot (a \cdot b)$ 

<u>Exercise</u>: Show that $(r) = \bigcap_{I, r\in I}$ $I$ (principal ideal is the minimal ideal containing $r$). 

**Notation:** $(r_1, \dots, r_n) = \{r_1a_1 + \cdots + r_na_n: a_i \in R \}$, the ideal generated by $r_1, \dots, r_n$, which is not a princpal ideal.

<u>Exercise</u>: Show that $(r_1, \dots r_n) = \bigcap_{I, \;r_1, \dots, r_n \in I} I$. 

----

**Question:** What are possible ideals in $\mathbb{Z}$ ?

- $\{0\} = (0)$ or $\mathbb{Z} = (1)$ 
- $n\mathbb{Z} = (n)$

**Proposition:** Any idea in $\mathbb{Z}$ is a principal ideal $= (n)$, or it's the zero ideal. 

**Proof:** Let $I \subset \mathbb{Z}$ be an ideal. Now, consider its smallest positive element $n \in \mathbb{Z}$. Assume $(n) \neq I$, then there exists $m \in I \backslash (n)$, which satisfies $m > n$.  We can then divide $m$ by $n$, which implies
$$
\begin{align*}
	m = k \cdot n + r \quad \text{ where } 0 \leq r < n\\
\end{align*}
$$
Since $I$ is an abelian subgroup and closed under addition, we know that $m - k \cdot n \in I$, then we have that $r$ is part of the ideal, which means that $r \in I$, a contradiction. Since $n$ is the smallest positive element in $I$, so $r = 0$, $m \in (n)$.  

---

**Definition:** A <u>principle ideal domain</u> (PID)  is a domain where every ideal is principal. 

<u>Example</u>: The computation above shows that $\mathbb{Z}$ is a PID.

### Quotient Rings & First Homomorphism Theorem

**Definition:** Let $I \subset R$ be an ideal. We define a quotient ring as 
$$
R / I = \{[a] = a+I, a \in R \}
$$

- $[a]$ is an equivalence class, we say that $[a] \backsim [b]$ if $a - b \in I$ 

<u>Ring Operations</u>: The ring operations are

- $[a] + [b] = [a + b]$ 
- $[a] \cdot [b] = [a \cdot b]$ 
- $0 = [0] = I$ and $1 = [1]$ 

<u>Exercise</u>: Check that $1) 2)$ do not depend on the choice of a representative in the equivalence class.

**Proof:** Let's check $2)$ is well defined. Let $[a] = [a']$ and $[b] = [b']$. We need to show that $ab - a'b' \in I$. Let's add elements that create a sum.
$$
ab - ab' + ab' - a'b' = a\underbrace{(b - b')}_{\in I} + b'\underbrace{(a - a')}_{\in I}
$$
Thus, we know that the RHS $\in I$​ by absorption. 

----

**Proposition:** A natural homomorphism $\phi: R \rightarrow R/I$ which is defined by $r \mapsto [r]$ is surjective and $\text{Ker}(\phi) = I$. 

<u>Corollary</u>: Ideals $\Longleftrightarrow$​ kernels of homomorphisms

**Theorem:** First homomorphism theorem for rings. Let $f: R \rightarrow S$ be a homomorphism. Then $\Im(f) \cong R/\text{Ker}(f)$, which implies $f(r) \longleftarrow^{\bar{f}} [r]$​.   
$$
\bar{f}([r]) := f(r)
$$
**Proof:** $R$, $R/ \text{Ker}(f)$, and $\Im(f)$ are abelian subgroups. By the first homomorphism theorem for groups, $\Im(f) \cong R \backslash \text{Ker}(f)$. 

We need to show that $[r] \rightarrow f(r)$ is a ring homomorphism. 
$$
\bar{f}([r][r']) = \bar{f}([r\cdot r']) = f(r \cdot r') = f(r)f(r') = f([r])f([r'])
$$
<u>Note</u>: Remember, for any ring $R$, there exists a unique homomorphism $i: \mathbb{Z} \rightarrow R$ such that $n \in \mathbb{Z} \mapsto \underbrace{1 + \dots + 1}_{n}$ . 

- By the theorem, $\Im(i) = \mathbb{Z}\backslash\text{Ker}(f)$ where $\text{Ker}(i)$ is an ideal in $\mathbb{Z}$.

- If $R \neq 0 \implies i(1) = 1 \neq 0$, then $\text{Ker}(i)$ is not $\mathbb{Z}$. Then, either 
  - $1) \;\text{Ker}(i) = \{0\}$, $\Im(i) = \mathbb{Z}$  
  - $2) \;\text{Ker}(i) = n\mathbb{Z}$, $n > 1 \implies \Im(i) = \mathbb{Z}/n\mathbb{Z}$.   

**Corollary:** A ring contains a subring $\mathbb{Z}$ or $\mathbb{Z}/n\mathbb{Z}$. 

---

**Theorem:** Assume $F$ is a field and $\Im(i) = \mathbb{Z}/n\mathbb{Z}$. then $n$ is prime.

**Proof:** If $n$ is not prime, then $\Im(i) \cong \mathbb{Z}/n\mathbb{Z}$ contains zero divisors, but a field cannot have those.

<u>HW Exercise</u>: If $R \leq F$, $F$ is a field, then $\text{Frac}(R) \leq F$. More precisely, there exists $R \subset S \subset F$ such that $S \cong \text{Frac}(R)$. 

<u>Notes:</u> Any field, contains a subring $\mathbb{Z}$ or $\mathbb{Z}/p\mathbb{Z}$ where $p$ is prime.

- $\text{Frac}(\mathbb{Z}) = \mathbb{Q}$ 
- $\text{Frac}(\mathbb{Z}/p\mathbb{Z}) = \mathbb{Z}/p\mathbb{Z} := \mathbb{F}_p$  

**Corollary:** Every field contains a subfield isomorphic to either $\mathbb{Q}$ or $\mathbb{F}_p$. 

- $\mathbb{Q}$: field of characteristic $0$ 
- $\mathbb{F}_p$: field of characteristic $p$ 

**Definition:** We say $r \in F$ is of order $p$ if $\overbrace{r + \cdots + r}^{p} = 0$.

**Theorem:** This theorem has two parts.

1. For a field of characteristic $p$, every nonzero element has order $p$. 
2. Every element of a field of characteristic $0$ has infinite order.

**Proof:** (exercise)

### Polynomial Rings over Fields

We define polynomial rings over fields $F[x]$ as notation.

**Theorem:** Let $F$ be a field and $g \in F[x]\backslash F$ be a non-constant polynomial. then for any $f \in F[x]$, there exists a unique decomposition $f = h \cdot g + r$ where $\deg(r) < \deg(g)$. 

**Proof:** First, we must prove existence. If $\deg(f) = n < deg(g) = m$, then we are done via $h = 0, r = f$. 

Otherwise $(n \geq m)$, let $f = \sum_{i=0}^n a_i x^i$, $g = \sum_{j=0}^m b_jx^j$ and $a_n, b_m \neq 0$. We prove this by induction in $n$. 

Let $h_1 = \frac{a_n}{b_m}^{n-m}$, then 
$$
\deg(\underbrace{f - h_1 \cdot g}_{f_1}) \leq n - 1
$$
Apply the induction step for $f_1$ to complete the proof.

