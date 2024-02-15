# [2/15] Number Theory

#### Tate's Functional Equation

**Definition:** For some $f \in \mathcal{S}$, where $\hat{f}(s) = \hat{f}(-s)$ for any $s \in \mathbb{C}$
$$
\tilde{f}(s) \zeta(s) = \tilde{\hat{f}}(1-s) \zeta(1-s) \implies \frac{\tilde{f}(s)}{\tilde{\hat{f}}(1-s)} = \frac{\zeta(1-s)}{\zeta(s)}
$$
Now, for the scenario where $f = \hat{f}$ where $f(y) = e^{-\pi y^2}$, we have
$$
\pi^{-\frac{s}{2}}\cdot  \Gamma\left(\frac{s}{2}\right) \cdot \zeta(s) = \pi^{-\frac{1-s}{2}} \cdot \Gamma\left(\frac{1-s}{2}\right) \cdot \zeta(1-s)
$$

---

#### Reimann's Explicit Formula

This holds for all $\sigma > 0$. 
$$
\frac{1}{2\pi i} \int_{\sigma - i\infty}^{\sigma + i\infty} \frac{x^s}{s} \;ds = \begin{cases}
1 &x > 1\\
0 &0\leq x < 1
\end{cases}
$$
Reimann then evaluates the following integral where $-\frac{\zeta'}{\zeta}(s) = \sum_{1}^\infty \frac{\Lambda(n)}{n^s}$ and $\sigma > 1$. 
$$
\begin{align*}
\lim_{T\rightarrow\infty }\frac{1}{2\pi i} \int_{\sigma - iT}^{\sigma + iT} -\frac{\zeta'}{\zeta}(s)\frac{x^s}{s} \;ds &= \sum \text{residues of } -\frac{z'}{z}(s)\\
&= x - \sum_{\zeta(\rho) = 0} \frac{x^\rho}{\rho}
\end{align*}
$$
If we explicitly look at the left hand side, we see that it's a sum over primes.
$$
\lim_{T\rightarrow \infty} \frac{1}{2\pi i} \int_{\sigma - iT}^{\sigma + iT} \sum_{n=1}^\infty \Gamma(n) \frac{\left(\frac{x}{n}\right)^s}{s}\;ds \quad \quad \text{since}\quad\quad \sum_{n\leq x} \Lambda(n) \backsim x - \sum_{\zeta(\rho)=0}\frac{x^\rho}{\rho}
$$
Since we know that $\rho = \frac{1}{2} + i\alpha$ and $\bar{\rho} = \frac{1}{2} - i\alpha$ where $\overline{\zeta(s)} = \zeta(\bar{s})$ , then we have the following where $\zeta\left(\frac{1}{2} + i\alpha\right) = 0$.
$$
\sum \frac{1}{\rho} = \sum_{\alpha} \left(\frac{1}{\frac{1}{2} + i \alpha} + \frac{1}{\frac{1}{2} - i \alpha} \right) = \sum_{\alpha} \frac{1}{\frac{1}{4} + \alpha^2}
$$
Later, we will show that there are at most $\mathcal{O}(\log T)$ zeroes in $\mathcal{R}_T$ where $\mathcal{R}_T$ is the box between $iT, \;1+iT, \;i(T+\epsilon),\;1+i(T+\epsilon)$. 

Using these properties, we can also rigorously prove the following identity.

**Identity:** The following formula
$$
\sum_{n \leq x} \Lambda(n)^{\Lambda(x)} = x - \sum \frac{x^\rho}{\rho}-\log(2\pi) - \frac{1}{2}\log(1-x^2)
$$

---

#### Weil's Explicit Formula

We start out with $f \in \mathcal{S}$, and $\tilde{f}(s) = \tilde{f}(-s)$. 
$$
z(s) = \pi^{-\frac{s}{2}} \cdot \Gamma\left(\frac{s}{2}\right) \zeta(s) = z(1-s)
$$

$$
\frac{z'}{z}(s) = -\frac{z'}{z}(1-s), \quad \quad \frac{z'}{z}\left(\frac{1}{2} + s\right) = -\frac{z'}{z} \left(\frac{1}{2} - s\right)
$$

$$
-\frac{z'}{z}(s) = -\frac{\log \pi}{2} + \frac{1}{2} \cdot \frac{\Gamma'}{\Gamma}\left(\frac{s}{2}\right) + \frac{\zeta'}{\zeta}(s)
$$

Now, let's evaluate the integral.
$$
\begin{align*}
\frac{1}{2\pi i} \int_{2 - i\infty}^{2 + i\infty} \frac{z'}{z}\left(\frac{1}{2} + s\right) \cdot \tilde{f}(s) \;ds &= \frac{1}{2\pi i} \int_{2-i\infty}^{2+i\infty} \left[-\frac{\log \pi}{2} + \frac{1}{2} \cdot \frac{\Gamma'}{\Gamma}\left(\frac{s}{2}\right) + \frac{\zeta'}{\zeta}(s)\right]\cdot \tilde{f}(s)\;ds\\
&= -\frac{\log \pi}{2} f(1) + \frac{1}{4\pi i} \int_{2-i\infty}^{2+i\infty} \frac{\Gamma'}{\Gamma}\left(\frac{s}{2}\right) \cdot \tilde{f}(s)\;ds - \sum_{n=1}^\infty \frac{\Lambda(n)}{n^{\frac{1}{2}}} f(n)
\end{align*}
$$
The first computation is as follows.
$$
\begin{align*}
\frac{1}{2\pi i} \int_{2 - i\infty}^{2 + i\infty} \frac{z'}{z}\left(\frac{1}{2} + s\right) \cdot \tilde{f}(s) \;ds = -\frac{\log \pi}{2} f(1) - \sum_{n=1}^\infty \frac{\Lambda(n)}{n^{\frac{1}{2}}} f(n) + \frac{1}{4\pi i} \int_{2-i\infty}^{2+i\infty} \frac{\Gamma'}{\Gamma}\left(\frac{s}{2}\right) \cdot \tilde{f}(s)\;ds
\end{align*}
$$
Now, we shift the line of integration to get the second computation.
$$
\begin{align*}
\frac{1}{2\pi i} \int_{2 - i\infty}^{2 + i\infty} \frac{z'}{z}\left(\frac{1}{2} + s\right) \cdot \tilde{f}(s) \;ds &= \text{``Sum of Residues''} + \overbrace{\text{``2 Horiz Integrals''}}^{\rightarrow^{\text{Small}} 0} \\
&- \int_{-2+i\infty}^{-2-i\infty} \underbrace{\frac{z'}{z}\left(\frac{1}{2} + s\right)\tilde{f}(s)}_{s\rightarrow -s}\;ds\\
\end{align*}
$$
<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-02-15 at 3.24.18 PM.png" alt="Screenshot 2024-02-15 at 3.24.18 PM" style="zoom:50%;" />

- Exponential decay means that the horizontal integrals go away

$$
\begin{align*}
\int_{-2+i\infty}^{-2-i\infty} \underbrace{\frac{z'}{z}\left(\frac{1}{2} + s\right)\tilde{f}(s)}_{s\rightarrow -s}\;ds\ &= -\int_{2-i\infty}^{2+i\infty} \frac{z'}{z}\left(\frac{1}{2}-s\right) \tilde{f}(s) (-ds) = -\int_{2-i\infty}^{2+i\infty} -\frac{z'}{z}\left(\frac{1}{2}+s\right) \tilde{f}(s) (-ds)\\
&= -\int_{2-i\infty}^{2+i\infty} \frac{z'}{z}\left(\frac{1}{2} + s\right) \tilde{f}(s)\;ds
\end{align*}
$$

Thus, we can simplify the original equation to the following expression.
$$
2 \cdot \frac{1}{2\pi i} \int_{2-i\infty}^{2+i\infty} \frac{z'}{z}\left(\frac{1}{2} + s\right) \tilde{f}(s) \;ds = \text{``Sum of Residues'' of } \frac{z'}{z}\left(\frac{1}{2} + s\right) \tilde{f}(s)
$$
This means that for any $F(s) = (s-a)h(s)$, we have
$$
\frac{F'(s)}{F(s)} = \frac{1}{s-a} + \frac{h'}{h}(s)
$$
This means that there are poles at $s = \pm\frac{1}{2}$ since $z$ has holds at $0$ and $1$. And, we have poles at zeroes of $z\left(\frac{1}{2} + s\right)$. Since we don't hit any trivial zeroes based on definiotion of $\zeta$, we are only concerned about zeroes in the critical strip. 

Now, consider the fact that $-\frac{\zeta'}{\zeta}(s) = \sum \frac{\Lambda(n)}{n^s}$ has a pole at $s = 1$. This means that for $\zeta(\frac{1}{2} + \alpha) = 0$, we have that
$$
-\tilde{f}\left(\frac{1}{2}\right) - -\tilde{f}\left(-\frac{1}{2}\right) + \sum_{\alpha} \tilde{f}(\alpha)
$$
 Finally, we can conclude that for $\zeta(\frac{1}{2} + \alpha) = 0$, we have the original expression.
$$
\frac{1}{2\pi i} \int_{2 - i\infty}^{2 + i\infty} \frac{z'}{z}\left(\frac{1}{2} + s\right) \cdot \tilde{f}(s) \;ds = \tilde{f}\left(\frac{1}{2}\right) - \frac{1}{2} \sum_{\alpha} \tilde{f}(\alpha)
$$
**Theorem:** Weil's Explicit Formala
$$
\sum_{n=1}^\infty \frac{\Lambda(n)}{\sqrt{n}} f(n) = \tilde{f}\left(\frac{1}{2}\right) - \frac{1}{2} \sum_{\zeta\left(\frac{1}{2} + \alpha\right) = 0} \tilde{f}(\alpha) - \frac{\log \pi}{2} + \frac{1}{4\pi} \int_{2-i\infty}^{2+i\infty} \frac{\Gamma'}{\Gamma}\left(\frac{1}{2} + s\right) \tilde{f}(s)\;ds
$$
