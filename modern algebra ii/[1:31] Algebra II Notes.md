# [1/31] Algebra II Notes

### Integral Domains

**Remark:** Not every integral domain is a field but any field is an integral domain.

- Fields $\subset$ Integral Domains $\subset$ Rings 
  - Field: $\mathbb{Q}$
  - Integral Domain: $\mathbb{Z}$ 
  - Rings: $\mathbb{Z}\backslash 4\mathbb{Z}$  

**Theorem:** Any finite integral domain is a field.

### Fraction Fields

**Precursor:** Any integral domain can be enlarged to a field.

**Definition:** Let $R$ be an integral domain. We define the fraction field of $R$ by $\text{Frac}(R)$ as the following
$$
\text{Frac}(R) = \left({R} \times R\backslash \{0\} \right) \;/ \backsim
$$

- $R$ is the numerator
- $R\backslash \{0\}$ is the denominator

-  $(a,b) \backsim (c,d)$ , or equivalently $\frac{a}{b} = \frac{c}{d}$, if $ad = bc$ 

Let's check if $\backsim$ is an equivalence relation.

1. Reflexivity: $(a,b) \backsim (a,b)$ is a given since $ab = ba$. 
2. Symmetric: $(a,b) \backsim (c,d) \implies (c,d) \backsim (a,b)$ is also obvious since $ad = bc \implies cb = ad$. 
3.  Transitivity: If $(a,b) \backsim (c,d)$  and $(c,d) \backsim (e,f)$, then $(a,b) \backsim (e,f)$. 

$$
adf = bcf \implies adf = bde \implies af = de
$$

<u>Note</u>: $\text{Frac}(R)$ is endowed with $+, \;\circ$ as follows.
$$
(a,b) + (c,d) = \frac{a}{b} + \frac{c}{d} = \frac{ad + bc}{bd} = (ad + bc,bd) 
$$

$$
(a,b) \circ (c,d) = \frac{a}{b} \circ \frac{c}{d} = \frac{ac}{bd} = (ac, bd)
$$

<u>Exercise</u>: Check commutativity, associativity, and distributivity.

**Fraction Notation:** $(a,b) = \frac{a}{b}$ 
$$
\frac{a}{b} := (a,b) \in \text{Frac}(R)
$$
We will define the following as well:

- *Zero*: $0 := (0,1) = (0,r)$ where $r \neq 0$
- *One*: $1 := (1,1) = (r,r)$ where $r \neq 0$ 

- *Inverse*: $(a,b)^{-1} = (b,a)$ which exists iff $a \neq 0 \implies (a,b) \neq 0$  

**Corollary:** $\text{Frac}(R)$ is a field.

**Notation:** $r^{-1} := \frac{1}{r} = (1,r)$  where $r^{-1} \in \text{Frac}(R)$ 

**Proposition:** There is a natural injective homomorphism $i: R \rightarrow \text{Frac}(R)$. We leave the proof as an exercise.
$$
r \mapsto (r,1) = \frac{r}{1}
$$
**Example 1**: $R = \mathbb{Z}$ and $\text{Frac}(\mathbb{Z}) = \mathbb{Q}$ 

**Example 2**: Let $F$ be a field, $\text{Frac}(F) \cong F$. 

**Proof:** We simply need to show that the above injective homomorphism $i: F \rightarrow \text{Frac}(F)$ is surjective. Let $(a,b) \in \text{Frac}(F) \implies \exists \;b^{-1} \in F$. 
$$
(a,b) \backsim (ab^{-1},1) = i(ab^{-1})
$$

$$
(a,b) \backsim (ab^{-1},bb^{-1}) = (ab^{-1},1) \implies \frac{a}{b} \backsim \frac{ab^{-1}}{bb^{-1}} = ab^{-1}
$$

The map is surjective since any element in its range is in the image. This shows that $F$ is a bijective homomorphism, which implies isomorphic.

**Example 3:** Let $F$ be a field and $F[x]$ is <u>not</u> a field, but is an integral domain. 

- $\text{Frac}(F([x])) := F(x) $ which is the field of <u>rational functions</u> with coefficients in $F$​.  
- Two definitions are provided below.

$$
F(x) = \begin{cases}
	\sum_{i=0}^n a_ix^i\\
	\sum_{j=0}^m b_jx^j
\end{cases}\quad \;\;a_i, b_j \in F \text{ and } \exists\; b_j \neq 0
$$

$$
F(x) = \{\frac{f}{g}: f,g \in F[x],\; g\neq 0\}
$$

- $F(x) \nrightarrow^{\text{ev}} F^F$ because $g$​ can have roots.

**Remark:** $\mathbb{Q}(\sqrt{2}) = \Im(\text{ev}_{\sqrt{2}}), \text{ev}_{\sqrt{2}} \cdot \mathbb{Q} \rightarrow \mathbb{R}$, evaluate polynomial with rational coefficients at $\mathbb{R}$ 
$$
\Im(\text{ev}_s) := R[x] \leq S
$$

$$
\text{ev}_s \cdot F(x) \longrightarrow^s E
$$

$$
\Im(\text{ev}_s) := F(S)
$$

### Ideals & Quotient Rings

Consider $f: \mathbb{Z} \rightarrow \mathbb{Z}\backslash n\mathbb{Z}$. Another way to write this is $k \mapsto [k]$.  

- $\Im(f) = \mathbb{Z}\backslash n \mathbb{Z}$
- $\text{Ker}(f) := \{a \in \mathbb{Z} : f(a) = [0]\}$ 

In this specific case, we have the following.
$$
\text{Ker}(f) = n\mathbb{Z} = \{n \cdot k, k \in \mathbb{Z}\}
$$

1) $n\mathbb{Z}$ is an abelian sugroup of $\mathbb{Z}$ by $+$ 
2) Closed under multiplication 

$$
(na) \cdot (nb) = n^2 ab = n(nab) \in n\mathbb{Z}
$$

3. No unit, $1 \notin n\mathbb{Z}$ 
4. Absorbtion of multiplication. Any element $a \in \mathbb{Z}$ is still closed under multiplication.

$$
a \cdot (nb) = n \cdot (ab) \in n\mathbb{Z}
$$

<u>Conclusion</u>: In particular, $n\mathbb{Z} $ is a ring without a unit! 

**Definition:** A subset $I \subset R$ is called an <u>ideal</u> if:

1. It is an abelian subgroup of $(R, +)$​ 
2. Closed under multiplication "$\circ$"
3. Absorbs multiplication

**Properties:** 

- $r \cdot I \subset I$ 
- $r \cdot a \in I$ for all $r \in R, a \in I$ 

**Examples:** 

- $\{0\}, R$ are ideals in $R$ 
- For any homomorphism, $f: R \rightarrow S$, we know that $\text{Ker}(f) \subset R$  is an ideal.

