# [2/21] Algebra Notes

### Last Time

- If $F \leq E$, then we call $E$ a field extension of $F$. 

- $E$ is an $F$-vector space over $F$ 
- degree of the extension $[E:F] = \dim_F E$ 
- $[F[\alpha]/(f) : F] = \deg f$ 

**Proposition:** Let $F$ be a finite field, then the number of elements in $F = p^n$ for some prime $p, n > 1$ where $n \in \mathbb{Z}$. 

**Proof:** First, since $F$ is finite, the characteristic of $F$ is some prime $p$. This means that $\mathbb{F}_p \leq F$, which also implies that $F$ is an $\mathbb{F}_p$ vector space. Since it's finite dimensional $\implies F \cong \mathbb{F}^n_p$ as an $\mathbb{F}_p$ vector space.
$$
\mathbb{F}_p^n = (\underbrace{a_1}_{\mathbb{F}_p}, \;\dots, \;\underbrace{a_n}_{\mathbb{F}_p}) \implies \# \mathbb{F}_p^n = p^n
$$

---

### Algbraic & Transcendental Extensions

Let $F \leq E$ be an extension and $\alpha \in E$. Consider $\text{ev}_{\alpha} : F[x] \rightarrow E$. 

**Notation:** $\Im(\text{ev}_\alpha) = F[\alpha] \leq E$ 

By the first homomoprhism theorem, $F[a] = F[x]/\text{Ker}(\text{ev}_\alpha)$. 
$$
\text{Ker}(\text{ev}_\alpha) = I \subset F[x], \quad I \neq F[x]
$$
 Thus, there are $2$ options. 

1) $I = \{0\}$ 

2. $I = (f)$ where $f \neq 0$ and $f$​ is irreducible. 

---

Let's examine the first option. We know that $\Im(\text{ev}_\alpha) = F[\alpha] \cong F[\alpha]$.  

**Definition:** If $\text{Ker}(\text{ev}_\alpha) = 0 \implies \alpha$ is called a transcendental element of $E$ over $F$. In other words, there are no algebraic relations for $\alpha$ in $E$ with coefficients from $F$. 
$$
F \leq \underbrace{F[\alpha]}_{\cong F[x]} \leq \underbrace{F(\alpha)}_{\text{Frac}\;F[x] = F(\alpha)} \leq E
$$
**Corollary:** $[E: F] = \infty$ 

**Proof:** $F[x] \leq E$  where $F[x]$ is an $F$-vector space of $\infty$ dimension. 

<u>Example</u>: $\pi, e \in \mathbb{R}$ are transcendental elements with respect to $\mathbb{Q}$. 

---

Let's now discuss the second option.
$$
\text{Ker}(\text{ev}_\alpha) = (f) \quad \quad f \text{ is irreducible}
$$
We also know the following.
$$
F[\alpha]\cong  \underbrace{F[x]/(f)}_{\text{field}}
$$
Thus, we have
$$
F \leq F[\alpha] = \underbrace{F(\alpha)}_{\text{Frac}\;F[x]} \leq E
$$
This means that $[F(\alpha) : F] = \deg f$​. 

**Definition:** If $\text{Ker}(\text{ev}_\alpha) = (f)$, then $\alpha$ is called an algebraic element of $F$. 

- The <u>monic</u> polynomial $f$ is called an irreducible polynomial of $\alpha$ with respect to $F$, denoted $\text{irr}(\alpha, F)$

<u>Example</u>: $\mathbb{Q} \leq \mathbb{R}$, $\alpha = \sqrt{2}$ 

We know that $\alpha$ is algebraic, $\text{irr}(\sqrt{2},\mathbb{Q}) = x^2 - 2$
$$
\mathbb{Q}(\sqrt{2}) \leq R \implies \text{irr}\left(\sqrt{2},\mathbb{Q}\left(\sqrt{2}\right)\right) = x - \sqrt{2}
$$

----

**Proposition:** $F \leq K \leq E$, then $[E: F] = [E : K] \cdot [K:F]$. Moreover, if $\{\alpha_1, \dots, \alpha_n\}$ is a basis of $K$ over $F$ and $\{\beta_1, \dots \beta_n\}$ is a basis of $E$ over $K$, then $\{\alpha_1\beta_1, \dots, \alpha_1\beta_n, \alpha_2\beta_1, \dots, \alpha_n\beta_n\}$ is the basis of $E$ over $F$ 

**Proof:** (spanning property of the basis)

Any $e \in E$ can be written as 
$$
e = \sum_{i=1}^\infty c_i\beta_i \quad \text{ where } \quad c_i \in K, \beta_i \in E
$$
Any $c_i \in K$ can be written as $c_i = \sum_{j=1}^n d_{ij} \alpha_j$ where $d_{ij} \in F$, $\alpha_j \in K$. This means that any element $e \in E$ can be written as 
$$
e = \sum_{i=1}^m \sum_{j=1}^n \underbrace{d_{ij}}_{\in F}\cdot  \alpha_i\beta_j
$$
To finish the proof, you must show that it is linearly independent. 

**Definition:** Let $F \leq E$, $\alpha_1, \dots \alpha_n \in E$. Then, $F(\alpha_1, \dots, \alpha_n)$ is the smallest subfield of $E$ containing $F$ and $\alpha_1, \dots, \alpha_n$. 

- "smallest" means that $F (\alpha_1, \dots, \alpha_n) = \bigcap_{K \leq E,\; F \leq K, \;\alpha_i \in K} K \leq E$ 

<u>Example</u>: Consider $\mathbb{Q} \leq \mathbb{Q}(\sqrt{2}) \leq \mathbb{Q}(\sqrt{2},\sqrt{3})$. 
$$
\underbrace{[\mathbb{Q}(\sqrt{2}) : \mathbb{Q}]}_{\{a+b\sqrt{2}\},\;a,b\in \mathbb{Q}} = 2 \iff \text{irr}\left(\sqrt{2}, \mathbb{Q}\right) = x^2 - 2 \iff \dim_{\mathbb{Q}} \mathbb{Q}(\sqrt{2}) = \deg(x^2 - 2)
$$

$$
[\underbrace{\mathbb{Q}(\sqrt{2},\sqrt{3})}_{\mathbb{Q}(\sqrt{2})(\sqrt{3})} : \mathbb{Q}(\sqrt{2})] = 2 \iff \text{irr}(\sqrt{3},\mathbb{Q}(\sqrt{2}) = x^2 - 3 \iff \deg(x^2 - 3)
$$

Finally, to clean up part $(11)$, you need to show that $\sqrt{3} \neq a + b \sqrt{2}$. 

By the above proposition, $[\mathbb{Q}(\sqrt{2}, \sqrt{3}) : \mathbb{Q}] = 2 \cdot 2  = 4$ 

**Direct Proof:** Consider $\alpha = \sqrt{2 } + \sqrt{3}$. 

First, we know $\alpha^2 = 5 + 2\sqrt{6} \implies \sqrt{2} = \frac{\alpha^3 - 9\alpha^2}{{2}}$​ 

Next, we know $\alpha^3 = 11\sqrt{2} + 9 \sqrt{3} \implies \sqrt{3} = \frac{\alpha^3 - 11\alpha}{-2}$. 

This also impleis that $\sqrt{2}, \sqrt{3} \in \mathbb{Q}(\sqrt{2} + \sqrt{3})$ and $\sqrt{2} + \sqrt{3} \in \mathbb{Q}(\sqrt{2},\sqrt{3})$, then 
$$
\mathbb{Q}(\sqrt{2} + \sqrt{3}) = \mathbb{Q}(\sqrt{2},\sqrt{3})
$$
Since $1, \alpha, \alpha^2, \alpha^3, \alpha^4$ are linearly dependent $\implies \exists$ degree $4$ polynomial $f$ with $\mathbb{Q}$-coefficients such that $f(\alpha) =  0$ and there is no polynomial of smaller deg $\implies \mathbb{Q}(\sqrt{2} + \sqrt{3}) = \mathbb{Q}[x]/(f)$.
$$
[\mathbb{Q}(\sqrt{2}, \sqrt{3}) : \mathbb{Q}] = \deg(f)  = 4
$$

---

**Definition:** $F \leq E$ is a <u>simple</u> extension if $\exists\;\alpha \in E$ such that $E = F(\alpha)$. 

- $\mathbb{Q}(\sqrt{2},\sqrt{3}) = \mathbb{Q}(\sqrt{2} + \sqrt{3})$ is a simple extension.

**Definition:** $F \leq E$ is an <u>algebraic extension</u> if every $\alpha \in E$ is algebraic over $F$. 

**Proposition:** Two parts. 

1. Every finite degree extension is algebraic. (Also, finite degree extensions can not have transcendental elements)
2. Every (algebraic) extension of finite degree is of the form $E = F(\alpha_1, \dots, \alpha_n)$, where $\alpha_1, \dots, \alpha_n \in E$. 
