# [3/5] Analytic Number Theory Notes

#### Prime Number Theorem

From last class, we have shown the following definition in (1) and the Hadamard product in (2).
$$
z(s) = \frac{1}{2} s ( s-1) \;\pi^{-\frac{s}{2}} \;\Gamma\left(\frac{s}{2}\right) \; \zeta(s) = z(1-s)
$$

$$
z(s) = e^{A+Bs} \prod_{z(\rho)=0} \left(1-\frac{s}{\rho}\right) e^{\frac{s}{\rho}}
$$

$\chi$ We also showed that in some rectangle $R$, as shown below, we have that the $\# \left(\text{zeroes in } R\right) = \mathcal{O}(\log T)$. 

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-03-05 at 2.46.52 PM.png" alt="Screenshot 2024-03-05 at 2.46.52 PM" style="zoom:50%;" />
$$
\frac{\zeta'}{\zeta}(s) = (*) \; + \sum_{\rho} \left(\frac{1}{s-\rho} + \frac{1}{\rho}\right)
$$

-----

**Lemma:** Let $s = \sigma + iT,\; T > 0$ and $0 < \sigma < 2$. 
$$
\frac{\zeta'}{\zeta}(\sigma + it) = \sum_{|\gamma-T|} \frac{1}{\sigma + iT - \rho} + \mathcal{O}(\log(2+T))
$$
**Proof:** In the published notes!

---

**Theorem (de la Valee Poussin):** There exists $c > 0$ such that for all $T \geq 2$, there are no zeroes of $\zeta(s)$ in the region.
$$
\sigma \geq 1 - \frac{c}{\log T}
$$

---

Using the two theorem's above, we can prove the Prime Number Theorem.

**Prime Number Theorem:** For some $c > 0$,
$$
\sum_{n \geq x} \Lambda(n) = x + \mathcal{O}\left(e^{-c\sqrt{\log x}}\right)
$$
<u>Note</u>: We also have that $e^{-c\sqrt{\log x}} \ll \frac{x}{\log x} B$. 

**Perron:** We also need Perron's Formula to complete the proof of the Prime Number Theorem.
$$
\frac{1}{2\pi i} \int_{c - iT}^{c + iT} \frac{y^s}{s}\;ds = \mathcal{O}\left(\frac{y^c}{T|\log y|}\right) + \begin{cases}
1 & y>1\\
0 & 0 < y \leq 1
\end{cases}
$$

---

**Proof (Prime Number Theorem):** We know the following relationship.
$$
\begin{align*}
-\frac{\zeta'}{\zeta}(s) = \sum_{n=1}^\infty \frac{\Lambda(n)}{n^s}
\end{align*}
$$
If we use Perron's formula, we have the relation as follows.
$$
\begin{align*}
\overbrace{\frac{1}{2\pi i} \int_{1+ \frac{1}{\log x} - iT}^{1+ \frac{1}{\log x} + iT} -\frac{\zeta'}{\zeta}(s) \frac{x^s}{s} \;ds}^{\Psi} &= \sum_{n \leq x} \Lambda(n) + \mathcal{O}\left(\sum_{n=2}^\infty \Lambda(n)\left(\frac{x}{n}\right)^{1+\frac{1}{\log x}} \frac{1}{T \left|\log \frac{x}{n}\right|}\right)\\
&= \sum_{n \leq x} \Lambda(n) + \mathcal{O} \left(\frac{x \log^2 x}{T}\right)
\end{align*}
$$
To complete the Prime Number Theorem, we need to shirt the line of integration of $\Psi$ to $\Re(s) = 1 - \frac{c}{\log T}$ where our region of integration is called $R$. 

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-03-05 at 3.03.01 PM.png" alt="Screenshot 2024-03-05 at 3.03.01 PM" style="zoom:50%;" />

When we integrate around $R$, then only pole inside is at $s = 1$. Thus, we just have to show that the other things disappear.
$$
\begin{align*}
\frac{1}{2\pi i} \int_{1+ \frac{1}{\log x} - iT}^{1+ \frac{1}{\log x} + iT} -\frac{\zeta'}{\zeta}(s) \frac{x^s}{s} \;ds &= \overbrace{x}^{\text{residue}} + \overbrace{\mathcal{O}\left(\frac{1}{2\pi i}\int_{1+\frac{1}{\log x} + iT}^{1-\frac{c}{\log T} + iT} \left|-\frac{\zeta'}{\zeta}(s) \frac{x^s}{s}\right|\;ds\right)}^{\text{Horizontal Integral}} + \overbrace{\mathcal{O}\left(\int_{1-\frac{c}{\log T}+iT}^{1-\frac{c}{\log T}-iT}\left|-\frac{\zeta'}{\zeta}(s) \frac{x^s}{s}\right|\;ds \right)}^{^{\text{Vertical Integral}}}


\end{align*}
$$
We know that the integrals $I_{\text{Hor}}$ and $I_{\text{Ver}}$ are bounded as follows.
$$
I_{\text{Hor}} \ll \left|\int_{1-\frac{c}{\log T}}^{1+\frac{1}{\log x}}\frac{(\log T)^2}{T}\;x^{1+\frac{1}{\log x}}\right|
$$

$$
I_{\text{Ver}} \ll \int_{-T}^T \left(\frac{\log^2 T}{\left(1 - \frac{c}{\log T} + iT\right)} \; x^{c-\frac{1}{\log T}}\right)\;dt
$$

And since $x^{c-\frac{1}{\log T}} \approx xe^{-\frac{\log x}{\log T}} \implies T = e^{c\sqrt{\log x}}$. And if you bound everything carefully, we have the following.
$$
I_{\text{Hor}} + I_{\text{Ver}} = \mathcal{O}\left(x (\log x)^3 \left(\frac{1}{T} + x^{-\frac{c}{\log T}}\right)\right) = \cdots
$$

####  Dirichlet Characters

**Definition:** A Dirichlet character of conductor $q$ (where $q \in \mathbb{Z}^+$) is a function $\chi: \mathbb{Z} \rightarrow \mathbb{C}$ that satisfies the following conditions.

- $\chi$ is periodic, which means that $\chi(a + q) = \chi (a)$, for all $a \in \mathbb{Z}$ 
- $\chi$ is totally multiplicative, which means that $\chi(ab) = \chi(a) \cdot \chi(b)$ for all $a,b \in \mathbb{Z}$. 
- $\chi(a) = 0$ whenever $(a,q) > 1$, otherwise $\chi(a) \neq 0$. 

**Examples:**

- $q = 1$

  - $\chi(a) = 1$ for all $a \in \mathbb{Z}$ 

- $q = 2$

  - $\chi(1) = 1$ and $\chi(2) = 0$ 
  - For every $q$, we have a trivial character.

- $q=3$​ 

  - $\chi_0(a) = \begin{cases} 1 & (a,q) = 1\\ 0 & \text{other}\end{cases}$

  - $\chi_1(1) = 1$, $\chi_1(2) = -1$, $\chi_1(3) = 0$
  - You can prove there are exactly two characters since $1 \cdot \beta = \beta$ and $\beta^2 = 1$. 

- $q = 4 \implies \chi_1(3)\cdot \chi_1(3) = \chi_1(9) = \chi_1(1)$

|          | 1    | 2    | 3    | 4    |
| -------- | ---- | ---- | ---- | ---- |
| $\chi_0$ | 1    | 0    | 1    | 0    |
| $\chi_1$ | 1    | 0    | -1   | 0    |

- $q = 5$ 

|                      | 1    | 2    | 3    | 4    | 5    |
| -------------------- | ---- | ---- | ---- | ---- | ---- |
| $\chi_0$             | 1    | 1    | 1    | 1    | 0    |
| $\chi_1$             | 1    | -1   | -1   | 1    | 0    |
| $\chi_2$             | 1    | $i$  | $-i$ | -1   | 0    |
| $\chi_3$ (conjugate) | 1    | $-i$ | $i$  | -1   | 0    |

---

**Proposition:** Let $x$ be a non-trivial Dirichlet character of conductor $q$. Then,
$$
\sum_{a=1}^q \chi(a) = 0
$$
**Proof:** Since $\chi$ is non-trivial, there exists some $b$ inside $\left(\mathbb{Z}/q\mathbb{Z}\right)^\times$ such that $\chi(b) \neq \{0,1\}$.  Now, you take $\chi(b) \cdot \sum_{a=1}^q \chi(ab) = 0$. This allows us to have.
$$
\chi(b) \cdot \sum_{a=1}^q \chi(a) = \sum_{a=1}^q \chi(ab) = \sum_{a=1}^q \chi(a) \implies \chi(b) \cdot S = S \implies S = 0
$$

----

**Construction (Dirichlet Characters):** How to construct $x$ of conductor $q$ for any $q > 1$. 

If $q$ is odd, then we have
$$
\begin{align*}
G_q &= \left(\mathbb{Z}/q\mathbb{Z}\right)^\times \text{ is a cyclic group with generator } b\\
&= \{b, \;b^2 \text{ mod } q,\;b^3\text{ mod }q, \dots, \;b^{\phi(q)} \text{ mod }q \}
\end{align*}
$$
Thus, we define $\chi(b^k) = e^{\frac{2\pi i k}{\phi(q)}}$ and $\chi(b) = e^{\frac{2\pi i }{\phi(q)}}$. 