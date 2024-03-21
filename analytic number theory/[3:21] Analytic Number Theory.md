# [3/21] Analytic Number Theory

#### Automorphic Forms

Define some group $G$. And let's define $X$ as a topological space. Now, define some action of $G$ on $X$. 

---

**Definition (Action):** Let $g \in G$ and $x \in X$. We define $g \cdot x$ as follows.

(1) $g \cdot x \in X$ for all $g \in G, x \in X$

(2) Let $e$ be the identity element. Then, $e \cdot x = x$ 

(3) $(g_1g_2) \cdot x = g_1 \cdot (g_2 \cdot x)$

---

Assume we have a group $G$ acting on $X$, and assume that we can define functions $f : X \rightarrow \mathbb{C}$. 

**Definition (Automorphic Function):** Assume that $G$ acts on $X$. A function $f: X \rightarrow \mathbb{C}$ is called an automorphic function for $G$ if $f(g \cdot x) = f(x)$ for all $g \in G$. 

---

<u>Example (1):</u> Take $X = \mathbb{R}$ and $G = (\mathbb{Z}, +)$. 

$\mathbb{Z}$ acts on $\mathbb{R}$ as follows. Let $a \in \mathbb{Z}, x \in \mathbb{R}$, we define $a \cdot x := x + a$. An automorphic function satisfies $f(a \cdot x) = f(a + x) = f(x)$ for all $a \in \mathbb{Z}, x \in \mathbb{R}$. That means $f$ must be a periodic function!

----

<u>Example (2):</u> $G = SL(2,\mathbb{Z}) = \left\{\begin{pmatrix} a & b \\ c & d\end{pmatrix} : a,b,c,d \in \mathbb{Z}, ad-bc = 1\right\}$ , a group under multiplication.

The identity element is $e = \begin{pmatrix} 1 &0 \\ 0 & 1\end{pmatrix}$ and inverse is defined by $\begin{pmatrix} d & -b\\ -c &a \end{pmatrix}$. 

We also define $X = \mathcal{Y} = $ upper-half plane $= \{x+iy : x \in\mathbb{R}, y \geq 0\}$. 

**Definition:** (Action of $SL(2,\mathbb{Z})$ on $\mathcal{Y}$ ) 

Let $\gamma = \begin{pmatrix} a & b \\ c & d\end{pmatrix} \in SL(2,\mathbb{Z})$ and let $z = x + iy \in \mathcal{Y}$. We define
$$
\gamma \cdot z := \frac{az + b}{cz + d}
$$
 **Proof of Action:** First, let's prove identity.
$$
\begin{pmatrix} 1 & 0 \\ 0 & 1\end{pmatrix} \cdot z = \frac{z}{0+1} = z
$$
 Now, assume that $z = x+iy$ and $\Im(z) = y$. We need to prove that if $z \in \mathcal{Y}$, for any $\begin{pmatrix} a & b \\ c & d \end{pmatrix} \in SL(2,\mathbb{Z})$ that
$$
\Im\left(\frac{az + b}{cz + d}\right) > 0
$$
 We can show the following.
$$
\Im\left(\frac{az + b}{cz + d}\right) = \Im \left(\frac{(a(x+iy) + b)(c(x - iy) + d)}{\left|cz + d\right|^2}\right) = \Im\left( \frac{(\cdots) + iy(ad-bc)}{|\cdots|^2} \right) > 0
$$
Now, we simply need to show the following.
$$
\begin{pmatrix} a & b \\ c & d \end{pmatrix} \begin{pmatrix} a' & b' \\ c' & d' \end{pmatrix} \cdot z = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \cdot \frac{a'z + b'}{c'z + d'}
$$
We can show this by brute force computation.

**Definition (Automorphic Function):** This should be a function $f: \mathcal{Y} \rightarrow C$.
$$
f\left(\frac{az + b}{cz + d}\right) = f(z) \quad \quad \forall \begin{pmatrix} a & b \\ c & d \end{pmatrix} \in SL(2,\mathbb{Z}), \forall \; z \in \mathcal{Y}
$$
It can be shown that the only holomorphic (on $\mathcal{Y}$ ) is the constant function $f(z) = \lambda \in \mathbb{C}$. 

---

**Question:** Can we define a more general automoprhic function satisfying 
$$
f\left(\frac{az + b}{cz + d}\right) = \underbrace{\psi\left(\begin{pmatrix} a & b \\ c & d \end{pmatrix}, z\right)}_{\text{weight}} f(z) \quad \quad \forall \begin{pmatrix} a & b \\ c & d \end{pmatrix} \in SL(2,\mathbb{Z}), \forall \; z \in \mathcal{Y}
$$
Where $\psi: SL(2,\mathbb{Z}) \rightarrow \mathbb{C}$ ? Can such weight functions exist?

First, if we define the following,
$$
\gamma = \begin{pmatrix} a & b \\ c & d \end{pmatrix}, \gamma' = \begin{pmatrix} a' & b' \\ c' & d' \end{pmatrix} \in SL(2,\mathbb{Z})
$$
and $e$ is the $2 \times 2$ identity matrix, so $\psi(e, z) = 1$. 
$$
\begin{align*}
f((\gamma \gamma') \cdot z) &= f(\gamma \cdot (\gamma' \cdot z))\\
\psi(\gamma \gamma', z) f(z) &= \psi(\gamma, \gamma'z) f(\gamma' \cdot z) \\
&= \psi(\gamma, \gamma' z) \psi(\gamma', z) f(z)

\end{align*}
$$
This tells us that all functions $\psi$ must satisfy the cocycle $\psi(\gamma \gamma', z) = \psi(\gamma',z) \psi(\gamma, \gamma'z)$. 

<u>Example of Cocylcle</u> (for $SL(2,\mathbb{Z})$ ):
$$
j(\gamma, z) = j\left(\begin{pmatrix} a & b \\ c & d \end{pmatrix}, z\right) := cz + d
$$
We can show that this satisfies the relation.
$$
\begin{align*}
j \left(\begin{pmatrix} a & b \\ c & d \end{pmatrix} \cdot \begin{pmatrix} a' & b' \\ c' & d' \end{pmatrix}, z\right) &= (ca' + dc')z + cb' + dd'\\
&= j\left(\begin{pmatrix} a' & b' \\ c' & d' \end{pmatrix} , z\right) \cdot j\left(\begin{pmatrix} a & b \\ c & d \end{pmatrix}, \frac{a'z + b'}{c'z + d'}\right)
\end{align*}
$$
Thus, we have that $j(\gamma, z) = cz + d$, but also $j(\gamma, z)^k = (ck + d)^k$ also satisfies the condition above!

--------

**Definition:** Modular form for $SL(2,\mathbb{Z})$ with weight $k$. It is the function
$$
f : \mathcal{Y} \rightarrow \mathbb{C}
$$
which satisfies the following for all $\begin{pmatrix} a & b \\ c & d \end{pmatrix} \in SL(2,\mathbb{Z})$ and $z \in \mathcal{Y}$. 
$$
f\left(\frac{az + b}{cz + d}\right) - (cz + d)^k f(z)
$$
<u>Sayer's Book!</u>