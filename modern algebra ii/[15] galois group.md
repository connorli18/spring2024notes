# Galois Group

**Definition:** An **automorphism** of $F$ is an isomorphism of $F$ with itself.

**Example:** Let $F = \C$. Consider the map $G : \C \to \C$ defined by $G(z) = \overline{z}$. We say that it is a homomorphism:
$$
\overline{(z + w)} = \overline{z} + \overline{w} \\
\overline{(z \cdot w)} = \overline{z} \cdot \overline{w}
$$
$G$ is bijective, so it is an automorphism.

The automorphisms of $F$ form a group $\text{Aut}(F)$: if $\sigma, \tau \in \text{Aut}(F),$ then $\sigma \cdot \tau$ is an automorphism defined by
$$
\sigma \cdot \tau(r) = \sigma(\tau(r))
$$
**Definition:** Let $F \leq E$ be a field extension. The **Galois group** of $E$ over $F$, $\text{Gal}(E / F) \subset \text{Aut}(E)$ is the set of automorphisms of $E$ that preserve $F$. In other words,
$$
\text{Gal}(E/F)
= \{G \in \text{Aut}(E) : \forall r \in F, G(r) = r\}
$$
**Example:** $G = $ complex conjugation $\in \text{Gal}(\C/\R)$, since $\overline{z} = z$ for any $z \in \R$. Later, we shall see that $\text{Gal}(\C/\R) = \{\text{id}, G\}$.

**Example:** $\text{Gal}(\Q(\sqrt{2})/\Q) \cong \{\text{id}, (a + b\sqrt{2} \mapsto a - b\sqrt{2})\}$.

## Preservation of Roots

**Lemma:** Let $f \in F[x]$ and let $\alpha \in E$ be a root of $f$. Then, for every $\sigma \in \text{Gal}(E / F)$, $\sigma(\alpha)$ is also a root of $f$.

**Proof:** In $E$,
$$
0
= f(\alpha)
= \sum_{i=1}^n c_i\alpha^i \quad c_i \in F
$$
Applying an automorphism $\sigma \in \text{Gal}(E / F)$,
$$
0
= \sigma(0)
= \sigma(f(\alpha))
= \sum_{i=0}^n \sigma(c_i)\sigma(\alpha^i)
= \sum_{i=0}^n c_i\sigma(\alpha)^i
= f(\sigma(\alpha))
$$
where $\sigma(c_i) = c_i$ because $\sigma$​ is an automorphism.

## Splitting Fields

**Theorem:** Let $F \leq E$ be a splitting field of a polynomial $f \in F[x]$ where $f$ is of degree $n$. Then, $\text{Gal}(E / F) \leq S_n$.

**Proof:** Since $E$ is a splitting field,
$$
f = c(x - \alpha_1) \cdots (x - \alpha_n)
$$
Define a map $\psi : \text{Gal}(E / F) \to S_n$ by
$$
\sigma \mapsto \begin{pmatrix}
	\alpha_1 & \cdots & \alpha_n \\
	\sigma(\alpha_1) & \cdots & \sigma(\alpha_n) \\
\end{pmatrix}
$$
This map is well-defined by the lemma and is a group homomorphism. Since $E = F(\alpha_1, \ldots, \alpha_n)$, if $\sigma(\alpha_i) = \alpha_i$ for every root $\alpha_i$, then $\sigma(\alpha) = \alpha$ for any $\alpha \in E$, so $\ker\psi = \{\text{id}\}$ and $\psi$​ is an injective homomorphism.

### Examples

**Example:** Compute $\text{Gal}(\C/\R)$.

First, $\text{Gal}(\C/\R) \supset \{\text{id}, z \mapsto \overline{z}\}$. Also, $\C$ is the splitting field of $x^2 + 1 = (x + i)(x - 1)$. By the theorem,
$$
\text{Gal}(\C/\R) \leq S_2 = \Z/2\Z = \qty{
	\begin{pmatrix}
		i & -i \\
		i & -i \\
    \end{pmatrix},
		\begin{pmatrix}
		i & -i \\
		-i & i \\
    \end{pmatrix}
}
$$
Therefore, $\text{Gal}(\C/\R) = \{\text{id}, z \mapsto \overline{z}\}$.

**Example:** Compute $\text{Gal}(\Q(\sqrt{n})/\Q)$, where $n$ is not a square.

$\Q(\sqrt{n})$ is a splitting field of $x^2 - n$, so by the theorem,
$$
\text{Gal}(\Q(\sqrt{n})/\Q) \leq S_2 = \qty{
	\begin{pmatrix}
		\sqrt{n} & -\sqrt{n} \\
		\sqrt{n} & -\sqrt{n} \\
    \end{pmatrix},
		\begin{pmatrix}
		\sqrt{n} & -\sqrt{n} \\
		-\sqrt{n} & \sqrt{n} \\
    \end{pmatrix}
} = \qty{\text{id}, a + b\sqrt{n} \mapsto a - b\sqrt{n}}
$$
**Example:** Let $f = x^3 - 1 \in \Q[x]$. Let $\Q \leq E$ be the splitting field of $f$. What is $\text{Gal}(E / \Q)$?

Let $\omega = e^{2\pi i/3}$. Then,
$$
f
= x^3 - 1
= (x - 1)(x - \omega)(x - \omega^2)
$$
Therefore, $E = \Q(1, \omega, \omega^2) = \Q(\omega) \cong \Q[x]/(x^2 + x + 1)$.

We know $[\Q(\omega) : \Q] = 2$. By the theorem from last class, the number of automorphisms of $E$ extending identity on $\Q$ is $[\Q(\omega) : \Q] = 2$, so $|\text{Gal}(\Q(\omega) / \Q)| = 2|$.

**Example:** $f = x^3 - 2$ and $\Q \leq E = $ splitting field of $f$. What is $\text{Gal}(E/\Q)$?

$f$ is irreducible in $\Q$. If we let $\alpha = \sqrt[3]{2}$, then $f$ splits in $\C$ as
$$
x^3 - 2
= (x - \sqrt[3]{2})(x - \sqrt[3]{2}\omega)(x - \sqrt[3]{2}\omega^2)
= (x - \alpha)(x - \alpha\omega)(x - \alpha\omega^2)
$$
The splitting field is $E = \Q(\alpha, \alpha\omega, \alpha\omega^2) = \Q(\alpha, \omega)$. By the theorem,
$$
\text{Gal}(\Q(\alpha, \omega)/\Q) \leq S_3
$$
Define $\sigma, \tau \in \text{Gal}(\Q(\alpha, \omega)/\Q)$ by
$$
\begin{align*}
    \sigma(\alpha) &= \alpha\omega \quad \sigma(\omega) = \omega \\
    \tau(\alpha) &= \alpha  \quad \tau(\omega) = \omega^2 \\
\end{align*}
$$
 Since $\sigma \circ \sigma \circ \sigma = \text{id}$, $\text{Gal}(\Q(\alpha, \omega) / \Q)$ contains a cycle of length $3$ and a transposition, so $\text{Gal}(\Q(\alpha, \omega) / \Q) = S_3$.

### Splitting Subfields

**Theorem:** Let $F \leq B \leq E$, where $B$ and $F$ are splitting fields of some polynomials. Then,
$$
\text{Gal}(B/F) \cong \text{Gal}(E/F) / \text{Gal}(E/B)
$$
**Example:** Let $E \cong \Q(\alpha, \omega)$ be the splitting field of $x^3 - 2$. Consider
$$
\underbrace{\Q}_F \leq \underbrace{\Q(\omega)}_B = \text{splitting field of $x^3 - 1$} \leq \underbrace{\Q(\alpha, \omega)}_E = \text{splitting field of $x^3-2$}
$$
We know that

- $\text{Gal}(E / F) \cong S_3$
- $\text{Gal}(B/F) \cong \Z_2$
- $\text{Gal}(E/B) = A_3$, since it explicitly consists of $\sigma \in \text{Aut}(E/F)$ that fix $\omega$

and we see that $\Z_2 \cong S_3 / A_3$.

## Finite Fields

**Theorem:** Let $\mathbb{F}_q$ be a finite field with $q = p^n$. Then,
$$
\text{Gal}(\mathbb{F}_q/\mathbb{F}_p) \cong \Z/n\Z = \langle \text{Fr}_p \rangle
$$
where $\text{Fr}_p(\alpha) = \alpha^p$ is the Frobenius homomorphism such that for $\alpha, \beta$ in a field of characteristic $p$,

$$
\text{Fr}_p(\alpha + \beta) = \text{Fr}_p(\alpha) + \text{Fr}_p(\beta)
$$
**Proof:** Recall that the group $(\mathbb{F}_q^*, \cdot) \cong (\Z/(q-1)\Z, +)$, so we can take a generator $\alpha \in \mathbb{F}_q^*$ such that every nonzero element of $\mathbb{F}_q$ equals $\alpha^k$ for some $k$.

>  **Remark:** Group of $n$ roots of unity (in $\C$) of order $n$ provide a multiplicative realization of $\Z/n\Z$.

Since $\text{ev}_\alpha : \mathbb{F}_p[x] \to \mathbb{F}_q$ is surjective, $\mathbb{F}_q = \mathbb{F}_p(\alpha) \cong \mathbb{F}_p[x] / \text{irr}(\alpha, \mathbb{F}_p)$. Let $f = \text{irr}(\alpha, \mathbb{F}_p)$. Then,
$$
\deg f = \dim_{\mathbb{F}_p} \mathbb{F}_q = n
$$
Since $\mathbb{F}_q$ is perfect, the number of automorphisms of $\mathbb{F}_p(\alpha) = \mathbb{F}_q$ that fix $\mathbb{F}_p$ is $[\mathbb{F}_p(\alpha) : \mathbb{F}_p] = n$, so
$$
|\text{Gal}(\mathbb{F}_q/\mathbb{F}_p)| = n
$$
We know that $\text{Fr}_p(\alpha) = \alpha$ for $\alpha \in \mathbb{F}_p$ and is an automorphism of $\mathbb{F}_q$, so $\text{Fr}_p \in \text{Gal}(\mathbb{F}_q / \mathbb{F}_p)$. Also,
$$
\text{Fr}_p \circ \text{Fr}_p \circ \cdots \circ \text{Fr}_p(\alpha) =  (\text{Fr}_p)^k(\alpha) = \alpha^{p^k}
$$
and $\alpha^{p^k} \neq \alpha$ if $k < n$, so $(\text{Fr}_p)^k \neq \text{id}$ for all $k < n$. Therefore, $\text{Fr}_p$ generates the entire group and $\text{Gal}(\mathbb{F}_q/\mathbb{F}_p) \cong \langle \text{Fr}_p \rangle$.

## Irreducible Polynomials

**Proposition:**

1. If $f \in F[x]$ is an irreducible polynomial and $F \leq E$ is its splitting field, then $\text{Gal}(E/F)$ acts transitively on the set of roots.
    - That is, if $f(\alpha) = f(\beta) = 0$, then there exists $\sigma \in \text{Gal}(E/F)$ such that $\sigma(\alpha) = \beta$
2. If $f$ has no double roots and $\text{Gal}(E/F)$ acts transitively on the set of roots, then $f$ is irreducible.

**Proof of 1:** Let $f(\alpha) = f(\beta) = 0$. There exists an automorphism of $F[x] / (f) = F(\alpha) = F(\beta)$ sending $\alpha$ to $\beta$ and fixing $F$.

**Proof of 2:** Use proof by contradiction: assume $f = gh$ where $\deg g, \deg h \geq 1$ and $g(\alpha) = 0$ for $\alpha \in E$. If the Galois action is transitive on the roots of $f$, then for every $\beta$ such that $h(\beta) = 0$, there exists $\sigma \in \text{Gal}(E/B)$ such that $\sigma(\alpha) = \beta$. But, $g(\sigma(\alpha)) = 0$, so $\sigma(\alpha)$ is a root of both $g$ and $h$, so $f = gh$ has a double root $\sigma(\alpha)$.

## Roots of Unity

**Definition:** A **root of unity** is a root of $x^n - 1$.

In general, we will be interested in radicals of arbitrary elements, roots of $x^n - c$ where $c \in F$. If $\alpha^n = c$, then $(\omega\alpha)^n = c$, for any $\omega$ such that $\omega^n = 1$. Moreover, in its splitting field,[^1]
$$
x^n - c
= \prod_{i=0}^{n-1} (x - \omega^i\alpha)
$$
**Definition:** For a ring $R$, $U(R)$ is its multiplicative group of roots of $1$.

- If $\alpha^n = 1$ and $\beta^m = 1$, then $(\alpha\beta)^{nm} = 1$.

- We call $\alpha \in U(R)$ a **primitive $n$-th root of unity** if $\alpha^n = 1$ but $\alpha^k \neq 1$ for all $k < n$.
    - In other words, $\alpha$ generates all the $n$-th roots of unity.


**Example:** $U(\C) = \{e^{2\pi in/m} : n, m \in \Z, m \neq 0\}$.

**Example:** $U(\R) = \{1, -1\}$.

In $\C$, the primitive $n$-th roots of unity is $e^{2\pi i/n}$ or $e^{2\pi im/n}$, where $\gcd(m, n) = 1$​.
$$
U(\Z/n\Z) = \{i \in \Z/n\Z : \gcd(n, i) = 1\}
$$
**Proof:** $i\alpha + n\beta = 1$ if $\gcd(n, i) = 1$.

**Example:** $U(\Z/p\Z) = U(\mathbb{F}_p) = \mathbb{F}_p^*$​​.

### Fields Adjoined with Roots of Unity

**Theorem:** Let $F \leq E = F(\alpha)$, where $\alpha$ is a primitive $m$-th root of unity. Then, $\text{Gal}(E/F) \leq U(\Z/m\Z)$. (That is, there exists an injective homomorphism.)

**Proof:** Consider $\sigma \in \text{Gal}(E/F)$. Then, $\sigma(\alpha)^m = \sigma(\alpha^m) = 1$. Therefore, $\sigma(\alpha) = \alpha^i$ for some $i$, and denote this $\sigma$ by $\sigma_i$. Moreover, $(i, m) = 1$.

- If $(i, m) \neq 1$, then $\sigma(\alpha)^{m/(i, m)} = \alpha^{i \cdot m/(i, m)} = 1$, contradicting the fact that $\sigma(\alpha)$ has order $m$.

Define a map $\psi : \text{Gal}(E/F) \to U(\Z/n\Z)$ by $\sigma_i \to i$​.

**Claim:** $\psi$ is an injective group homomorphism.

**Proof:** $\psi(\sigma_1) = 1$ and
$$
\sigma_i \circ \sigma_j(\alpha) = \sigma_i(\alpha^j) = (\alpha^j)^i = \alpha^{ji} \\
\sigma_i \circ \sigma_j = \sigma_{ij} \implies \underbrace{\psi(\sigma_i \circ \sigma_j)}_{ij} = \psi(\sigma_{ij}) = ij
$$
To show it is injective, we notice that if $\psi(\sigma) = 1$, then $\sigma = \sigma_1 = \text{id} \in \text{Gal}(E/F)$.

> **Remark:** In particular, $\text{Gal}(E/F)$ is abelian.

**Example:** Consider $x^3 - 2$​. We already showed that
$$
\text{Gal}(\Q(\sqrt[3]{2}, e^{2\pi i/3})/\Q) \cong S_3 \\
\text{Gal}(\Q(\sqrt[3]{2}, e^{2\pi i/3})/\Q(e^{2\pi i/3})) \cong \Z/3\Z = A_3
$$
and we know
$$
\text{Gal}(\Q(e^{2\pi i/3})/\Q) \cong \Z/2\Z \cong U(\Z/3\Z)
$$

> **Goal:** generalize this observation.

### Polynomials and Roots of Unity

**Theorem:** Let $f = x^n - c \in F[x]$ and let $F \leq E$ be the splitting field of $f$.

1. If $F$ contains $n$-th roots of unity, then $\text{Gal}(E/F) \leq (\Z/n\Z, +)$
2. If $\text{Gal}(E/F) \cong (\Z/n\Z, +)$ and $\text{char}(F) \nmid n $ (this is needed so $f$ does not have double roots), then $f$ is irreducible.

**Proof of 1:** Let $E = F(\alpha, \omega)$,[^2] where $\alpha$ is a root of $f$ and $\omega \in F$ is a primitive $n$-th root of unity.

If $\alpha$ is a root of $f$ and $\xi$ is an $n$-th root of unity, then $\alpha\xi$ is a root of unity, since
$$
(\alpha\xi)^n = \alpha^n\xi^n = \alpha^n = c
$$
Moreover, if $\alpha, \beta$ are roots of $f$, then $\alpha/\beta$ is a root of unity, since
$$
(\alpha/\beta)^n = \alpha^n/\beta^n = c/c = 1
$$
so every root of $f$ is of the form $\alpha \cdot \omega^i$, where $\omega$ is a primitive $n$-th root of unity.

Let $\sigma \in \text{Gal}(E/F)$. Then, $\sigma(\text{root}) = \text{root}$, so $\sigma(\alpha) = \alpha \cdot \omega^i$ for some $i \in \Z/n\Z$. We call such an $\sigma$ by $\sigma_i$, and define a homomorphism
$$
\chi : \text{Gal}(E/F) \to (\Z/n\Z, +)
$$
by $\sigma_i \to i$​. Next, I claim $\chi$ is an injective homomorphism.

First, $\chi$ is a homomorphism, because

- $\text{id}(\alpha) = \alpha \cdot \omega^0$. $\text{id} = \sigma_0$ so $\chi(\sigma_0) = 0$.
- $\sigma_i \circ \sigma_j(\alpha) = \sigma_i(\alpha\omega^j) = \sigma_i(\alpha)\sigma_i(\omega)^j = \alpha\omega^i\omega^j = \alpha\omega^{i+j} = \sigma_{i+j}(\alpha)$. Therefore, $\chi(\sigma_i \circ \sigma_j) = i + j$.

Also, $\chi$ is injective for the same reason as the previous theorem: if $\chi(\sigma) = 0$, then $\sigma = \sigma_0 = \text{id}$.

**Proof of 2:** If $\chi$ is surjective, then $\text{Gal}(E/F)$ acts transitively. If $f$ has no double roots, then by a proposition we proved earlier, $f$​ is irreducible.

> **Remark:** In particular, $\text{Gal}(E/F)$ is cyclic (under assumptions of the theorem).

**Corollary:** If $n = p$ is prime, then $\text{Gal}(E/F) \leq \Z/p\Z$.

1. $\text{Gal}(E/F) = \{1\}$ and $x^p - c$ splits in $F = E$.
2. $\text{Gal}(E/F) \cong \Z/p\Z$ and $x^p - c$ is irreducible.

[^1]: In this case, $\omega$ must be a primitive $n$-th root of unity.
[^2]: Notice that $F(\alpha, \omega) = F(\alpha)$ since we assume that $\omega \in F$ in this part.
