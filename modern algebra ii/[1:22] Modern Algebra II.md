# [1/22] Modern Algebra II

### Rings & Fields

#### Rings

**Definition:** The set of all invertible elements in a ring (not necessarily commutative), forms a multiplicative group $R^*$ (group of units of $R$).

- $a \in R$ is invertible if $\exists b \in R$ such that $ab = ba = 1$. 

**Proof:** $a_1, a_2 \in R$ and $a_1b_1 = a_2b_2 = 1$, then we can explicitly construct the inverse such that
$$
a_1a_2b_2b_1 \implies a_1(a_2b_2)b_1 = 1
$$
Since the identity exists, $1 = 1^{-1}$​, then we can prove group properties.

#### Fields

**Definition:** A ring $R$ is called a field if $R^* = R\backslash\{0\}$. This is to say that every non-zero element is invertible. 

**Example(s):** $\mathbb{Q}, \mathbb{R}, \mathbb{C}$​ are all fields.

----

**Proposition:** If $0 \in R$ is invertible, then $R = \{0\}$. 

**Proof:** If $0$ is invertible, then $\exists\; 0^{-1} \in \mathbb{R}$ such that $0 \cdot 0^{-1} = 1$. But in fact, $0 \cdot a = 0$ for all $a \in R$. 

- $0 \cdot a \implies (1-1) \cdot a \implies a-a = 0$ 

These two facts together, we get that $1 = 0$. The only ring where $1 = 0$ is the zero-ring $R = \{0\}$.

----

**Example:** Rings of residues modulo $n$. Notation is $\mathbb{Z}\backslash n\mathbb{Z} = \mathbb{Z}n = \{[0],[1],\dots,[n-1]\}$. 

- $\mathbb{Z}_n$ is an abelian group with respect to  "$+$"

**Proposition:** $\left(\mathbb{Z}_n, +, \circ\right)$ is a ring.

**Proof:** First, we need to check that multiplication is well-defined.
$$
\begin{align*}
[a] \cdot [b] &= [a \cdot b]\\
[a + nx][b + ny] &= [(a+nx)(b+ny)] \\
&= [ab + n(xb + ay + nxy)]\\
&= [ab]
\end{align*}
$$
You then you need to prove associativity and distributivity (left as an exercise).

- $[1]$ is the unit of this ring

**Example:** Take $\mathbb{Z}_3$. We have that $2^{-1} = 2$ and $0 \cdot a = 0$. 
$$
R^* = \{1,2\} \implies \mathbb{Z}_3 \text{ is a field}
$$
**Example:** Take $\mathbb{Z}_4$. We have that $R^* = \{1,3\} \cong (\mathbb{Z}_2, +)$. Thus, $\mathbb{Z}_4$ is not a field.

---

**Definition:** If $a, b \neq 0$ and $a,b \in R$ such that $a \cdot b = 0$, then $a,b$ are called <u>zero-divisors</u>.

- $2 \in \mathbb{Z}_4$ is a zero-divisor

- If $a \in R$ is a zero divisor, it cannot have an inverse.

**Corr:** If $\exists \;a^{-1} \in R$, such that $a^{-1}a = 1 \implies a^{-1}ab = b \implies a^{-1}(ab) \neq b \text{ if } ab = 0$.  

**Exercise:** $\mathbb{Z}_p$ is a field iff $p$​ is a prime number.

---

#### Homomorphisms of Rings

**Definition:** A function $f: R \rightarrow S$ (where $R,S$ are rings) is called a homomorphism if 

- $f$ is a homomorphism of abelian groups (preserves addition and sends $f(0) \mapsto 0$)

$$
f(a +_R b) = f(a) +_S f(b)
$$

- Preserves $\circ$ such that $f(ab) = f(a)f(b)$

- $f(1_R) = 1_s$​ 

- $\Im(f) \leq S$ 

**Remark:** $\Im(f) \leq S$ $\rightarrow$ $\leq$ this is a subring notation. If $x,y \in \Im(f) \implies \exists\;a,b \in R$ such that $x = f(a)$ and $y = f(b)$ $\implies f(a+b) \in \Im(f)$. 

**Examples:** 

- $R \rightarrow \{0\}$ is in fact a homomorphism
- $\{0\} \rightarrow R$ is a homomorphism iff $R \neq \{0\} $ 
- There always exists only one homomorphism $\mathbb{Z}\rightarrow R$ 

**Proposition:** For any $R$, there exists a unique homomorphism from $\mathbb{Z} \rightarrow R$. First, we have that $f(0) = 0_R$ and $f(1) = 1_R$. By preserving addition, $f(n) = f(1 + \dots +1) = f(1) + \dots + f(1) \in R$. 

<u>Exercise:</u> You still need to show that $f(a) \cdot f(b) = f(a \cdot b)$. 

**Examples:**

- $\mathbb{Z} \rightarrow \mathbb{Z}_n$ is a homomorphism. $f(n) \mapsto f([n])$ 

- $\mathbb{C} \rightarrow \mathbb{C}$ such that $f(z) \mapsto \overline{z}$ 
  - $\overline{1} = 1$, $\overline{(z+w)} = \overline{z} + \overline{w}$, and $\overline{zw} = \overline{z} \cdot \overline{w}$

-  $\mathbb{Q} (\sqrt{2}) \rightarrow \mathbb{Q}(\sqrt{2})$ such that $f(a+b\sqrt{2}) \mapsto a - b\sqrt{2}$ 

#### Polynomial Ring

**Definition:** Let $R$ be a ring, then the polynomial ring with coefficients $\in \mathbb{R}$ is
$$
R[x] = \sum_{i=0}^n a_ix^i ,\quad a_i \in \mathbb{R}
$$
We also know that there exists some $n \in \mathbb{N}$ such that for all $m > n$, we have $a_m = 0$. 

**Addition:** Consider $f,g \in R$ where
$$
f = \sum_{i=0}^n a_ix^i \quad \text{and} \quad g = \sum_{j=0}^m b_j x^j
$$
We can define $f+g$ as follows.
$$
f+g = \sum_{i=0}^{\max(n,m)} (a_i+b_i)x^i
$$
**Multiplication:** Define multiplication by $x \cdot x = x^2$. Then, multiplication on either polynomial is defined by distributivity. 

**Distributivity:** Holds on $R$. 
$$
f \cdot g = \left(\sum_{i=0}^n a_ix^i\right) \cdot \left(\sum_{j=0}^m b_j x^j\right) = \sum_{i,j}^{(n,m)} (a_ix^i)(b_jx^j) = \sum_{i,j} a_ib_j x^{i+j} = \sum_{k=0}^{n+m} \left(\sum_{i+j = k}^{} a_ib_j\right) x^k
$$
<u>Exercise:</u> Check Associativity as an Exercise.