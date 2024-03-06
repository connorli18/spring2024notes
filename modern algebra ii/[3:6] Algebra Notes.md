# [3/6] Algebra Notes

#### Last Time

Define $F \leq E$ where $E$ is a splitting field of $f \in F[x]$. 

**Theorem:** Let $E, E'$ be two splitting fields of the same polynomial, then 

1) $\exists \;\sigma : E \rightarrow^\cong E'$ 
2) If $f$ is <u>separable</u>, then there are exactly $[E:F]$ such isomorphisms $\sigma$. 

<u>Recall</u>: If $f \in F[x] \rightarrow \sigma_0 (f) \in F'[x]$ where $f$ is irreducible, then $f(\alpha) = 0$ and $\sigma(f)(\alpha') = 0$.

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-03-06 at 2.48.35 PM.png" alt="Screenshot 2024-03-06 at 2.48.35 PM" style="zoom:50%;" /> <img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-03-06 at 2.49.11 PM.png" alt="Screenshot 2024-03-06 at 2.49.11 PM" style="zoom:50%;" />

**Definition:** $f \in F[x]$ is called separable if every irreudicble factor of $f$ has no multiple roots.

**Definition:** A field $F$ is called <u>perfect</u> if every polynomial $f \in F[x]$​ is separable.

<u>Remark</u>: Any field of characteristic $0$ is perfect. Any finite field is perfect. 

---

#### Galois Groups

**Definition:** $\text{Gal}(E/F) = \{\sigma \in \text{Aut}(E) \text{ such that } \sigma(\alpha) = \alpha, \;\forall \;\alpha \in F\}$ 

**Lemma:** Let $f \in F[x]$ and $\alpha \in E$ is a root of $f$, where $f(\alpha) = 0$. Then, for every $\sigma \in \text{Gal}(E/F)$, we have that $\sigma(\alpha)$ is also a root of $f$. 

**Proof:** $0 = f(\alpha) = \sum_{i=0}^n c_i \alpha^i$ where $c_i \in F$. Since we are using group homomorphisms/automorphisms, we can write
$$
\sigma(0) = \sigma(f(\alpha)) = \sum_{i=0}^n \sigma(c_i) \sigma\left(\alpha^i\right) = \sum_{i=0}^n c_i \sigma(\alpha)^i = f(\sigma(\alpha))
$$
This is because the Galois group fixes the coefficient field. 

---

**Theorem:** Let $F \leq E$ be a splitting field of a polynomial $f \in F[x]$ where $f$ is of degree $n$. Then, $\text{Gal}(E/F) \leq S_n$. 

**Proof:** Since $E$ is a splitting field of $f$, we can write $f$ as a product of linear factors
$$
f = c(x - \alpha_1) \cdots (x - \alpha_n)
$$
Now, define a map $\psi : \text{Gal}(E/F) \rightarrow S_n$ by
$$
\sigma \rightarrow 
\begin{pmatrix} 
\alpha_1 & \cdots & a_n\\
\sigma(\alpha_1) &  \cdots & \sigma(\alpha_n) 
\end{pmatrix}
$$
This map is well-defined by the lemma because image of every root is mapped to a root, and it is a group homomorphism by construction. $E = F (\alpha_1, \dots, \alpha_n)$ so if $\sigma(\alpha_i) = \alpha_i$ for every root $\alpha_i$, then $\sigma(\alpha) = \alpha$ for any $\alpha \in E$ so $\text{Ker} \psi = \{\text{id}\}$ and $\psi$ is an injective homomorphism. 

<u>Example 1</u>: $\text{Gal} ( \mathbb{C} / \mathbb{R}) = \{\text{id}, z \rightarrow \overline{z}\}$

Since $\mathbb{C}$ is a splitting field of $x^2 + 1$. By the theorem, 
$$
\text{Gal}(\mathbb{C}/\mathbb{R}) \leq S_2 = \mathbb{Z}/2\mathbb{Z} = 
\left\{
\begin{pmatrix}
i & -i\\
i & -i
\end{pmatrix},
\begin{pmatrix}
-i & i\\
i & -i
\end{pmatrix}
\right\}
$$
<u>Example 2</u>: $\text{Gal}(\mathbb{Q}(\sqrt{n})/\mathbb{Q})$

We have that $\mathbb{Q}(\sqrt{n})$ is a splitting field of $x^2 - n$, so by the theorem,
$$
\text{Gal} (\mathbb{Q}(\sqrt{n})) \leq S_2  = \left\{\begin{pmatrix}
\sqrt{n} & -\sqrt{n}\\
\sqrt{n} & -\sqrt{n}
\end{pmatrix},
\begin{pmatrix}
-\sqrt{n} & \sqrt{n}\\
\sqrt{n} & -\sqrt{n}
\end{pmatrix}\right\} \implies \text{Gal} (\mathbb{Q}(\sqrt{n}))  = S_2
$$
<u>Example 3</u>: Let $f = x^3 - 1 \in \mathbb{Q}[x]$ and let $E$ be a splitting field of this $f$. What is the $\text{Gal}(E / \mathbb{Q})$?
$$
x^3 - 1 = (x-1)\left(x - \overbrace{e^{\frac{2\pi i}{3}}}^{\omega}\right)\left(x - \overbrace{e^{\frac{4\pi i}{3}}}^{\omega^2}\right)
$$
This means that
$$
E = \mathbb{Q} \left(1, \omega, \omega^2\right) = \mathbb{Q}(\omega) = \mathbb{Q}[x]/(x^2 + x + 1) \implies [\mathbb{Q}(\omega) : \mathbb{Q}] = 2
$$
By the theorem from last class, the $\#$ of automorphisms of $E$ extending identity on $\mathbb{Q}$ is $[\mathbb{Q}(\omega): \mathbb{Q}] = 2 \implies$  $\text{Gal}\left(\mathbb{Q}(\omega)/\mathbb{Q}\right) = \{\text{id}, z\rightarrow \overline{z}\}  \cong S_2$ . 

<u>Example 4</u>: Let $f = x^3 - 2$ and $\mathbb{Q} = E =$ splitting field of $F$. 

We know that $f$ is irreducibe for $\mathbb{Q}$ but splits in $\mathbb{C}$ as
$$
x^3 - 2 = (x - \overbrace{\sqrt[3]{2}}^{\alpha}) (x - \omega \sqrt[3]{2}) (x - \omega^2 \sqrt[3]{2})
$$
We know that the roots are $\alpha, \alpha\omega, \alpha\omega^2$. This means that $E = \mathbb{Q}(\alpha, \alpha \omega, \alpha\omega^2) = \mathbb{Q}(\alpha, \omega)$. By the theorem, we have
$$
\text{Gal}(\mathbb{Q}(\alpha,\omega)/\mathbb{Q}) \leq S_3
$$
We can define $\sigma: \alpha \rightarrow \alpha \omega, \omega \rightarrow \omega$ where $\sigma \in \text{Gal}$. Also, define $\tau: \alpha \rightarrow \alpha, \omega \rightarrow \omega^2$​. 

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-03-06 at 3.38.25 PM.png" alt="Screenshot 2024-03-06 at 3.38.25 PM" style="zoom:50%;" />

The diagram implies that $\text{Gal} \leq S_3$ containing a cycle of length $3$ and a transposition $\implies \text{Gal} = S_3$.   

---

**Theorem:** Let $\mathbb{F}_q$ be a finite field with $q = p^n$, then $\text{Gal}(\mathbb{F}_q / \mathbb{F}_p) \cong \mathbb{Z}/n\mathbb{Z} = \langle \text{Fr}_p\rangle$ where $\text{Fr}_p (\alpha) = \alpha^p$ is a Frobenius homomorphism. 

**Proof:** Recall, that $\left(\mathbb{F}_q^*, \circ\right) \cong \left(\mathbb{Z}/(q-1)\mathbb{Z}, +\right)\implies$take a generator $\alpha \in \mathbb{F}_q^*$ such that every non-zero element of $\mathbb{F}_q$ is  $\alpha^k$ for some $\alpha$​. 
$$
\implies \mathbb{F}_q = \mathbb{F}_p (\alpha) \cong \mathbb{F}_p[x]/\underbrace{\text{irr}(\alpha, \mathbb{F}_p)}_f
$$

$$
\deg f = \dim_{\mathbb{F}_p} \mathbb{F}_q = n
$$

Since $\mathbb{F}_q$ is perfect, $\#$ of automoprhisms of $\mathbb{F}_q$ extending $\mathbb{F}_p$ is $n \implies \text{Gal} (\mathbb{F}_q / \mathbb{F}_p) = n$

<u>Remark</u>: Group of $n$-th roots of $1$ in $\mathbb{C}$ of order $n$ provide a multiplicative realization of $\mathbb{Z}/n\mathbb{Z}$. We also have $k, m \in \mathbb{Z}/n\mathbb{Z}$ where $e^{\frac{2\pi i k}{n}}, e^{\frac{2\pi i m}{n}} \in$ groups of $n$-th roots of $1$ in $\mathbb{C}$. 
$$
k + m \rightarrow e^{\frac{2\pi i k}{n}} \cdot e^{\frac{2\pi i m}{n}}
$$