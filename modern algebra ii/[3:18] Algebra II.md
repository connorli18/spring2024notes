# [3/18] Algebra II

#### Review

**Definition:** If $F \leq E$ field extension. $\text{Gal}(E/F) = \{\sigma \in \text{Aut}(E): \sigma(\alpha) = \alpha \;\text{ for every }\alpha \in F\}$. 

<u>Example(s):</u>

- $\text{Gal}(\mathbb{C}/\mathbb{R}) = \{\text{id}, z \mapsto \overline{z}\}$ 
- $\text{Gal}(\mathbb{Q}(\sqrt{2})/\mathbb{Q}) = \{\text{id}, a+b\sqrt{2} \mapsto a-b\sqrt{2}\}$ 
- $\text{Gal}(\mathbb{R}/\mathbb{Q})$ is infinite
- $\text{Gal}(E/Q) \cong S_3$ where $E = $ splitting field of $x^3 - 2$. For the below, consider $\alpha = \sqrt[3]{2}$ and $\omega = e^{\frac{2\pi i }{3}}$.

$$
x^3 - 2 = (x-\alpha) \cdot (x-\alpha\omega) \cdot(x-\alpha\omega^2)
$$

**Recall:** If $f(\alpha) = 0$ and $f \in F[x]$, for $\alpha \in E$, then for every $\sigma \in \text{Gal}(E/F)$, $f(\sigma(\alpha)) = 0$. 

**Theorem:** If $F \leq B \leq E$, where $B$ and $F$ are splitting fields of some polynomials, then
$$
\text{Gal}(B/F) \cong \text{Gal}(E/F) /\text{Gal}(\underbrace{E/B}_{\text{normal subgroup}})
$$
<u>Example:</u> Let $E$ be the splitting field of $x^3 - 2$. Then, we know that $E \cong \mathbb{Q}(\alpha,\omega)$. Now, consider $\underbrace{\mathbb{Q}}_{F} \leq \underbrace{\mathbb{Q}(\omega)}_{B} \leq \underbrace{\mathbb{Q}(\alpha, \omega)}_{E}$. 

Since we know that $\text{Gal}(E/F) \cong S_3$. We can consider $B$ as the splitting field of $x^3 - 1$ and $E$ as the splitting field of $x^3 - 2$. This means that $\text{Gal}(B/F) \cong \mathbb{Z}/2\mathbb{Z}$ and $\text{Gal}(E/B) = A_3$. 
$$
\mathbb{Z}/2\mathbb{Z} \cong S_3/A_3
$$
We also know that $\text{Gal}(E/B)$ explicitly consists of $\sigma \in \text{Aut}(E/F)$ that fix $\omega$. 

----

**Theorem:** $\text{Gal}(\mathbb{F}_q/\mathbb{F}_p) = \langle \text{Fr}_p \rangle \cong \mathbb{Z}_n$. Recall, where $\text{Fr}_p(\alpha) = \alpha^p$. 

**Proof:** $\mathbb{F}_q^* \cong \mathbb{Z}/(q-1)\mathbb{Z}$, so there is a generator $\alpha \in \mathbb{F}_q^*$ such that every non-zero element in $\mathbb{F}_q$ is $\alpha^k$ for some $k$. In particular, $\mathbb{F}_q = \mathbb{F}_p[x] / \left(\text{irr}(\alpha, \mathbb{F}_p)\right)$ and we will call this irreducible polynomial $f$. 

Now, we have that $\mathbb{F}_p[x] \rightarrow^{\text{ev}_\alpha} \mathbb{F}_q$ is surjective. This also means that $\deg f = \dim_{\mathbb{F}_p}\mathbb{F_q} = n$. Remember that the number of automorphisms of $\mathbb{F}_p(\alpha)$ that fix $\mathbb{F}_p = \left[\mathbb{F}_p(\alpha) : \mathbb{F}_p\right] = n \implies |\text{Gal}(\mathbb{F}_q/\mathbb{F}_p)| = n$.

We need to show that $\text{Fr}_p \in \text{Gal}$ and that the order of $\text{Fr}_p$ is $n$. First, we show that $\text{Fr}_p(\alpha) = \alpha$ for $\alpha \in \mathbb{F}_p$ and is an automorphism of $\mathbb{F_q} \in \text{Fr}_q \in \text{Gal}(\mathbb{F}_q/\mathbb{F}_p)$. 
$$
\left(\text{Fr}_p\right)^k (\alpha) = \alpha^{p^k} \quad \text{   and   }\quad a^{p^k} \neq \alpha \text{ if } k < n
$$
The above means that $(\text{Fr}_p)^k \neq \text{id}$ for all $k < n$. 

---

**Proposition:** 1) If $f \in F[x]$ is an irreducible polynomial and $F \leq E$ is its splitting field $\implies \text{Gal}(E/F)$ acts transitively on the set of roots $(f(\alpha) = f(\beta) = 0 \implies \exists \;\sigma \in \text{Gal}(E/F)$ such that $\sigma(\alpha) = \beta$).

And 2) if $f$ has no double roots and $\text{Gal}(E/F)$ acts transitively on the set of roots, then $f$ is irreducible. 

**Proof:** 1) Let $f(\alpha) = f(\beta) = 0$. There exists an automoprhisms of $F[x]/(f) = F(\alpha) = F(\beta)$ sending $\alpha$ to $\beta$ and fixing $F$. 

And 2) Assume $f = g \cdot h$, where $\deg g, \deg h \geq 1$ and $g(\alpha) = 0$ where $\alpha \in E$. If the $\text{Gal}$ action is transitive on the roots of $f$, then for every $\beta$, $h(\beta) = 0 \; \exists\; \sigma \in \text{Gal}(E/B)$ such that $\sigma(\alpha) = \beta$. But $g(\sigma(x)) = 0$ so $\sigma(\alpha)$ is a root of both $g$ and $h \implies f = gh$ has a double root $\sigma(\alpha)$. 

#### Roots of Unity

A root of $1$ is a root of $x^n - 1$. In general, we will be interested in radicals of arbitrary elements, roots of $x^n - c$ where $c \in F$. 

If $\alpha^n - c \implies (\omega\alpha)^n = c$ for any $\omega$ since $\omega^n  = 1$. Moreover, in the splitting field $x^n - c = \prod_{i=0}^{n-1} (x - \omega^i \alpha)$. 

**Definition:** Let $R$ be a ring, we call $U(R)$ its multiplicative group of roots of $1$ (If $\alpha^n = 1, \beta^m = 1 \implies (\alpha\beta)^{nm} = 1$). 

We call $\alpha$ a <u>primitive</u> with root of $1$ is $\alpha^n = 1$, but $\alpha^k \neq 1$ for all $k < n$. 

- $U(\mathbb{C}) = \{e^{2\pi i \cdot q, \;q\in \mathbb{Q}}\}$
- $U(\mathbb{R}) = \{1,-1\}$  

In $\mathbb{C}$ primitive $n$-th root of $1$ is $e^{\frac{2\pi i}{n}}$ or $e^{2\pi i \frac{m}{n}}$ where $(m,n) = 1$. 

- $U(\mathbb{Z}/n\mathbb{Z}) = \{i \in \mathbb{Z}/n\mathbb{Z} : (n,i) = 1\}$ since $i\alpha + n\beta = 1$ if $(n,i) = 1$ 
- $U(\mathbb{Z}/p\mathbb{Z}) = U(\mathbb{F}_p) = \mathbb{F}_p^*$ 