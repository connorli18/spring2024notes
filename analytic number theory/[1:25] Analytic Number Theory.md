# [1/25] Analytic Number Theory

### Riemann

- **Riemann's Paper of 1859:** The number of primes less than a given quantity.

**Introduction:** Meromorphic continuation of $\zeta(s) = \sum_{1}^\infty \frac{1}{n^s}$ to $\Re(s) > 0$. 

**Proof:** Start with the following integral where $\Re(s) > 1$.  
$$
\int_1^\infty x^{-s}\;dx = \frac{1}{s-1}
$$
This implies the following.
$$
\begin{align*}
	\zeta(s) - \frac{1}{s-1} &= \sum_{n=1}^\infty \frac{1}{n^s} - \int_1^\infty x^{-s}\;dx \\
	&= \sum_{n=1}^\infty \int_n^{n+1}  (n^{-s}-x^{-s})\;dx
\end{align*}
$$
Now, define $h_n(s) = \int_n^{n+1} (n^{-s}-x^{-s})\;dx$​. I claim the following is true.
$$
|h_n(s)| < |s| n^{-\sigma-1} \text{ where } \sigma = \Re(s) > 0
$$
Assuming the claim, this tells us that $h_n$ is bounded, which means it is a holomorphic function of $s$. 
$$
\begin{align*}
&\implies \zeta(s) - \frac{1}{s-1} = \sum_{n=1}^\infty h_n(s) \\
&\implies \sum_{n=1}^\infty |h_n(s)| < |s| \sum_{n=1}^\infty \frac{1}{n^{\sigma+1}} < \infty
\end{align*}
$$
**Proof (of claim):** We start with the following.
$$
\begin{align*}
	|h_n(s)| \leq \int_n^{n+1} |n^{-s} - x^{-s}| \;dx\\
	
\end{align*}
$$
We can rewrite the internal sum via the following conversion: 
$$
|n^{-s} - x^{-s}| = \left|\int_n^{n+1} su^{-s-1}\;du\right| \leq |s| \int_n^{n+1} u^{-\sigma-1}\;du \leq |s|n^{-\sigma-1}
$$
 Applying the bound to the above equation, we can complete the proof for the claim.
$$
|h_n(s)| \leq |s| n^{-\sigma-1}
$$

****

**Perron's Formula:** Let $c,y > 0$. 
$$
\lim_{T\rightarrow\infty} \int_{C-iT}^{C+iT} y^s \;\frac{ds}{s} = \begin{cases}
	1 &y > 1\\
	\frac{1}{2} &y=1\\
	0 &0<y<1
\end{cases}
$$
Let $Z(s) = \sum_{n=1}^\infty \frac{a(n)}{n^s}$ be an infinite series that converges absolutely for $\Re(s) > 1$. Now, let's integral transform $Z(s)$. 
$$
\frac{1}{2\pi i} \int_{C-i\infty}^{C+i\infty} Z(s) y^s\;\frac{ds}{s} = \sum_{n=1}^\infty a(n) \cdot \frac{1}{2\pi i} \int_{C-i\infty}^{C+i\infty} \left(\frac{y}{n}\right)^s\;\frac{ds}{s} = \sum_{n \leq y} a(n)
$$
 We want to construct a function where $a(n)$ is basically a prime numbers. Reimann used the function below.
$$
\begin{align*}
\log(\zeta(s)) &= \log\left(\prod_p \left(1-\frac{1}{p^s}\right)^{-1}\right) \\
&= -\sum_p \log\left(\prod_p \left(1-\frac{1}{p^s}\right)\right)\\
&= \sum_p \sum_{k=1}^\infty \frac{p^{-ks}}{k}
\end{align*}
$$
This allows us to convert the integral transform into the following.
$$
\frac{1}{2\pi i} \int_{C-i\infty}^{C+i\infty} \log\zeta(s) x^s \;\frac{ds}{s} = \sum_p \sum_{k=1}^\infty \frac{1}{k} \cdot \frac{1}{2\pi i} \int_{C-i\infty}^{C+i\infty} \left(\frac{x}{p^k}\right)^s \;\frac{ds}{s}
$$
Applying Perron, we have.
$$
\begin{align*}
\frac{1}{2\pi i} \int_{C-i\infty}^{C+i\infty} \log\zeta(s) x^s \;\frac{ds}{s} &= \sum_{k=1}^\infty \frac{1}{k} \sum_{p^k \leq x} 1\\
&= \pi(x) + \sum_{k=2}^\infty \frac{1}{k} \sum_{p^k \leq x} 1\\
&= \pi(x) + \text{Error}(x) 
\end{align*}
$$
We also know that $\text{Error}(x) \leq \sqrt{x}$ . 

---

### Riemann Hypothesis 

**Conjecture:** All zeroes of $\zeta(s)$ for all $\Re(s) > 0$ are on the line $\Re(s) = \frac{1}{2}$​. 

- $\overline{\zeta(s)} = \zeta(\overline{s})$ 
- Reimann also showed the functional equation $s \rightarrow 1-s$. 
