# [1/18] Number Theory

### Review

**Definition:** We define the $\zeta$ function as follows where $s \in \mathbb{C}$ and $s = \sigma + it$. 
$$
\zeta(s) = \sum_{n=1}^\infty \frac{1}{n^s}
$$

### Euler Primes

**Theorem:** We define $p$ as the set of all prime numbers.
$$
\zeta(s) = \prod_{p} \left(1-\frac{1}{p^s}\right)^{-1} = \left(1-\frac{1}{2^s}\right)^{-1}\left(1-\frac{1}{3^s}\right)^{-1}\left(1-\frac{1}{5^s}\right)^{-1}\dots
$$
**Definition:** 
$$
P(\sigma) = \prod_{n=1}^\infty \left(1+\frac{1}{n^\sigma}\right) = \lim_{N\rightarrow\infty} \prod_{n=1}^N \left(1+\frac{1}{n^\sigma}\right)
$$
**Proposition:** For $\sigma > 1$, the product defined above converges.

**Preliminaries:** Using the Taylor series expansion, we have that
$$
\log(1+x) = \sum_{k=1}^\infty (-1)^{k+1}\frac{x^k}{k}
$$
**Proof:** 

Re-indexing the $n=1 \rightarrow n=2$, we have the following. 
$$
P(\sigma) = 2\prod_{n=2}^\infty \left(1+\frac{1}{n^\sigma}\right)
$$

$$
\log(P(\sigma)) = \log(2) + \sum_{n=2}^\infty \log\left(1+\frac{1}{n^\sigma}\right)
$$

Thus, we simply need to show that the rightmost term converges to show that the whole product converges.
$$
\sum_{n=2}^\infty \log\left(1+\frac{1}{n^\sigma}\right) = \sum_{n=2}^\infty \sum_{k=1}^\infty \frac{(-1)^{k+1} n^{-k\sigma}}{k}
$$

$$
\left|\sum_{n=2}^\infty \log\left(1+\frac{1}{n^\sigma}\right)\right| \leq \sum_{n=2}^\infty \sum_{k=1}^\infty \frac{n^{-k\sigma}}{k} \leq \sum_{n=2}^\infty \left(n^{-\sigma} + n^{-2\sigma} + n^{-3\sigma} + \cdots\right)
$$

$$
\leq \sum_{n=2}^\infty n^{-\sigma} \left(1 + n^{-\sigma} + n^{-2\sigma} + n^{-3\sigma} + \cdots\right) \leq \sum_{n=2}^\infty n^{\sigma} \left(1 + \frac{1}{2} + \frac{1}{4} + \dots\right) \leq 2 \zeta(\sigma)
$$

This converges for $\sigma > 1$. 

**Proposition:** For $s \in \mathbb{C}$, with $\Re(s) > 1$ , the product $\prod_{n=1}^\infty \left(1 \pm \frac{1}{n^s}\right)^{\pm 1}$ converges absolutely. 

### Euler Product

**Theorem:** $\zeta(s) = \prod_p \left(1 - \frac{1}{p^s}\right)^{-1}$ if $s \in \mathbb{C}$ and $\Re(s) > 1$. 

-  As $s \rightarrow 1$, then there are infinitely many primes, since the product blows up! We know this because $\zeta(1)$ is the harmonic series, which we know diverges. 

**Proof:**  First, Euler multiples by the constant term to eliminate all even numbers from the series.
$$
(1 - 2^{-s}) \cdot \zeta(s) = 1 + \frac{1}{3^s} + \frac{1}{5^s} + \cdots
$$
Then, he multiplies the term again to eliminate all numbers divisble by (3) and divisible by (2) from the step above.
$$
(1-3^{-s})(1-2^{-s}) \cdot \zeta(s) = 1+\frac{1}{5^s} + \frac{1}{7^s} + \frac{1}{11^s} + \cdots
$$
Then, get rid of the multiples of five. Notice that both sides converge as long as $s > 1$.
$$
(1-5^{-s})(1-3^{-s})(1-2^{-s}) \cdot \zeta(s) = 1 + \frac{1}{7^{s}} + \frac{1}{11^s} + \cdots
$$
Now, imagine for some very large prime $p_l$, we have the following result.
$$
(1- p_l^{-s}) \cdots (1 - 2^{-s}) \cdot \zeta(s) = 1 + \frac{1}{p^s_{l+1}} + \cdots
$$

$$
\lim_{l\rightarrow\infty} (1- p_l^{-s}) \cdots (1 - 2^{-s}) \cdot \zeta(s) = 1
$$

**Theorem (Euler):** $\sum_p \frac{1}{p} = \infty$ 

**Proposition:** For fixed $\epsilon > 0$ and $1 < \sigma \leq 1 + \epsilon$, we have that
$$
\left(\sum_p p^{-\sigma} - \log\frac{1}{\sigma-1}\right) < \zeta(2) + \epsilon
$$
**Lemma:** For $\sigma > 1$
$$
\frac{1}{\sigma-1} < \zeta(\sigma) < \frac{1}{\sigma - 1} + 1 = \frac{\sigma}{\sigma + 1}
$$
**Proof:** 
$$
\int_{n}^{n+1} x^{-\sigma} \;dx = \frac{(n+1)^{1-\sigma}}{1-\sigma} - \frac{n^{1-\sigma}}{1-\sigma}
$$
We can bound the integral as follows.
$$
(n+1)^{-\sigma} < \int_{n}^{n+1} x^{-\sigma} \;dx < n^{-\sigma} \implies (n+1)^{-\sigma} < \frac{n^{1-\sigma} - (n+1)^{1-\sigma}}{\sigma-1} < n^{-\sigma}
$$
If you sum over $n$, then we have that.
$$
\sum_{n=1}^\infty \frac{n^{1-\sigma} - (n+1)^{1-\sigma}}{\sigma-1} = \frac{1}{\sigma-1}
$$
Thus, we can propose the bounds.
$$
\zeta(\sigma) - 1 < \frac{1}{\sigma-1} < \zeta(s)
$$
**Theorem (Euler):** 
$$
\left| \sum_{p} p^{-\sigma} - \log\frac{1}{\sigma - 1} \right| < \zeta(2) + \epsilon
$$
We just proved the lemma such that
$$
\log \frac{1}{\sigma-1} \leq \log \zeta(\sigma) \leq \log \frac{\sigma}{\sigma - 1}
$$
We also know the following, which we can find from the Taylor series expansion.
$$
\log(\sigma) < \sigma - 1 \implies \left|\log \zeta(\sigma) - \log\frac{1}{\sigma-1}\right| < \sigma - 1 = \epsilon
$$
We also have that
$$
\log \zeta(\sigma) = \sum_p -\log(1-p^{-\sigma})
$$

$$
\sum_p p^{-\sigma} - \sum_p -\log(1-p^{-\sigma}) < \sum_p p^{-2\sigma} \leq \zeta(2)
$$

### The Gamma Function

**Definition:** The Gamma Function is defined as follows.
$$
\Gamma(s) = \int_0^\infty e^{-u}u^s \frac{du}{u}
$$
**Lemma:** If $0 \leq n \in \mathbb{Z}$, then we have
$$
\Gamma(n+1) = n!
$$
**Proof:** 
$$
\Gamma(s) = \int_0^\infty e^{-u} u^{s-1}\;du = \int_0^\infty -e^{-u} (s-1) u^{s-2}\;du = (s-1)\int_0^\infty e^{-u}u^{s-1}\;du
$$
Thus, we have the following conclusion.
$$
\Gamma(s) = (s-1)\Gamma(s-1) 
$$
Since we know that $\Gamma(1) = 1$, we can draw the conclusion above.

**Proposition:** The integral $\Gamma(s)$ converges absolutely if $\Re(s) > 0$.   

**Proof:** We know the following is true.
$$
\left|u^s\right| = \left|u^\sigma \cdot u^{it}\right| = \left|u^\sigma e^{it\log u}\right| = u^\sigma
$$
We need to prove that $\int_0^\infty e^{-u} u^\sigma \;\frac{du}{u}$ converges for $\sigma > 0$. This is true because
$$
\int_0^\epsilon \frac{1}{u^\delta} \;du = \frac{e^{1-\delta}}{1-\delta} \neq \infty
$$
**Functional Equation:**
$$
\Gamma(s+1) = s\Gamma(s)
$$
**Question:** What is $\Gamma(s)$ when $s = 0$?
$$
\Gamma(s) = \frac{\Gamma(s+1)}{s} \implies \lim_{s\rightarrow 0} \Gamma(s) = \infty
$$
This implies that $\Gamma(s)$ has a simple pole at $s = 0$ with residue $=1$. Also, it has poles at all of the negative integer values.