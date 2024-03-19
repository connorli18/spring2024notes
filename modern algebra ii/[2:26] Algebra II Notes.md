# [2/26] Algebra II Notes

#### Field Extensions Review

Imagine there exists some $E$ such that $F \leq E$. 
$$
\text{ev}_{\alpha} : F[x] \rightarrow E
$$

1. $\text{Ker\;} \text{ev}_\alpha = \{0\} \implies \alpha$  is transcendental.

$$
F \leq F[\alpha] \leq F(\alpha) \leq E \quad \quad \quad [E:F] = \infty
$$

2. $\text{Ker\;} \text{ev}_\alpha = (p) \implies p \text{ irreducible} \implies$ $\alpha$ is called <u>algebraic</u> in this case

$$
F \leq F[\alpha] = \Im \;\text{ev}_\alpha \cong F[x] / (p) = F(\alpha) \leq E \quad \quad \quad [F(\alpha) : F] = \deg(p)
$$

Some more useful notes:

- $F \leq K \leq E \implies [E:F] = [E:K] \cdot [K : F]$ 

- Every finite degree extension is algebraic (every element of $E$ is $F$-algebraic)
- Every finite degree extension $F \leq E$ is of the form $E = \underbrace{F(\alpha_1, \dots, \alpha_n)}_{\bigcap_{F \leq K \leq E, \;\alpha_i \in K} K}$ for some $\alpha_1, \dots, \alpha_n \in E$.  
- If $\alpha$ is algebraic, then $F[\alpha] = F[x]\;/\;(p)$ then we call an irreducible <u>monic</u> polynomial $p$ the irreducible polynomial of $\alpha$:

$$
p = \text{irr}\left(\alpha, F\right)
$$

- <u>Example</u>: $\text{irr}\left(\sqrt{2},  \mathbb{Q}\right) = x^2 - 2$, $\text{irr}\left(\sqrt{2},\mathbb{R}\right) = x-\sqrt{2}$   

---

#### Classification of Finite Fields

**Recall:** If $F$ is finite, then $\#F = p^n$ and $p$ is prime, $n \in \mathbb{N}$. 

**Proof:** $F$ is finite $\implies$ $F$ has characteristic $p > 0 \implies \mathbb{F}_p \leq F$, $F$ is an $\mathbb{F}_p$ vector space of dimension $n < \infty \implies$ as a vector space, $F \cong (\mathbb{F}_p)^n$.  

---

For today, fix $q = p^n$. 

<u>Proposition</u>: if $\#F = q$, then $F^* = (F, \circ)$ (the multiplicative group) is cyclic.
$$
F^* \cong \mathbb{Z}/(q-1)\mathbb{Z}
$$
This is because every element is invertible except for $0$. 

**Proof:** Since $F$ is finite, $F^*$ is a finite abelian group. By the classification theory, $F^* = \times_{i}\left(\mathbb{Z}/p_i^{n_i}\mathbb{Z}\right)$ 
$$
F^* = \left(\mathbb{Z}/p_1^{n_1}\mathbb{Z}\right) \times \left(\mathbb{Z}/p_2^{n_2}\mathbb{Z}\right) \times \cdots
$$
<u>Note</u>: The product of two cyclic groups is cyclic if the $\mathbb{Z}/a\mathbb{Z}$ (if $a,b$ are coprime).

It follows that $F^*$ is not cyclic iff there exist $p_i = p_j, \; i \neq j$ in the decomposition. In particular, if $F^*$ is not cyclic, then there exists a prime $p$ and a subgroup
$$
H = \left(\mathbb{Z}/p\mathbb{Z} \times \mathbb{Z}/p\mathbb{Z}, +\right) \leq \left(F^*, \circ\right)
$$
Now, we will prove that $F^*$ has to be cyclic by contradiction. If $F^*$ is not, then every element of $H$ is multiplicatively of order $p$. 
$$
\alpha \in H \implies \alpha^p = 1
$$
In other words, $\alpha$ is a root of $x^p - 1 \in F[x]$. We have that $x^p - 1$ has at most $p$ roots, but every $\alpha \in H$ is a root and $\# H = p^2 \implies \cancel{\exist} H \leq F$. 

**Proposition:** For every prime $p$ and integer $n \in \mathbb{N}$, there exists a field $F$, $\#F = q = p^n$. 

**Proof:** We will construct a particular field $\mathbb{F}_q = \mathbb{F}_{p^n}$. Since $F^* \cong \mathbb{Z}/(q-1)\mathbb{Z}$, for every $\alpha \in F/\{0\}$, $\alpha^{q-1} = 1 \implies$ for every $\alpha \in F$, then $\alpha^q = \alpha$. 

If $F$ exists, then every element of $F$ satifies the above $\implies$ every $\alpha$ is a root fo $x^q - x \in \mathbb{F}_p[x]$. 

Consider $x^q - x \in \mathbb{F}_p[x]$, there exists a field extension $\mathbb{F}_p \leq E$ where $x^q - x$ splits as the following by Kronecker's theorem.
$$
x^q - x = (x-\alpha_1) \cdots (x-\alpha_q)
$$
Let $\mathbb{F}_q \subset E$ be defined as follow.
$$
\mathbb{F}_q = \{\alpha \in E : \alpha^q - \alpha = 0\}
$$
In order to prove the theorem, we show that

1. $\mathbb{F}_q$ is closed under $+, \;\circ, \;(\cdot)^{-1}$ 
2. $\# \mathbb{F}_q = q$ 

To prove (1), let $\alpha,\beta \in \mathbb{F}_q \implies \alpha^q = \alpha$ and $\beta^q = \beta$. This implies that
$$
(\alpha\beta)^q = \alpha^q \beta^q = \alpha\beta \implies \alpha\beta \in \mathbb{F}_q
$$
Similarly, show the following.
$$
(\alpha + \beta)^q = \text{Fr}_q (\alpha + \beta) = \text{Fr}_q (\alpha) + \text{Fr}_q (\beta) = \alpha^q + \beta^q = \alpha + \beta
$$
We have shown that $\mathbb{F}_q$ is closed under $+,\circ \implies \mathbb{F}_q \leq E$ subring, if $\alpha \neq 0 \in \mathbb{F}_q \implies \alpha^{q-1} = 1$, which means that $\alpha^{q-2} = \alpha^{-1}$. Therefore, $\mathbb{F}_q \leq E$ is a subfield.

To prove (2), in $E$, $x^q - x = (x-\alpha_1) \cdots (x-\alpha_q) \implies \#\mathbb{F}_p \leq q$  because of repeated roots.If $x^q - x$​ does not have repeated roots, then we are done.

----

**Subsection**: This subsection is dealing with repeated roots of polynomials. 

Let $f \in \mathbb{C}[x]$. How do we know if $f$ has repeated roots? 

- $f = (x-a)^2 \cdot \tilde{f}$  , factor and check! 
- At the repeat root of $f$, $f'$ vanishes, $f' = 2(x-\alpha) \cdot \tilde{f} + (x-\alpha)^2 \tilde{f}'$

$$
f'(\alpha) = 0 \iff f,f'\text{ have a common root} \implies (f,f') \neq 1
$$

**Derivatives:** Let $R,S$ be rings. A function $D: R \rightarrow S$ is called a <u>derivation</u> if 

1) $D$ is a homomorphism of additive groups
2) $D$ satisfies the product rule: $D(a\cdot b) = D(a)\cdot b + a \cdot D(b)$ 

**Definition:** We define a derivation on $R[x]$ by 

1. $D(x) = 1$
2. $D(1) = 0$ or $D(R) = 0$

<u>Exercise</u>: $D$ is a well-defined derivation from $R[x] \rightarrow R[x]$ that concides with the usual derivative for $R = \mathbb{C}$. 

In particular, $D(x^n) = nx^{n-1}$ and $D(f^n) = n \cdot f^{n-1} D(f)$. 

**Theorem:** (Next class) Let $f \in F[x]$, then there exists a field extension $F \leq E$  where $f$ has a repeated root  $\iff$ $\text{gcd}(f, D(f)) \neq 1$. 

<u>Example</u>: We have $D(x^q - x)$ and since $q = p^n$, 
$$
D(x^q - x) = q\cdot x^{q-1} - 1 = -1 \implies (x^q - x, D(x^q - x)) = 1
$$
This implies that $x^q - x$ has no repeated roots.d
