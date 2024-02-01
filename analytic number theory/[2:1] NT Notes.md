# [2/1] Number Theory

#### Last Time

Assuming the Reimann Hypothesis, we have the following formula.
$$
\psi(x) = \sum_{n \leq x} \Lambda(n) = \sum_{p^k \leq x} \log p = x + \mathcal{O}(x^{\frac{1}{2} + \epsilon} )
$$

#### The Goal

We also want to introduce the following functions.
$$
\theta(x) = \sum_{p \leq x} \log p
$$

$$
\pi(x) = \sum_{p \leq x} 1
$$

The goal is to prove the prime number theorem (this is a better approximation that $\frac{x}{\log(x)}$. 
$$
\pi = \mathcal{Li}(x) + O(x^{\frac{1}{2} + \epsilon}) \quad \quad \text{where}\quad \quad  \mathcal{Li}(x) = \int_2^x \;\frac{dt}{\log t}
$$
Via calculator, we have that $\mathcal{Li}(x)$ is far more accurate than $\frac{x}{\log (x)}$. 

|                | $\frac{\pi(x)}{\frac{x}{\log(x)}}$ | $\frac{\pi(x)}{\mathcal{Li(x)}}$ |
| -------------- | ---------------------------------- | -------------------------------- |
| $\pi(10^8)$    | 1.06                               | .9999                            |
| $\pi(10^{10})$ | 1.03                               | .9999                            |
| $\pi(10^{16})$ | 1.02                               | .9999                            |

#### Proving $\mathcal{Li}(x)$ 

**Steps:**

1. $\psi(x) \implies \theta(x) = x + \theta(x^{\frac{1}{2} + \epsilon})$ 
2. $\theta(x) \implies \pi(x) = \mathcal{Li}(x) + \mathcal{O}(x^{\frac{1}{2} + \epsilon})$ 

**Step 1:**
$$
\begin{align*}
	\psi(x) &= \sum_{p \leq x} \log (p) + \sum_{p^2 \leq x} \log(p) + \sum_{p^3 \leq x} \log(p) + \dots + \sum_{p^k \leq x} \log(p)\\
	&= \theta(x) + \mathcal{O}\left(x^{\frac{1}{2} + \epsilon}\right)
\end{align*}
$$

- <u>Note</u>: You know that each term after $\theta(x)$ is bounded by $x^{\frac{1}{2} + \epsilon}$ and $k$ is bounded as $\log (p)$, which means that it is finite.

**Step 2:**

First, use integration by parts.