# [2/28] Algebra Notes

#### Finite Fields (Continued)

- $F$ is a finite field $\implies \# F = p^n = q$

**Theorem:** For each such $q$, there exists a finite field $\mathbb{F}_q$ with $\# \mathbb{F}_q$ elements. 

**Proof Idea:** Consider $f = x^q - x$ in $\mathbb{F}_p[x]$. By Kronecker's Theorem, $\exists\;\mathbb{F}_p < E$ where $f = c(x-\alpha_1) \cdots (x-\alpha_q)$. It's important to note that $E$ is not completely constructive. 
$$
\mathbb{F}_q = \{\alpha \in E : \alpha^q - \alpha = 0\}
$$
We showed that $\mathbb{F}_q$ is a field. And, another way to describe $\mathbb{F}_q \leq E$ as 
$$
\mathbb{F}_q = \{\alpha \in E : \text{Fr}_q (\alpha) = \alpha\}
$$
The only elements of $\mathbb{F}_q$ are $\{\alpha_1, \dots, \alpha_q\}$. And, $\mathbb{F}_q$ has exactly $q$ elements if $x^q - x$ has no repeated roots. 

---

**Lemma:** Let $f,g \in F[x]$, then there exists a $\exists F \leq E$ and $\alpha \in E$ such that $f(\alpha) = g(\alpha) = 0 \iff (f,g) \neq 1$.  

**Proof:** Let $h = (f,g)$. There exists a field extension $F \leq E$ where $fg$ splits $\implies$ $f,g$ splits $\implies$ $h$ splits $\implies$ $\exists \alpha \in E$ such that $h(\alpha) = 0 \implies f(\alpha) = g(\alpha) = 0$.

The other direction is trivial. Assume that $\exists F \leq E$, $\alpha \in E$ such that $f(\alpha) = g(\alpha) = 0 \implies$ $(x-\alpha ) | f,g \in E[x] \implies \text{irr}(\alpha,F) | f,g$. 

<u>Reminder</u>: $\text{ev}_\alpha : F[x] \rightarrow E$, $\;\text{Ker}(\text{ev}_\alpha) = (\text{irr}(\alpha, F))$. 

---

**Lemma:** $f$ has a double root $\iff (f,f') = (f,D(f)) \neq 1$ in some extension.

<u>Intuition</u>: Left hand side means that $\exists F \leq E, \; \alpha \in E$ such that $f = (x-\alpha)^2 \cdot \tilde{f}$. Recall, $D(f)$ denotes an algebraic version of $\frac{d}{dx}$. 
$$
D(f) := D\left((x-\alpha)^2\right) \cdot \tilde{f} + (x-\alpha)^2 \cdot D(\tilde{f}) = 2(x-\alpha) \cdot \tilde{f} + (x-\alpha)^2 D(\tilde{f}) \iff (f,D(f)) \neq 1
$$
We will prove the other direction later ($\Longleftarrow$).

**Corollary:** $x^q - x \in \mathbb{F}_p[x]$ has no double root in any extension because
$$
D(x^q - x) = qx^{q-1} - 1 = p^n x^{q-1} - 1
$$
However, $p \cdot x = 0$ in any field of characteristic $p$ and $-1$ has no GCF except for $1$. Thus, this concludes the proof of the existence of $\mathbb{F}_q$ such that $\#\mathbb{F}_q = q$. 

**Remark:** $\mathbb{F}_q$ is a minimal subfield of $E$ where $x^q - x$ splits (if $K \leq \mathbb{F}_q \leq E$ ) such that $x^q -x $ splits $\implies$ $K = \mathbb{F}_q$. 

---

#### Splitting Fields

**Definition/Proposition:** Let $f \in F[x]$. The field $F \leq E$ is called a <u>splitting field</u> of $f$ if

1. $f$ splits in $E$ 
2. $f$ does not split in <u>any</u> subfield of $E$ 

In fact, if $f = c (x-\alpha_1) \cdots (x-\alpha_n)$, then $E = F(\alpha_1, \dots, \alpha_n) :=$ the minimal subfield of $E$ containing $F, \alpha_1, \alpha_2, \dots, \alpha_n$.  

**Proof:** If $f$ splits in $E$, then $\alpha_1, \dots \alpha_n \in E \implies F(\alpha_1, \dots, \alpha_n)$ . We need to prove that if $f$ splits in $K \leq F(\alpha_1, \dots, \alpha_n)$, then $K = F(\alpha_1,\dots,\alpha_n)$. If $K \neq F$, then $\exists \alpha_j \notin K$. But, then $K$ has not all the roots of $f$ in $E \implies f$ does not split in $K$. 

**Theorem:** If $F$ is a field with $q$ elements, then $F \cong \mathbb{F}_q$. 

---

**Lemma:** Let $F$ be a field with $q' \leq q$ elements, then $F \leq \mathbb{F}_q \iff q = (q')^k \iff p^m = q, (q')^k = p^n$ where $m | n \implies$ if $F \leq \mathbb{F}_q$, then $\mathbb{F}_q$ is an $F$-vector space, which means that as a vector space
$$
\mathbb{F}_q \cong F^k \quad \quad k > 0
$$
This also implies that $\# \mathbb{F}_q = (\# F)^k = (q')^k$. 

To prove the other direction, let $F$ be a field with $q'$ elements. We need to construct an injective homomorphism $G: F \rightarrow \mathbb{F}_q$. 

- $(F^*, \circ) \cong \left(\mathbb{Z}/(q'-1) \mathbb{Z}, +\right) \implies$ for any $\beta \neq 0 \in F$, then

$$
\beta^{q' - 1} = 1 \implies \forall \beta \in F, \;\beta^{q'} = \beta
$$

 Since $(q')^k = q, \;\beta^q = \beta$. This tells us that $\beta \in F \implies \beta$ is a root of $x^q - x \in \mathbb{F}_p[x] \implies$ $f = \text{irr}(\beta,\mathbb{F}_p) \;|\; x^q - x$ . 

In $\mathbb{F}_q$, $x^q - x = (x- \alpha_1) \cdots (x-\alpha_q)$ splits into linear factors. 
$$
\begin{align*}
x^q - x &= \text{irr}(\beta,\mathbb{F}_p) \cdot h \quad \quad \deg\left(\text{irr}(\beta,\mathbb{F}_p)\right) > 0
\end{align*}
$$
Each $\alpha_i$ is a root of either $\text{irr}(\beta,\mathbb{F}_p) $ or $h, \;\deg(h) < q$. This means $\exists \; \alpha_i$ which is a root of $\text{irr}(\beta,\mathbb{F}_p)$. This also means that $\text{irr}(\beta,\mathbb{F}_p) \in \left(\text{irr}(\alpha_i,\mathbb{F}_p)\right)$. Since both are irreducible and monic, then $\text{irr}(\beta,\mathbb{F}_p) = \text{irr}(\alpha_i,\mathbb{F}_p)$. 

Now consider $\text{ev}_{\alpha_i}$ and $\text{ev}_{\beta}$.
$$
\text{ev}_{\alpha_i} : \mathbb{F}_p[x] \rightarrow \mathbb{F}_q \quad \quad \text{Ker} (\text{ev}_{\alpha_i}) = \text{irr}(\alpha_i,\mathbb{F}_p)
$$

$$
\text{ev}_{\beta} : \mathbb{F}_p[x] \rightarrow F \quad \quad \text{Ker}(\text{ev}_\beta) = \text{irr}\left(\beta,\mathbb{F}_p\right)
$$

Since $F^*$ is cyclic, we can choose $\beta$ to be its generator. Then, $\text{ev}_{\beta} : \mathbb{F}_p[x] \rightarrow F$ is surjective $\implies$by the first homomorphism theorem, we have the folllowing. 
$$
F \cong \mathbb{F}_p[x] / \text{irr}\left(\beta,\mathbb{F}_p\right)
$$
By the first homomorphism theorem, $\Im(\text{ev}_{\alpha_i}) \leq \mathbb{F}_q$ and the following result.
$$
\big(\Im(\text{ev}_{\alpha_i}) \cong \mathbb{F}_p[x] / \text{irr}\left(\beta,\mathbb{F}_p\right) \cong F \big) \leq \mathbb{F}_q
$$
**Remark:** This isomorphism is far from unique in general. 

---

**Proof (Theorem):** By the lemma, if $F$ has $q$ elements, then $F \leq \mathbb{F}_q$, both have $q$ elements $\implies F \cong \mathbb{F}_q$. 

---

#### Galois Groups

**Definition:** An <u>automorphism</u> of $F$ is an isomorphisms of $F$ to itself. 

<u>Example</u>: Let $F = \mathbb{C}$, consider the map $G: \mathbb{C} \rightarrow \mathbb{C}$ such that $G(z) = \bar{z}$. We saw that this is a homomorphisms since $\overline{z + w} = \overline{z} + \overline{w}$ and $\overline{z \cdot w} = \overline{z} \cdot \overline{w}$ . We also know that $G$ is bijective $\implies$ $G$ is an automorphism.

- Automorphisms of $F$ form a group $\text{Aut}(F)$ if $G,\tau \in \text{Aut}(F)$, then $G \cdot \tau$ is an automorphisms defined by $G \cdot \tau (r) = G(\tau(r))$

**Definition:** Let $F \leq E$ be a field extension. The Galois group of $E$ over $F$ denoted $\text{Gal} (E/F) \subset \text{Aut}(E)$ that preserve $F$. In other words,
$$
\text{Gal}(E/F) = \{G \in \text{Aut}(E) \;: \;\forall r \in F, \; G(r) = r\}
$$
<u>Example</u>: $G = $ complex conjugation $\in \text{Gal}(\mathbb{C}/\mathbb{R})$ where $\overline{z} = z$ for any $z \in \mathbb{R}$. Later, we will see that $\text{Gal}(\mathbb{C}/\mathbb{R}) = \{\text{id}, G\}$. 

<u>Example</u>: $\text{Gal}(\mathbb{Q}(\sqrt{2}),\mathbb{Q}) \cong \left\{\text{id}, \;\left(a + \sqrt{2}b \mapsto a-\sqrt{2}b\right)\right\}$. 