# [3/4] Algebra Notes

#### Last Time

1. For everye $q = p^n$ there exists a finite field $\mathbb{F}_q$ with $q$ elements.
2. Every $2$ fields with $q$ elements are isomorphic
3. There are no other $f \cdot f -$ 

$$
\mathbb{F}_q = \mathbb{F}[x] / (p) \quad \quad p \text{ irred. of degree } n
$$

$$
\mathbb{F}_q = \text{splitting field of }x^q - x \text{ over } \mathbb{F}_p
$$

 **Reminder:** $E$ is a splitting field of $f \in F[x]$ if 

1. $f$ splits in $E$ and $f = c(x- \alpha_1) \cdots (x-\alpha_n)$
2. For any proper $F \leq B \leq E$, $f$ does not split

**Definition:** Assume $F \leq E$. 
$$
\text{Gal}(E / F) := \{G \in \text{Aut}(E) \text{ s.t. } G(\alpha) = \alpha, \;\forall \alpha \in F\}
$$
**Note:** We will mostly consider Galois groups of splitting fields of some polynomial. 

---

Recall, if $E$ is a splitting field of $f \in F[x]$, then $E = F(\alpha_1, \cdots, \alpha_n)$, where $\alpha$ are the roots of $f$. 

**Theorem:** Let $E, E'$ be splitting fields of $f \in F[x]$, then $\exists$ an isomorphism $\sigma: E \rightarrow E'$ that preserves $F$ pointwise. If $f$ is separable (to be defined in the proof), then there are exactly $[E:F]$ such isomoprhisms $\sigma$. 

**Proof:** Let's reforulate the statement.

Let $\sigma_0: F \rightarrow^{\cong} F'$, $f \in F[x]$. This implies that $\sigma_0(f) = \sum_i \sigma_0 (\alpha_i) x^i$ where $\sigma_0(f) \in F'[x]$. Define $E'$ as a splitting field of $\sigma_0(f)$. Then, 

1. $\exists$ an isomorphism $\sigma: E \rightarrow^\cong E'$ such that $\sigma|_{F \leq E} = \sigma_0$ $\iff \sigma(\alpha) = \sigma_0(\alpha) \text{ if } \alpha \in F \leq E$. 
2. if $f$ is <u>separable</u>, then there are $[E:F]$ such isomophisms. 

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-03-04 at 3.10.03 PM.png" alt="Screenshot 2024-03-04 at 3.09.55 PM" style="zoom:33%;" />

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-03-04 at 3.10.10 PM.png" alt="Screenshot 2024-03-04 at 3.10.10 PM" style="zoom:33%;" />

**Intuition:** "Isomoprhism between fields extends to isomophism between splitting fields"

**Proof (of above):** We prove this by induction in $[E:F]$.

<u>Base Case</u>: If $[E:F] = 1 \implies E = F \implies f$ splits and the statement is trivial. 

<u>Inductive</u>: Assume $[E:F] = n > 1$, then we can write $f$ as a product of irr polynomial such that $\exists\; p_i$ of $\deg > 1$. 
$$
f = p_1 \cdot p_n \quad \quad p_i \text{ are irr over } F
$$
Let $p_i(\alpha) = 0$ for $\alpha \in E$ and consider the tower of extensions.
$$
F \leq F(\alpha) \leq E = F(\alpha_1, \dots, \alpha_n)
$$
By the theorem we proved in class, we have that $[E:F] = [E:F(\alpha)] \cdot [F(\alpha):F]$. Now, let $\alpha'$ be a root of $\sigma_0(p_i)$ in $E'$. We also know the following nested field extension.
$$
F' \leq F'(\alpha') \leq E'
$$
 <img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-03-04 at 3.19.39 PM.png" alt="Screenshot 2024-03-04 at 3.19.39 PM" style="zoom: 33%;" />

**Lemma:** Let $F \rightarrow^{\cong,\;\sigma_0} F'$, $p \in F[x]$ irr, $p$ splits in $E$, $p(\alpha = 0)$ for $\alpha \in E$, $\sigma_0(p)$ irr, $\sigma_0(p)$ splits in $E'$, $\sigma_0(p)(\alpha') =0 $, there exist a unique extension of $\sigma_0$ to an isomorphism $\sigma_1 : F(\alpha) \rightarrow^{\cong} F'(\alpha')$ such that $\sigma_1(\alpha) = \alpha'$. 

**Proof:** Since $p$ is irreducible, $F(\alpha_1) \cong F[x] / (p)$. 
$$
F[x] / (p) \cong_1 F'[x]/(\sigma_0(p)) \cong F'(\alpha')
$$
The reason why $\cong_1$ exists is because there exists an unique isomorphism extending $\sigma_0$ because it maps the ideal to the ideal $\implies\sigma_0$ indices $F[x] \rightarrow F'[x]$. Thus, we have that $\sigma_1$ is by definition, a composition of 
$$
\sigma_1 : F(\alpha) \cong F[x] / (p) \cong F'[x] / (\sigma_0(p)) \cong F'(\alpha')
$$
Now, we can apply the inductive step to $[E:F(\alpha)] < [E: F]$ by the hypohtesis. $\exists \sigma: E \rightarrow E'$ such that $G|_{F(\alpha)} = G_1 $. 

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-03-04 at 3.32.43 PM.png" alt="Screenshot 2024-03-04 at 3.32.43 PM" style="zoom:33%;" />

---

**Question:** Is it true that in the setting of the lemma, there are $[F(\alpha): F] = \deg p$ isomophisms extending $F \rightarrow^{\sigma_0} F'$ ?

**Answer:** $\exists!$ isomorphism for each root of $\sigma_0(p)$, so the answer is positive iff there are no multiple roots of $p$. 

---

**Proposition:** If $f$ is <u>separable</u> (not defined yet) and irreducible, then $f$ has no multiple roots.

**Proof:** We saw, $f$ has a multiple root $\implies (f,D(f)) \neq 1$. We know that $\deg D(f) < \deg f$, then $(f, D(f)) | D(f) \implies \boxed{\deg(f,D(f)) \leq \deg(D(f))}$ $\implies$ since $f$ is irr, $(f,D(f))$ constant. 

The error for larger proofs is that every polynomila divides $0$, so the boxed implication is true if $D(f) \neq 0$. If $f$ is a constant, then it has no multiple roots but it could happen that $D(f) = 0$ but $f \neq 0$. 

<u>Example</u>: $F = \mathbb{F}_q$, $D(x^{p^k}) = p^k x^{p^{k-1}} = 0$. 

<u>Exercise</u> (1): $D : F[x] \rightarrow F[x]$ is a linear operation of $\mathbb{F}_p$ or $\mathbb{Q}$ vector spaces (depending on characterstic of $p$).

<u>Exercise</u> (2): $\text{Ker}(D) = \text{span}\{x^{p^k} : k \geq 0\}$ 

**Definition:** $f \in F[x]$ is called <u>separable</u> if every irreducible factor of $f$ has no multiple roots.

- A field $F$ is called <u>perfect</u> if every $f \in F[x]$ is separable.

**Proposition:** Every field of characterstic $0$ and every $\mathbb{F}_q$ is perfect.

**Proof:** If $f$ is separable, then $\exists\; [F(\alpha): F]$ isomophisms $F(\alpha) \rightarrow^\cong F'(\alpha')$ such that $\sigma_1|_{F} = \sigma_0$. 

By induction, we have that $[E: F(\alpha)] = \# \sigma$ such that $\sigma|_{F(\alpha)} = \sigma_1$ and $\#\sigma$ such that $G|_{F} = \sigma_0 = \# \sigma$ such that $\sigma |_{F(\alpha)} = \sigma_1$, $\sigma_1 | F = \sigma_0 = [E:F (\alpha)] [F(\alpha): F]$.   
