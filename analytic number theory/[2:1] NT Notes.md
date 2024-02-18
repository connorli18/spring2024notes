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
$$
\int_a^b f'(t)g(t)\;dt = (f(b)g(b) - f(a)g(a)) - \int_a^b f(t)g'(t)\;dt
$$
Apply it to $\mathcal{Li}(x)$. 
$$
\mathcal{Li}(x) = \int_0^x 1 \frac{1}{\log (t)}\;dt = \frac{x}{\log(x)} - \frac{2}{\log(2)} - \int_2^x t\left(\frac{-1}{(\log t)^2}\right) \cdot \frac{1}{t} \;dt
$$
Now, we are left with the following formula.
$$
\begin{align*}
\mathcal{Li}(x) &= \frac{x}{\log (x)} + \int_2^x \frac{dt}{(\log t)^2} + \mathcal{O}(1)
\end{align*}
$$
We also have the following trick from Euler.
$$
\frac{d}{dy} \left(\frac{1}{\log y}\right) = \frac{-1}{(\log y)^2} \cdot \frac{1}{y} \implies \int_p^x \frac{-1}{(\log y)^2} \frac{1}{y} \;dy = \eval{\frac{1}{\log y}}_p^x = \frac{1}{\log x} - \frac{1}{\log p}
$$
This gives us the following.
$$
\sum_{p \leq x} \int_p^x \frac{dy}{(\log y)^2 \cdot y} = \int_2^x \sum_{2 \leq p \leq y} \frac{\log p}{y\cdot (\log y)^2}\;dy = \sum_{p \leq x} \left(\frac{1}{\log x} - \frac{1}{\log p}\right) = \pi(x) - \frac{\theta(x)}{\log(x)}
$$
Since we know that $\theta(x) = x + \mathcal{O}( x^{\frac{1}{2} + \epsilon})$ and $\theta(y) = y+ \mathcal{O}() y^{\frac{1}{2} + \epsilon})$, we can show intermediate steps.
$$
\int_2^x \frac{y + \theta(y^{\frac{1}{2} + \epsilon})}{y \cdot (\log y)^2} \;dy = \frac{dy}{(\log y)^2} + \theta(x^{\frac{1}{2}+\epsilon}) = \cdots
$$
This implies the following asymptotic formula.
$$
\begin{align*}
&\implies \mathcal{Li}(x) - \frac{x}{\log x} = \pi(x) - \frac{x}{\log x} + \theta(x^{\frac{1}{2} + \epsilon})\\
&\implies \pi(x) = \mathcal{Li}(x) + \mathcal{O}(x^{\frac{1}{2} + \epsilon})
\end{align*}
$$

#### Functional Equation

**Theorem:** Our main goal is to prove the functional equation.
$$
z(s) = \pi^{-\frac{s}{2}} \cdot \Gamma\left(\frac{s}{2}\right) \zeta(s) = z(1-s)
$$
**Proof:** This requires Fourier analysis.

----

**Fourier Theorem:** Assume $f: \mathbb{R} \rightarrow \mathbb{C}$ and $f$ is periodic, i.e. $f(x+1) = f(x) \quad\forall \;x \in \mathbb{R}$ . Assume $f$ is smooth, then $f(x)$ has a Fourier expansion of the following form, which converges absolutely and uniformly on compact subsets of $\mathbb{R}$. 
$$
f(x) = \sum_{n=-\infty}^\infty a_ne^{2\pi i nx}
$$
Furthermore, we have the following definitions for $a_n$.
$$
\hat{f}_n = \int_0^1 f(t)e^{-2\pi itn}\;dt
$$
**Proof of (12):** Assume that we have $(11)$.  
$$
a_k = \int_0^1 f(t) e^{-2\pi i k t}\;dt = \int_0^1 \sum_{n=\infty}^\infty a_n e^{2\pi i (n-k)t}\;dt
$$
Assuming $\ell \in \mathbb{Z}$, we have the following property.
$$
\int_0^1 e^{2\pi i \ell t}\;dt = \begin{cases} 
1 & \ell = 0\\
0 & \ell \neq 1
\end{cases}
$$
Using the above property, we can then finish the rest of the proof.
$$
\int_0^1 \sum_{n=\infty}^\infty a_n e^{2\pi i (n-k)t}\;dt = a_k
$$
**Proof of (11):** This is the more difficult proof. The first thing we want to show is that if there exists an expansion, then it converges. Assume that an expansion exists.
$$
a_n = \int_0^1 f(t) e^{-2\pi i n t }\;dt = -\int_0^1 \frac{f'(t) e^{2\pi i n t}}{-2 \pi i n}\;dt = \left|\int_0^1 \frac{f''(t) e^{-2\pi i n t}}{(2\pi i n)^2} \;dt \right| \ll \frac{1}{n^2}
$$
Thus, we know that it converges. Now, we have to prove that $(11)$ exists. We will do this in $3$​ steps.

-----

<u>**Step 1**</u>: It is enough to prove $f(0) = \sum_{n=-\infty}^\infty \hat{f}_n$ . 

**Proof:** Define $g(x) := f(x+x_0)$
$$
f(x_0) = g(0) = \sum_{n=-\infty}^\infty\int_0^1 f(t+x_0)\;dt = \sum_{n=-\infty}^\infty \hat{g}_n
$$
Now, let's take a look at the $n$-th coefficinet of $g(x)$.
$$
\begin{align*}
\hat{g}_n &= \int_0^1 g(t) e^{-2\pi i n t}\;dt = \int_0^1 f(t + x_0) e^{-2\pi i n t} \;dt \\
&= \int_{x_0}^{x_0+1} f(t)e^{2\pi i n (t-x_0)}\;dt = e^{2\pi i n x_0} \cdot \hat{f}_n
\end{align*}
$$


**<u>Step 2</u>**: We can assume $f(0) = 0$. This implies that the Fourier Expansion holds for all $f$. Simply, we use $f(x) - f(0)$ to finish the proof. 

**<u>Step 3:</u>** We are reduced to considering functions which are periodic, smooth, and vanishing at $x = 0$. We only need to prove the following.
$$
\sum_{n=-\infty}^\infty \hat{f}(n) = 0
$$
**Proof:** Since $f(0) = 0$, we can define a new function 
$$
g(x) := \frac{f(x)}{1-e^{2\pi i x}} \implies \lim_{x\rightarrow 0} \frac{f'(0)}{-2\pi i} 
$$
Next, we show that
$$
\begin{align*}
\hat{f}_n = \int_0^1 f(x) e^{-2\pi i n x}\;dx &= \int_0^1 \left(1-e^{2\pi i x}\right)  g(x) e^{-2\pi i n x}\;dx\\
&= \int_0^1 g(x) e^{-2\pi i nx}\;dx - \int_0^1 g(x)e^{-2\pi i (n-1)x}\;dx\\
&= \hat{g}_n - \hat{g}_{n-1} \implies \sum_{n} \hat{g}_n - \hat{g}_{n-1} = 0
\end{align*}
$$

-----

#### Fourier Precursors

**Fourier Transform:** This is the transform formula - will be proven next class.
$$
\hat{f}(x) = \int_{-\infty}^\infty f(t)e^{-2\pi i nx}\;dt
$$