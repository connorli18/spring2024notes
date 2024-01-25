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
**Proof (of claim):** 
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
