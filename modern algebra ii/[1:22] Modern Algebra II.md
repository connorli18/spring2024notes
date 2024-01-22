# [1/22] Modern Algebra II

### Rings

**Definition:** The set of all invertible elements in a ring (not necessarily commutative), forms a multiplicative group $R^*$ (group of units of $R$).

- $a \in R$ is invertible if $\exists b \in R$ such that $ab = ba = 1$. 

**Proof:** $a_1, a_2 \in R$ and $a_1b_1 = a_2b_2 = 1$, then we can explicitly construct the inverse such that
$$
a_1a_2b_2b_1 \implies a_1(a_2b_2)b_1 = 1
$$
Since the identity exists, $1 = 1^{-1}$, then we can prove group properties.

**Definition:** A ring $R$ is called a field if $R^* = R\backslash\{0\}$. This is to say that every non-zero element is invertible. 

**Example(s):** $\mathbb{Q}, \mathbb{R}, \mathbb{C}$

