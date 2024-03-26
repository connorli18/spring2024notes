# [2/7] Algebra II Notes

### Last Time

**First Isomorphism Theorem:** Define some ring homomorphism $f: R \rightarrow S$. 
$$
\Im(f) \cong R / \ker(f)
$$
**Prime fields:** $\mathbb{Q}$ and $\mathbb{F}_p$ 

**Division Algo:** Division of polynomials with residue.

------

### Modular Division

**Example:** Divide $x^3 + x^2 + 2x + 1$ by $x + 2$ in $\underbrace{\mathbb{Z}/3\mathbb{Z}}_{\text{field}}[x]$ . Continue the exercise for all $n$ such that $\mathbb{Z}/n\mathbb{Z}[x]$. 

**Example:** You can show that $x^2 + 2x + 1$ cannot be divided by $2x + 1$ in $\mathbb{Z}[x]$. 

**Theorem:** $F[x]$ is a principle ideal domain (PID).

**Proof:** (as in $\mathbb{Z}$) Let $\forall I \subset F[x]$ , and define $g \in I$ of minimal degree.  Take $f \in I\backslash (g)$. 

We can use the division algorithm to show $f = hg + r$ where $hg \in I$ and $f \in I$. This means that $r = f - hg \implies r \in I$. This means that $\deg(r) < \deg(g)$, which is a contradiction. Thus, we know that $I\backslash (g) = 0$, which means that $I = (g)$. 

**Corollary:** Every ideal $F[x]$ is of the form $I = (m)$ where $m = 0$ or $m$ is monic (which means that leading coefficient is one).

**Example:** Consider $\mathbb{Q}[x]$ and $I = (x^2 + 2x, x-1) \subset \mathbb{Q}[x]$. 
$$
I = (f,g) \neq (fg)
$$
We want to find the $\text{gcd}(f,g)$ since it generates both $f$ and $g$. 
$$
g,f \in (\text{gcd}(f,g)) \implies (f,g) \subset (\text{gcd}(f,g)) \text{ and }(f,g) \supset (\text{gcd}(f,g)) \implies (f,g) = (\text{gcd}(f,g))
$$

---

**Definition:** Consider some $R[x]$. We can say $g | f$ if $f \in (g) \iff f = hg$. Let $f_1, \dots, f_n \in F[x]$. $(f_1, \dots f_n) = (d)$ for a monic or zero $d \in F[x]$. 

**Lemma:** $\forall \;d' \;|\;f_1, \dots f_n \implies d'\;|\;d$ 

**Proof:** $f_1 \in (d'), \dots, f_n \in (d') \implies (d')$ contains $f_1, \dots, f_n$. Using a proof from homework, we have that $(d) = (f_1, \dots, f_n) = \cap I \implies (d) \subset (d') \implies d'\;|\;d$. 

**Corollary:** (Bezout's Identity) $d = \sum_i f_ih_i$ and $(d) = (f_1, \dots, f_n)$. Use <u>E</u><u>uclidean algorithm</u> to find $\text{gcd}(f_1, f_2)$. Assume that $\deg(f_1) \geq \deg(f_2)$. 
$$
f_1 = h_1f_2 + r_1
$$

$$
f_2 = h_2r_1 + r_2
$$

$$
r_{n-1} = h_{n+1} \cdot r_n
$$

**Example:** Find the $\text{gcd}$ of $x^2 + 2$ and $x + 2$ in $\mathbb{Z}/3\mathbb{Z}[x]$. The answer is $x + 2$. 
$$
(x+1)(x+2) = x^2 + \cancel{3x} + 2 = x^2 + 2
$$

---

**Recall:** We have $\text{ev}_r: F[x]\rightarrow F$ where $f \mapsto f(r)$. 

**Definition:** We say that $r$ is a root of $f$ if $\text{ev}_r(f) = f(r) = 0 \in F$. 

**Theorem:** $\alpha$ is a root of $f \Leftrightarrow f = (x- \alpha) \cdot g \implies x-\alpha | f$ .

The reverse direction is obvious, $f = 0$ when $x = \alpha$. To prove the forward direction, we divide $f$ by $x - \alpha \in F[x]$. We now have the following.
$$
f = (x-\alpha) \cdot g + r
$$
We also know that $0 \leq \deg(r) < \deg(x - \alpha) = 1 \implies \deg(r) = 0 \implies r \in F$. We can then show that $r = 0$. 
$$
0 = \text{ev}_{\alpha}(f) = 0 \cdot g + r \implies 0 = r
$$

---

**Theorem:** Polynomials of degree $n$ cannot have more than $n$ roots. 

**Proof:** First, note that  $\deg(0)$ polynomials have no roots.

Now, assume that $\deg(f) = n$ and $\alpha_1$ is a root. Now, imagine $\alpha_2 \neq \alpha_1$. 
$$
\text{ev}_{\alpha_2} (f) = \underbrace{(\alpha_2 - \alpha_1)}_{\neq 0} \underbrace{f_1(\alpha_2)}_{=0} = 0
$$
**Corollary:** The $\ker(\text{ev}_{\alpha}) = (x-\alpha) \subset F[x]$