# [3/19] Number Theory

#### Infinite Primes

We have the following proposition where $(a,q) = (n,q) = 1$. 
$$
\frac{1}{\phi(q)} \sum_{\chi \text{ mod } q} \chi(n) \overline{\chi}(n) = \begin{cases} 
1 & n \equiv a \text{ mod }q\\
0 & \text{other}
\end{cases}
$$
Now, examine the following structure.
$$
\begin{align*}
\frac{1}{\phi(q)} \sum_{\chi \text{ mod }q} (\log L(s,\chi)) \cdot \overline{\chi}(a) &= \frac{1}{\phi(q)}\sum_{\chi \text{ mod }q} \log\left(\prod(1-\frac{\chi(p)}{p^s}\right)^{-1} \cdot \overline{\chi}(a)\\
&= \frac{1}{\phi(q)}\sum_{\chi \text{ mod }q} -\sum_{p} \left(\log\left(1-\frac{\chi(p)}{p^s}\right)\right) \overline{\chi}(a) \\
&= \frac{1}{\phi(q)}\sum_{\chi \text{ mod }q} \sum_{p} \sum_{m=1}^\infty \frac{\chi(p)^m}{m\cdot p^{ms}} \cdot \overline{\chi}(a)\\
&= \sum_p \sum_{m=1}^\infty \frac{1}{m\cdot p^{ms}} \frac{1}{\phi(q)} \sum_{\chi \text{ mod }q} \chi(p^m) \overline{\chi}(a)\\
&= \sum_{\substack{m=1 \\ p^m \equiv a \text{ mod q}}}^\infty \sum_{p} \frac{1}{mp^{ms}}\\
&= \sum_{p \equiv a \text{ mod }q} \frac{1}{p^s} + \underbrace{\sum_{\substack{m=2 \\ p \equiv a \text{ mod }q}}^\infty \frac{1}{mp^{ms}}}_{\mathcal{O}(1) \text{ for }\Re(s) > \frac{1}{2}}
\end{align*}
$$
To prove infinitely many $p \equiv a \text{ mod }q$, it is enough to show that $\lim_{s\rightarrow 1} \frac{1}{\phi(q)} \sum_{\chi \text{ mod }q} \log L(s,\chi) \cdot \overline{\chi}(a) = \infty$. 

**Claim (1):** $L(1,\chi) \neq 0$ for $\chi \text{ mod }q$. 

---

**Claim (2):** It is easy to prove that $L(1,\chi) \neq 0$ for $\chi$ complex.

**Proof (2):** We have that $L(s,\chi) \neq L(s,\overline{\chi})$ for $\chi$ complex.

If $L(1,\chi) = 0 \implies L(1,\overline{\chi}) = 0$. Thus, all the complex characters vanish!

---

However, proving that the real parts don't vanish is more difficult. We will outline the proof here.

**Proof (1):** Let $\chi$ be a real cahracter $\text{ mod }q$. It takes the values $(0, \pm 1)$. To prove Dirichlet's theorem, it is enough to prove that $L(1,\chi) \neq 0$ for all real characters $\chi$. 

Dirichlet used Gauss's binary quadratic form $ax^2 + bxy + cy^2 = (a,b,c)$ where $a,b,c \in \mathbb{Z}$. The discriminant term of $a,b,c = b^2 - 4ac$. To get an equivalent binary quadratic form, pick $\begin{pmatrix} \alpha & \beta \\ \gamma & \delta \end{pmatrix}$. Then, define
$$
\begin{pmatrix}
x' \\ y'
\end{pmatrix} = \begin{pmatrix} \alpha & \beta \\ \gamma & \delta \end{pmatrix}\begin{pmatrix}
x \\ y
\end{pmatrix}
$$
If the discriminant is $D$, then $h(D)$ is equal to the class $\#$. If take any real character $\chi \text{ mod } D$, where $\alpha = c\pi$, 
$$
L(1,\chi) = \frac{h(D)}{\sqrt{D}} \cdot \alpha \implies h(D) \geq 1
$$
**Alternative Proof (1):** First, we need the following lemma.

---

<u>Lemma:</u> (Landou) Let $z (s) = \sum_{n=1}^\infty \frac{a(n)}{n^s}$ where $a(n) \geq 0$, $a(1) = 1$. 

Now, we have the <u>abscissa of convergence</u> is $\sigma_0 \in \mathbb{R}$ where $z(\sigma) = \infty$ for $\sigma \leq \sigma_0$. Then, if $z(s)$ has analytic continuation near $\sigma_0$, it must have a pole at $s = \sigma$. 

<u>Proof of Lemma:</u> Since $z(s)$ is analytic around $s = \sigma_0 \implies z(s)$ has the following power series expansion for $\sigma \in \mathbb{R}$. 
$$
z(s) = \sum_{k=0}^\infty \frac{z^{(k)} (\sigma_0 + \epsilon)}{k!} (\sigma - \sigma_0 + \epsilon)^k
$$
Now, define $z_N(s) = \sum_{n=1}^N \frac{a(n)}{n^s}$. We can remove the tail end of $z(s)$ above to show
$$
\begin{align*}
\sum_{k=0}^\infty \frac{z^{(k)} (\sigma_0 + \epsilon)}{k!} (\sigma - \sigma_0 + \epsilon)^k &\gg \sum_{k=0}^\infty \frac{z_N^{(k)} (\sigma_0 + \epsilon)}{k!} (\sigma - \sigma_0 + \epsilon)^k\\
&= z_N(\sigma)
\end{align*}
$$
This then implies that $\lim_{N\rightarrow \infty} z_N(\sigma) = \infty$. 

---

Now, we use Landau's lemma to prove $L(1,\chi) \neq 0$ for $\chi$ real. 
$$
\begin{align*}
z(s) := \zeta(s) L(s,\chi) = \prod_{p} \left(1 - \frac{1}{p^s}\right)^{-1} \left(1-\frac{\chi(p)}{p^s}\right)^{-1} &= \prod_{\substack{p \\ \chi(p) = +1}} \left(1-\frac{1}{p^s}\right)^{-2} \prod_{\substack{p \\ \chi(p) = -1}} \left(1-\frac{1}{p^{2s}}\right)^{-1}\\
&= \sum_{1}^\infty \frac{a(n)}{n^s}
\end{align*}
$$
We also know that $a(1) = 1$ and $a(n) \geq 0$, which makes this a candidate for Landau's lemma. 

This means that the abscissa of convergence of $z(s) \geq \frac{1}{2}$. Assume $L(1,\chi) = 0 \implies z(s)$ is holomorphic around $s=1 \implies z(s)$ is holomorphic for $\Re(s) > 0$​.  

-----

#### Siegel's Theorem

<u>Note:</u> Dirichlet proved $L(1,\chi) \approx \frac{h(D)}{\sqrt{D}} \implies L(1,\chi) > \frac{1}{\sqrt{D}}$ for $\chi \text{ mod }D$ where $\chi$​ is real.

**Theorem:** For every $\epsilon > 0$, there exists $c_\epsilon > 0 $ such that 
$$
L(1,\chi) > c_\epsilon \frac{1}{D^{\epsilon}}
$$
**Proof:** First, prove the following proposition.

---

**Proposition:** Fix $\epsilon > 0$. Then $\exists$ real character $\chi_1$ and $1-\epsilon < \beta < 1$ such that 
$$
z(s) = \zeta(s) L(s,\chi_1) L(s,\chi_2) L(s,\chi_1\chi_2)
$$
and $z(s)$ satisfies $z(\beta) \leq 0$ for any real character $\chi_2$. 

**Proof:** Assume $L(\sigma,\chi) \neq 0$ for all $\chi$ real and all $\sigma \in [1-\epsilon, 1]$. 

<u>Case 1:</u> This implies that $z(\beta) < 0$. 

<u>Case 2:</u> $\exists \;\chi_1$ with $L(\beta, \chi_1) = 0$ for $1-\epsilon < \beta < 1$. This implies that $z(\beta) = \zeta(\beta) L(\beta, \chi_1) L(\beta, \chi_2) L(\beta, \chi_1\chi_2) = 0$.  

---

To complete the proof, we have that 
$$
\begin{align*}
1 &\ll \frac{1}{2\pi i} \int_{2-i\infty}^{2+i\infty} z(s+\beta) \frac{x^s}{s(s+1)(s+2)(s+3)(s+4)} \;ds\\
&= \cdots \\
&= \frac{L(1, \chi_1) L(1, \chi_2)L(1,\chi_1\chi_2)}{(1-\beta)(2-\beta)(3-\beta)(4-\beta)(5-\beta)} x^{1-\beta} + \mathcal{O}\left((q_1q_2)^2x^{-B}\right)


\end{align*}
$$
<u>Lemma:</u> $L(1,\chi) \ll \log q$ 

Thus, we end up with the following.
$$
1 \ll \frac{L(1,\chi_2) \log q}{\epsilon} x^\epsilon \implies L(1,\chi_2) \gg_{q_1, \;\beta} \underbrace{q^{L\epsilon}}_{x = q^L}
$$
