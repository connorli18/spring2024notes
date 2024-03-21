# Solvability in Radicals

## Quadratic Equations

Consider the quadratic equation $f = ax^2 + bx + c$. The quadratic formula tells us that
$$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$
Let $F = \Q(b, c) \leq F(\sqrt{b^2 - 4ac})$, and this is the splitting field for $f$. Notice that this is a field extension of the type from the last theorem.

**Definition:** $F \leq B$ is called a **pure radical extension of type $m$** (or simple instead of pure) if $B = F(\alpha)$, where $\alpha^m \in F$.

**Example:** $F(\sqrt{b^2 - 4ac})$ is a pure radical extension of type $2$.

**Definition:** $F \leq B_t$ is called a **radical extension** of $F$ if there is a tower
$$
F = B_0 \leq B_1 \leq B_2 \leq \cdots \leq B_t
$$
where each individual extension is a pure radical extension (of any type).

**Definition:** We say $f \in F[x]$ is **solvable in radicals** if there exists a radical extension $F \leq B_t$ such that $f$ splits in $B_t$.

>  **Remark:**
>
> 1. $B_t$ is not necessarily the splitting field of $f$​; if $E$ is the splitting field of $f$, then $E \leq B_t$.
> 2. If $f$ is solvable in radicals (in the sense of the definition), we can write all the roots of $f$ using field operations and roots, but a priori, this expression is not "general".

