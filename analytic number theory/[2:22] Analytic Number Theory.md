# [2/22] Analytic Number Theory

#### Hadamard Order of Entire Functions

**Definition:** Let $f: \mathbb{C} \rightarrow \mathbb{C}$ be entire. Let $0 < \alpha$ be minimal such that for all $\epsilon > 0$ and $z \in \mathbb{C}$ 
$$
|f(z)| \ll_{\epsilon} e^{|z|^{\alpha + \epsilon}}
$$
**Theorem:** (Hadamard) Let $f$ be an entire function of finite order $\alpha$. Let $0 \leq |rho_1| \leq |rho_2| \leq |rho_3| \leq \dots$ and $f(rho_i) = 0$ for all $\rho_i$. Then, for every $\epsilon > 0$, 
$$
\sum_{k=1}^\infty |\frac{1}{|\rho_k|^{\alpha + \epsilon}} < \infty
$$

---

**Claim:** $s(1-s)\pi^{-\frac{s}{2}} \Gamma\left(\frac{s}{2}\right) \zeta(s)$ is an entire function of Hadamard order $=1$. 

**Proof of Claim:** First of all $z(s) = z(1-s) \implies$ it is enough to prove the bound $(1)$ with $\alpha = 1$ for $\Re(s) \geq \frac{1}{2}$.  
$$
\left|s(1-s) \pi^{-\frac{s}{2}}\right| \ll e^{|s|} \quad \quad \quad \quad \left|\Gamma\left(\frac{s}{2}\right)\right| \ll e^{|s|\log s}
$$

$$
\left|s(1-s) \pi^{-\frac{s}{2}}\right| \ll e^{{|s|}^{1+\epsilon}} \quad \quad \quad \quad \left|\Gamma\left(\frac{s}{2}\right)\right| \ll e^{{|s|}^{1+\epsilon}}
$$



The second bound for $\Gamma$ comes from Stirling. We can thus bound by the larger bound(s),
$$
|\zeta(s)| \ll |s|^2
$$
This also implicates Hadamond's Theorem.
$$
\implies \sum_{k=1}^\infty \frac{1}{|\rho_k|^{1 + \epsilon}} < \infty
$$
**Lindelof Conjecture:** $|\zeta(s)| \ll \left(1+|s|\right)^{\epsilon}$ for $\Re(s) \geq \frac{1}{2}$. 

---

**Theorem**: (Jensen's Formula) Let $f: \mathbb{C} \rightarrow \mathbb{C}$ be a holomorphic function with no zeroes in $|z| \leq R$ for $R > 0$ (in the circle with radius $R$ in $\mathbb{C}$). Then, 
$$
\frac{1}{2\pi}\int_0^{2\pi} \log \left(\left|f\left(Re^{i\theta}\right)\right|\right)\;d\theta = \log |f(0)|
$$
**Proof** (of Jensen): We know that $\log f(z)$ is holomorphic in $|z| \leq R$. This implies that
$$
\frac{1}{2\pi i} \int_{|z| = R} \underbrace{\frac{\log f(z)}{z}\;dz}_{z = Re^{i\theta}}  = \log f(0)
$$
For the change of variables above, we also have $z = Re^{i\theta}$ and $dz = Rie^{i\theta}\;d\theta$. 
$$
\frac{1}{2\pi} \int_{\theta = 0}^{2\pi }\log\left(f\left(Re^{i\theta}\right)\right) \; d\theta = \log(f(0))
$$
To show the absolute values, let's use the expansion.
$$
\begin{align*}
\log\left(Re^{i\theta}\right) &= \log R + i\theta\\
\Re\left(\log\left(Re^{i\theta}\right)\right) &=\log R \\
\Re\left(\log\left(f(Re^{i\theta})\right)\right) &= \log \left|f(Re^{i\theta})\right|
\end{align*}
$$
We also have the final statement.
$$
\begin{align*}
\frac{1}{2\pi}\int_0^{2\pi} \log \left(\left|f\left(Re^{i\theta}\right)\right|\right)\;d\theta &= \Re\left(\frac{1}{2\pi i} \int_{|z| = R} \frac{\log f(z)}{z}\;dz\right)\\
&= \Re\left(\frac{1}{2\pi} \int_{\theta = 0}^{2\pi }\log\left(f\left(Re^{i\theta}\right)\right) \; d\theta\right) \\
&= \Re(\log f(0)) \\
&= \log |f(0)|
\end{align*}
$$

----

**Theorem:** (Generalized Jensen Formula) Let $f(z)$ be holomorphic in $|z| \leq R$ with zeroes $\rho_, \rho_2, \dots, \rho_n$ inside $|z| \leq R$. Assume $f(0) \neq 0$. Then,
$$
\frac{1}{2\pi i } \int_0^{2\pi} \log\left|f\left(Re^{i\theta}\right)\right|\;d\theta = \log\left|f(0)\right| + \log\left(\frac{R^n}{|\rho_1|\cdot |\rho_2| \cdots |\rho_n|}\right)
$$
**Proof** (of Generalized Jensen's): Define $F(z) = f(z) \cdot \prod_{k=1}^n \frac{R^2 - \overline{\rho_k} \cdot z}{R(z - \rho_k)}$. Note that $F(z) \neq 0$ for $|z| \leq R$. 

<u>Claim</u>: I claim that $\left|F(Re^{i\theta})\right| = \left|f(Re^{i\theta})\right|$. 

 <u>Proof:</u> This is equivalent to the following statement.
$$
\begin{align*}
\left|F(Re^{i\theta})\right| = \left|f(Re^{i\theta})\right| &\iff \prod_{k=1}^n \left|\frac{R^2 - \overline{\rho_k} \cdot Re^{i\theta}}{R(Re^{i\theta} - \rho_k)}\right| = 1\\
&= \prod_{k=1}^n \left| \frac{R-\overline{\rho_k} e^{i\theta}}{Re^{i\theta} - \rho_k} \right|\\
&= \prod_{k=1}^n \left| \frac{Re^{-i\theta}-\overline{\rho_k}}{Re^{i\theta} - \rho_k} \right| = 1
\end{align*}
$$
We can apply Jensen's first formula to $F(z)$. 
$$
\begin{align*}
\implies \frac{1}{2\pi} \int_0^{2\pi} \log\left|F(Re^{i\theta})\right|\;d\theta &= \log|F(0)|\\
&= \log f(0) +  \sum_{k=1}^n \log \left(\frac{R^2}{R \rho_k} \right)\\
&= \log\left|f(0)\right| + \log\left(\frac{R^n}{|\rho_1|\cdot |\rho_2| \cdots |\rho_n|}\right)
\end{align*}
$$

---

**Claim**: Take the generalized version of the Jensen's formula and let $n(r) =$ \\# of zeroes of $f(z)$ inside $|z| \leq r$.  
$$
\log\left(\frac{R^n}{|\rho_1|\cdot |\rho_2| \cdots |\rho_n|}\right) = \int_0^R \frac{n(r)}{r}\;dr
$$
**Proof:** Let $r_1 = |\rho_1|$, $r_2 = |\rho_2|$ $\dots$ $r_n = |\rho_n|$ where $r_1 \leq r_2 \leq \cdots \leq r_n$. 
$$
\begin{align*}
\int_0^R \frac{n(r)}{r} \;dr &= \int_0^{r_1} \frac{n(r)}{r}\;dr + \int_{r_1}^{r_2} \frac{n(r)}{r}\;dr + \dots + \int_{r_{n-1}}^{r_n} \frac{n(r)}{r}\;dr\\
&= \log \frac{r_2}{r_1} + 2 \log \frac{r_3}{r_2} + \dots + n \log \frac{R}{r_n} \\
&= \log\left(\frac{R^n}{r_1r_2\cdots r_n}\right)
\end{align*}
$$

---

**Theorem:** (Hadamar's Theorem) Let $f(z)$ have order $\alpha$. Then, $n(R) \ll R^{\alpha + \epsilon}$. 

**Proof:** Finite order $\alpha$ implies that $\log\left|f(Re^{i\theta})\right| \ll_\epsilon R^{\alpha + \epsilon}$. Using Jensen, we also have the following.
$$
\log |f(0)| + \int_0^{2R} \frac{n(r)}{r}\;dr \ll R^{\alpha + \epsilon} \implies \int_0^{2R} \frac{n(r)}{r}\;dr \ll R^{\alpha + \epsilon}
$$
This also means that we can algebraically show the following.
$$
\begin{align*}
n(R) \log 2 = n(R) \int_R^{2R} \frac{dr}{r} \leq \int_R^{2R} \frac{n(r)}{r}\;dr \ll R^{\alpha + \epsilon}
\end{align*}
$$
Finally, we prove the following.
$$
\sum_{k=1}^\infty \frac{1}{|\rho_k|^{\alpha + \epsilon}} < \infty
$$
<u>Claim</u>: For all $\beta > 0$ , we have
$$
\sum_{k=1}^\infty \frac{1}{|\rho_k|^\beta} = \int_{r_1}^\infty n(r)\beta r^{-\beta - 1}\;dr
$$
Assuming the claim is true, we can choose $\beta = \alpha + \epsilon$ and show that the bound is as follows.
$$
\sum_{k=1}^\infty \frac{1}{|\rho_k|^{\alpha + \epsilon}} \ll \int_{r_1}^\infty r^{\alpha + \epsilon} (\alpha + \epsilon) r^{-\alpha - 1 - 2 \epsilon} \;dr < \infty
$$
<u>Proof of Claim</u>: Let $r_j = |\rho_j|$. 
$$
\begin{align*}
\int_{r_1}^\infty n(r)\beta r^{-\beta - 1} &= \sum_{k=1}^\infty n(r_k) \int_{r_k}^{r_{k+1}} \beta r^{-\beta - 1}\;dr\\
&= \sum_{k=1}^\infty n(r_k) \left(r_k^{-\beta} - r_{k+1}^{-\beta}\right) \\
&= \sum_{k=1}^\infty \underbrace{\left(n(r_k) - n(r_{k-1})\right)r^{-\beta}_k}_{n(r_k) - n(r_{k-1}) = \#\{\rho_i | \rho_i = \rho_k\}}\\
&= \sum_{k=1}^\infty |\rho_k|^{-\beta}
\end{align*}
$$
