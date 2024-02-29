# [2/29] Analytic Number Theory

#### Prime Number Theorem

We have the following function.
$$
z(s) = \frac{1}{2}s(1-s) \;\pi^{-\frac{s}{2}} \;\frac{\Gamma\left(\frac{s}{2} + 1\right)}{\frac{s}{2}}\;\zeta(s) = e^{A+Bs} \prod_{\rho, \;z(\rho) = 0} \left(1-\frac{s}{\rho}\right) e^{\frac{s}{\rho}}
$$
However, since we know that $z(\rho) = 0 \iff \zeta(\rho) = 0$ (non-trivial). So, we can rewrite the product as follows.
$$
= e^{A+Bs} \prod_{\rho, \;\zeta(\rho) = 0} \left(1-\frac{s}{\rho}\right) e^{\frac{s}{\rho}}
$$
We can then rewrite the $\log z(s)$ as follows.
$$
\log z(s) = \log(1-s) - \frac{s}{2}\log \pi + \log \Gamma\left(\frac{s}{2} + 1\right) + \log (\zeta(s))
$$
Similarly, we can show that $\frac{z'}{z}(s)$ is equivalent to the following. 
$$
\begin{align*}
\frac{z'}{z}(s) = \frac{1}{s-1} - \frac{\log \pi}{2} + \frac{1}{2} \cdot \frac{\Gamma'}{\Gamma}\left(\frac{s}{2} + 1\right) + \frac{\zeta'}{\zeta}(s) &= \frac{d}{ds} \log e^{A+Bs} \prod_{\rho, \;z(\rho) = 0} \left(1-\frac{s}{\rho}\right) e^{\frac{s}{\rho}}\\
&= \frac{d}{ds} \left(A+Bs + \sum_{\rho} \left(\log\left(1-\frac{s}{\rho}\right) + \frac{s}{\rho}\right)\right)\\
&= B + \sum_{\rho} \left(\frac{-\frac{1}{\rho}}{1-\frac{s}{\rho}} + \frac{1}{\rho}\right)\\
&= B + \sum_{\rho} \left(\frac{1}{s-\rho} + \frac{1}{\rho}\right)
\end{align*}
$$
This implies the following
$$
\frac{\zeta'}{\zeta}(s) = \frac{1}{1-s} + \frac{\log \pi}{2} - \frac{1}{2} \cdot \frac{\Gamma'}{\Gamma} \left(\frac{s}{2} + 1\right) +B + \sum_{\rho} \left(\frac{1}{s-\rho} + \frac{1}{\rho}\right)
$$

$$
\implies -\frac{\zeta'}{\zeta}(s) = \frac{1}{1-s} - B - \frac{\log \pi}{2} \frac{1}{2} \cdot \frac{\Gamma'}{\Gamma} \left(\frac{s}{2} + 1\right) - \sum_{\rho} \left(\frac{1}{s-\rho} + \frac{1}{\rho}\right)
$$

**Proposition:** Let $\rho = \beta + i\gamma$ run through non-trivial zeroes of $\zeta(s)$, then for $T \rightarrow +\infty$, 
$$
\sum_{\rho = \beta + i\gamma} \frac{1}{4 + (T - \gamma)^2} = \mathcal{O} (\log T)
$$

---

**Corollary:** The number of zeroes if $\rho = \beta + i\gamma$ where $0\leq \beta \leq 1 $ is bounded by $\log T$. 
$$
\#\{\rho = \beta + i\gamma : T \leq \gamma \leq T+1 \;\wedge\;0 \leq \beta \leq 1 \} = \mathcal{O}(\log T)
$$
**Proof (Corollary):** This proposition implies that we can
$$
\implies \sum_{T \leq \gamma \leq T+1} \frac{1}{4 + (T-\gamma)^2} = \mathcal{O}(\log T)
$$

$$
\implies \sum_{T \leq \gamma \leq T+1} 1 = \mathcal{O}(\log T)
$$

---

**Proof of Proposition:** Define $s = 2 + iT$ where $T \geq 2$.  We can use Stirling to bound $= \mathcal{O}(\log T)$. 
$$
\begin{align*}
\Re\left(-\frac{\zeta'}{\zeta} (2 + iT) \right) &= \Re\left(\frac{1}{1+iT}\right) - B - \frac{\log \pi}{2} + \Re\left(\frac{1}{2} \frac{\Gamma'}{\Gamma}\left(\frac{2+iT}{2} + 1\right)\right) - \sum_{\rho} \Re\left(\frac{1}{2+iT - \rho} + \frac{1}{\rho}\right)\\
&= -\sum_{\rho} \left(\Re\left( \frac{1}{2+iT - B - i\gamma}\right) + \Re\left(\frac{1}{B + i\Gamma}\right)\right) + \mathcal{O}(\log T)\\
&= -\sum_{\rho = \beta + i\gamma, \;\zeta(\rho) = 0, \; 0 \leq \beta \leq 1} \underbrace{\left(\frac{2-\beta}{(2-\beta)^2 + (T-\gamma)^2} + \frac{\beta}{\beta^2 + \gamma^2}\right)}_{\geq 0} + \mathcal{O}(\log T)
\end{align*}
$$
Since $\Re\left(-\frac{\zeta'}{\zeta} (2 + iT) \right) = \mathcal{O}(1)$, then we have the following final bound.
$$
\sum_{\rho} \left(\frac{2-\beta}{(2-\beta)^2 + (T-\gamma)^2} + \frac{\beta}{\beta^2 + \gamma^2}\right) = \mathcal{O}(\log T) \implies \sum_{\rho} \left(\frac{2-\beta}{(2-\beta)^2 + (T-\gamma)^2}\right) = \mathcal{O}(\log T)
$$
 Finally, we can conclude the desired result based on the following intuition.
$$
\frac{2-\beta}{(2-\beta)^2 + (T-\gamma)^2} \geq \frac{1}{4 + (T-\gamma)^2}
$$
**Note:** The hardest part of the Perron formula is as follows.
$$
\sum_{|\gamma| \leq T} \frac{x^\beta}{\beta + i\gamma} = \sum_{k = 1, \;k \leq |\gamma| \leq k+1}^{T-1} \frac{x}{k}\log(k) = \mathcal{O}\left(x(\log T)^2\right)
$$
We want to show that $\beta < 1$ so that we can show a value less than $x$. 

---

#### De La Valee Poussin

**Theorem:** There exists $c > 0$ such that for all $T \geq 2$, there are no zeroes of $\zeta(\sigma + it)$ in the region $|t| \leq T$ and $\sigma \geq 1 - \frac{c}{\log T}$. 

**Proof:** First, we use the following elementary theorem $3 + 4 \cos (\theta) + \cos (2 \theta) = 2 (1 + \cos \theta)^2 \geq 0$.  
$$
-\frac{\zeta'}{\zeta} (s) = \sum_{n=1}^\infty \frac{\Lambda(n)}{n^s} = \sum_{1}^\infty \frac{\Lambda(n)}{n^\sigma} e^{-(\log n) it}
$$

$$
\Re\left(-\frac{\zeta}{\zeta} (\sigma + it)\right) = \sum_{n=1}^\infty \frac{\Lambda (n)}{n^\sigma} \cos(t \log n)
$$

$$
\begin{align*}
\implies \Re\left(-3 \frac{\zeta'}{\zeta}(\sigma) - 4 \frac{\zeta'}{\zeta}(\sigma + it) - \frac{\zeta'}{\zeta}(\sigma + 2it)\right) &= \sum_{n=1}^\infty \frac{\Lambda(n)}{n^\sigma} \left(3 + 4 \cos(t \log n) + \cos(2 + \log n)\right) \\
&\geq 0
\end{align*}
$$

So, the formula that we want to use is as follows where $\sigma > 1$. 
$$
\Re\left(-3 \frac{\zeta'}{\zeta}(\sigma) - 4 \frac{\zeta'}{\zeta}(\sigma + it) - \frac{\zeta'}{\zeta}(\sigma + 2it)\right) \geq 0
$$
**Step 1:** For $\sigma > 1 + \epsilon$, we've already proved the following result.
$$
-\frac{\zeta'}{\zeta}(\sigma) < \frac{1}{\sigma - 1} + \mathcal{O}_\epsilon(1)
$$
This implies the following result.
$$
\frac{3}{\sigma - 1} + \Re\left( -4\frac{\zeta'}{\zeta}(\sigma + it) - \frac{\zeta'}{\zeta}(\sigma + 2it)\right) + \mathcal{O}(1) \geq 0
$$
**Step 2:** Set $s = \sigma + it$ where $\sigma > 1$ and $T \geq 2$ and $|t| \leq T$. 
$$
\begin{align*}
\Re\left(\frac{\zeta'}{\zeta}(s)\right) &= -\sum_{\rho} \underbrace{\left(\Re\left(\frac{1}{s-\rho}\right) + \Re\left(\frac{1}{\rho}\right)\right)}_{\geq 0} + \mathcal{O}(\log T)\\
\end{align*}
$$
Now, fix one zero $\rho_0 = \beta_0 + i\gamma_0$. This implies the following.
$$
-\frac{\zeta'}{\zeta}(\sigma + it) = \frac{1}{\sigma - \beta_0} + \mathcal{O}(\log T)
$$
This is because of the proposition that
$$
\Re\left(\frac{1}{\sigma + iT - \beta_0}\right) = \frac{\sigma - \beta_0}{(\sigma - \beta_0)^2 + (t-\gamma_0)^2} \leq \frac{1}{\sigma - \beta_0}
$$
Using the formula above for $-\frac{\zeta'}{\zeta}(s)$, we have the result.
$$
\frac{4}{\sigma - \beta_0} < \frac{3}{\sigma - 1} + \mathcal{O}(\log T)
$$
Choose some $\sigma = 1 + \frac{\delta}{\log T}$ and for some $c > 0$.  
$$
\begin{align*}
\beta_0 &< 1 + \frac{\delta}{\log T} - \frac{4\delta}{3 + \mathcal{O}(\log T)}\\
&< 1 - \frac{c}{\log T}
\end{align*}
$$