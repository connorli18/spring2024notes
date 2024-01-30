# [1/30] Analytic Number Theory

#### Introduction

**Theorem (Perron):** Let $c, t,y > 0$. Then,
$$
\frac{1}{2\pi i}\int_{c-i\infty}^{c+i\infty} y^s \;\frac{ds}{s} = \begin{cases}
	1 + O\left(y^c \min\left(1,\frac{1}{T \cdot \log(y)}\right)\right) &y \geq 1\\
	y^c \min\left(1,\frac{1}{T \cdot \log(y)}\right) &0 < y < 1
\end{cases}
$$
**Goal #1:** $\pi(x) \backsim \frac{x}{\log(x)}$, and Gauss conjectured that $\pi(x) \backsim y_i(x) := \int_2^x \frac{dt}{\log(t)}$.
$$
y_i(x) = \frac{x}{\log(x)} + \frac{x}{(\log(x))^2} + \dots
$$
<u>Note</u>: Reimann worked with $\log(\zeta(s))$. 
$$
\log(\zeta(s)) = \log(\prod_p \left(1-\frac{1}{p^s}\right)^{-1}) = \sum_{k=1}^\infty \sum_p \frac{p^{-ks}}{k}
$$
He also found the derivative by a IBP such that the formula is as follows.
$$
\frac{d}{ds} \log(\zeta(s)) = \frac{\zeta'(s)}{\zeta(s)} \implies -\frac{\zeta'}{\zeta}(s) = \sum_{n=1}^\infty \frac{\Lambda(n)}{n^s}
$$

$$
\Lambda(n) = \begin{cases}
	\log p &n = p^k \;(k=1,2,\dots)\\
	0 &\text{other}
\end{cases}
$$

**Proof:** How did we derive the above $\Lambda(n)$ formula?
$$
\begin{align*}
	\log(\zeta(s)) &= \sum_{k=1}^\infty \sum_p \frac{\frac{d}{ds} p^{-ks}}{k} = 	\sum_{k=1}^\infty \sum_p \frac{\frac{d}{ds} e^{-\log(p)ks}}{k}\\
	&= \sum_{k=1}^\infty \sum_p \frac{-(\log p) k \cdot p^{-ks}}{k}
\end{align*}
$$

### Counting Prime Powers

We are interested in discovering the following sum.
$$
\sum_{n \leq x} \Lambda(n) = \sum_{p^k \leq x} \log p
$$
**Proposition:** Let $c = \frac{1}{\log(x)}$ and $T \geq x^{\frac{1}{2}} >> 1$.

$$
\frac{1}{2\pi i} \int_{c-iT}^{c+iT} \left(\frac{\zeta'}{\zeta}(s)\right) x^s \;\frac{ds}{s} = \sum_{n \leq x} \Lambda(n) + O (x^{\frac{1}{2}}\left(\log x)^2\right)
$$
**Proof:** Assume that $x - \frac{1}{2} \in \mathbb{Z}$. 
$$
\frac{1}{2\pi i} \int_{c-iT}^{c+iT} \left(\frac{\zeta'}{\zeta}(s)\right) x^s \;\frac{ds}{s} = \sum_{n=1}^\infty \Lambda(n) \cdot \frac{1}{2\pi i} \int_{c-iT}^{c+iT} \left(\frac{x}{n}\right)^s \;\frac{ds}{s}
$$
First, we need to break the sum into four distinct pieces $S_1, S_2, S_3, S_4$. 
$$
\frac{\zeta'}{\zeta}(s) = \left|\sum_{n \leq \frac{3}{4}x} + \sum_{\frac{3}{4}x \leq n < x} + \sum_{x \leq n \leq \frac{5}{4}} + \sum_{n > \frac{5}{4}}\right|
$$
**Case 1:** Now, compose the following sum with the two error terms.
$$
\begin{align*}
\left(\sum_{n \leq \frac{3}{4}x} + \sum_{n > \frac{5}{4}}\right) \cdot \Lambda(n) \cdot \frac{1}{2\pi i} \int_{c-iT}^{c+iT} \left(\frac{x}{n}\right)^s \;\frac{ds}{s} &= \sum_{n \leq \frac{3}{4}x} \Lambda(n) + O\left(\sum_{1 \leq n \leq \frac{3}{4}x} \Lambda(n) \frac{\left(\frac{x}{n}\right)^c}{T}\right) \\
&\quad+ \;O\left(\sum_{\frac{5}{4}x \leq n} \Lambda(n) \frac{\left(\frac{x}{n}\right)^c}{T}\right)\\
&= \sum_{n \leq \frac{3}{4}x} \Lambda(n) + \underbrace{O\left(\sum_{n=1}^\infty \frac{\Lambda(n) \left(\frac{x}{n}\right)^c}{T}\right)}_{\text{error term}}
\end{align*}
$$
We can estimate the error term above by the following.
$$
O\left(\sum_{n=1}^\infty \frac{\Lambda(n) \left(\frac{x}{n}\right)^c}{T}\right) = O\left(\frac{x^c}{T}\cdot \left|\frac{\zeta'}{\zeta}(c)\right|\right) = O\left(\frac{x^{1+\frac{1}{\log x}}}{T} \log(x)\right)\approx \frac{x}{T} \log x
$$
<u>Note</u>: We have the following formaul to bound the error even further.
$$
-\frac{\zeta'}{\zeta}\left(1 + \frac{1}{\log x}\right) \backsim \frac{1}{1+\left(1+\frac{1}{\log x}\right)} + O(1) << \log(x)
$$
Essentially, the contribution from $S_1$ to $S_4$ looks like the above, and you are left with some error (the easy case). Now, let's evaluate $S_2$ and $S_3$. They are symmetric so let's focus only on $S_2$. 

**Case 2:** This is symmetric to case $S_3$. 
$$
\begin{align*}
\sum_{\frac{3}{4}x \leq n < x} \Lambda(n) \cdot \frac{1}{2\pi i} \int_{c-iT}^{c+iT} \left(\frac{x}{n}\right)^s \frac{ds}{s} &= \sum_{\frac{3}{4}x \leq n < x} \Lambda(n) + O\left(\left(\frac{x}{n}\right)^c \cdot \frac{1}{T \cdot \log\left(\frac{x}{n}\right)}\right)\\
&= \sum_{\frac{3}{4}x \leq n < x} \Lambda(n) + O\left(\sum_{0 \leq v \leq \frac{x}{4}-\frac{1}{2}} \frac{\log x}{T \cdot \left|\log\left(1-\frac{v + \frac{1}{2}}{x}\right)\right|}\right)
\end{align*}
$$
<u>Note</u>: Let $n = x - \frac{1}{2} - v$ and $v \in \mathbb{Z}$ where $ - \leq v \leq \frac{x}{4} - \frac{1}{2}$.  

Now, using the expansion of the $\log$, we have the following.
$$
= \sum_{\frac{3}{4}x \leq n < x} \Lambda(n) + O\left(\frac{\log x}{T} \cdot \sum_{1 \leq v \leq \frac{x}{4} - \frac{1}{2}} \frac{x}{v + \frac{1}{2}}\right)
$$
**Theorem:** Assume the Riemann Hypothesis, which implies that $\left|\frac{\zeta'}{\zeta}(s)\right| = O(\log(1 + |s|)^2$ for $\Re(s) > \frac{1}{2} + \epsilon'$. Then, for $\epsilon = 2 \epsilon'$, we have 
$$
\sum_{1 \leq n \leq x} \Lambda(n) = x + O\left(x^{\frac{1}{2}+ \epsilon}\right)
$$
 <u>Note</u>: Take some boundary of a rectange in the complex plane $\partial R$. We can draw this rectangle up to $\frac{1}{2} + \epsilon$ to account for the zeroes. 
$$
\frac{1}{2\pi i} \int_{\partial R} -\frac{\zeta'}{\zeta}(s) x^s \;\frac{ds}{s} = x
$$
**Claim:** $2$ Horizontal Integrals + Vertical Integral $<< x^{\frac{1}{2} + \epsilon}$ 

 **Proof:** Start with the horizontal integrals.

<u>Horizontal Integrals</u>:
$$
\left|\int_{c+iT}^{\frac{1}{2}+\epsilon+iT} -\frac{\zeta'}{\zeta}(s) x^s \;\frac{ds}{s}\right| << (\log T)^2\int_{\frac{1}{2}+\epsilon}^{1+\frac{1}{\log x}} x^\sigma \; d\sigma << \frac{x}{T} (\log T)^2
$$
We define $s = \sigma + iT$  and $\frac{1}{2} + \epsilon \leq \sigma \leq 1 + \frac{1}{\log x}$. If you choose $T = x^{\frac{1}{2}}$, then we have the bound is as follows.
$$
<< x^\frac{1}{2} (\log x)^2
$$
<u>Vertical Integral</u>: 
$$
\left|\frac{1}{2\pi i} \int_{\frac{1}{2} + \epsilon - iT}^{\frac{1}{2} + \epsilon + iT} \frac{\zeta'}{\zeta}(s)x^s\;\frac{ds}{s}\right| << x^{\frac{1}{2} + \epsilon} \int_{-T}^{+T} \log(1 + |t|)^2 \;\frac{dt}{\frac{1}{2} + |t|} << x^{\frac{1}{2} + \epsilon}(\log T)^3
$$
