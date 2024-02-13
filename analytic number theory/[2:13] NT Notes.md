# [2/13] NT Notes

### Review

#### Mellin Transform

**Definition:** For $f \in \mathcal{S},\;s \in \mathbb{C}$, where $\tilde{f}(s)$ is holomorphic for $\Re(s) \geq 0$. 
$$
\tilde{f}(s) := \int_0^\infty f(y)y^s\;\frac{dy}{y} 
$$

$$
f(y) = \frac{1}{2\pi i} \int_{\sigma_0 - i\infty}^{\sigma_0 + i\infty} \tilde{f}(s) y^{-s}\;ds
$$

#### Fourier Transform

**Definition:** For $y \in \mathbb{R}$,
$$
\hat{f}(y) = \int_{-\infty}^\infty f(t)e^{-2\pi i t y }\;dt
$$

$$
f(y) = \int_{-\infty}^\infty \hat{f}(t) e^{2\pi i t y}\;dt
$$

---

### New

#### Relating Mellin $\rightarrow$ Fourier

**Idea:** We now show that the Mellin transform (I) $\implies$ Fourier (II). Let $F(y) := f(e^y)$.

**Claim:** $\hat{F}(x) \cong \tilde{f}(x)$

**Proof:** Also included in the notes, but we will review in class.
$$
\begin{align*}
\hat{F}(y) &= \int_{-\infty}^\infty \underbrace{f(e^t) e^{-2\pi i t y}}_{u = e^t}\;dt\\
&= \int_0^\infty f(u)\;u^{-2\pi i y}\;\frac{du}{u}\\
&= \tilde{f}(-2\pi i y)
\end{align*}
$$
The above is the first step to proving the secondary formula in (II). The second step is the prove the inverse Fourier Transform formula. 
$$
f(x) = \frac{1}{2\pi i }\int_{-i\infty}^{i\infty} \tilde{f}(s)x^s\;ds
$$
We choose some $x = e^y$ such that
$$
\begin{align*}
F(y) &= \frac{1}{2\pi i} \int_{-i\infty}^{i\infty} \underbrace{\tilde{f}(s) e^{sy}}_{s = -2\pi  i t}\;ds\\
&= \frac{1}{2\pi i} \int_{\infty}^{-\infty} \tilde{f}(-2\pi i t)e^{2\pi i ty}\cdot (-2\pi i)\;dt\\
&= \int_{-\infty}^\infty \hat{F}(t) e^{2\pi i t y}\;dt
\end{align*}
$$

----

#### Tate's Proof of Zeta Functional Equation

**Poisson Summation:** Let $f \in \mathcal{S} \implies \sum_{n=\infty}^\infty f(ny) = \frac{1}{y} = \sum_{n=-\infty}^\infty \hat{f}\left(\frac{n}{y}\right)$

Now, assume $f(x) = f(-x)$ for all $x \in \mathbb{R}$. This implies
$$
\begin{align*}
	\implies &2\sum_{n=1}^\infty f(ny) + f(0) = 2 cdot \frac{1}{y} \sum_{n=1}^\infty \hat{f}\left(\frac{n}{y}\right) + \frac{\hat{f}(0)}{y}\\
	&\sum_{n=1}^\infty f(ny) = \frac{1}{y} \sum_{n=1}^\infty \hat{f}\left(\frac{n}{y}\right) + \frac{\hat{f}(0)}{2y} - \frac{f(0)}{2}
\end{align*}
$$
<u>Riemann</u>: Reimann chose $f(x) = e^{-\pi x^2} = \hat{f}(x)$. 

<u>Tate</u>: Tate left $f$ unchosen, and the proof still works! 

**Theorem (Tate):** Let $f \in \mathcal{S}$ and $f(x) = f(-x)$ for all $x \in \mathbb{R}$. Then,
$$
\hat{f}(s) \zeta(s) = \tilde{\hat{f}} (1-s)\zeta(1-s)
$$
**Proof:** First, take the Mellin transform of the following sum.
$$
\int_0^\infty \sum_{n=1}^\infty \underbrace{f(ny) y^s}_{y \mapsto \frac{y}{n}} \;\frac{dy}{y} = \zeta(s) \cdot \tilde{f}(s) = \overbrace{\int_{1}^\infty \sum_{n=1}^\infty f(ny) \;y^s \frac{dy}{y}}^{I_1(s)} + \overbrace{\int_0^1 \sum_{n=1}^\infty \underbrace{f(ny)\;y^s}_{y\mapsto \frac{1}{y}}\;\frac{dy}{y}}^{I_2(s)}
$$
Consider only $I_2(s)$.
$$
I_2(s) = \int_{\infty}^1 \sum_{n=1}^\infty f\left(\frac{n}{y}\right) y^{-s}\;\frac{dy}{y}
$$
From earlier, we also have the following.
$$
\sum_{n=1}^\infty f\left(\frac{n}{y}\right) = y \sum_{n=1}^\infty \hat{f}(ny) + \frac{y\hat{f}(0)}{2} - \frac{f(0)}{2}
$$
This means that we have the following expression.
$$
I_2(s) = \int_1^\infty \sum_{1}^\infty \hat{f}(ny) \;y^{1-s}\;\frac{dy}{y} + \frac{\hat{f}(0)}{2} \int_1^\infty y^{1-s}\;\frac{dy}{y} - \frac{f(0)}{2} \int_1^\infty y^{-s}\;\frac{dy}{y}
$$
Because the expression is a combination of three integrals, we can split it up into solvable integrals.
$$
\int_1^\infty y^{1-s} \; \frac{dy}{y} = \frac{1}{s-1}
$$
The second term gets replaced such that
$$
I_2(s) = \int_1^\infty \sum_{1}^\infty \hat{f}(ny) \;y^{1-s}\;\frac{dy}{y} + \frac{\hat{f}(0)}{2}\cdot \frac{1}{s-1} - \frac{f(0)}{2} \int_1^\infty y^{-s}\;\frac{dy}{y}
$$
Similarly, take the third term.
$$
\int_1^\infty y^{-s} \; \frac{dy}{y} = \frac{1}{s}
$$
Now, we have the expression for $I_2$ is as follows.
$$
\begin{align*}
I_2(s) = \int_1^\infty \sum_{1}^\infty \hat{f}(ny) \;y^{1-s}\;\frac{dy}{y} + \frac{\hat{f}(0)}{2}\cdot \frac{1}{s-1} - \frac{f(0)}{2} \cdot \frac{1}{s}
\end{align*}
$$
This means that we can continue the proof of the functional equation.
$$
\begin{align*}
\zeta(s)\cdot \tilde{f}(s) &= I_1(s) + I_2(s)\\
&= \int_1^\infty \sum_{n=1}^\infty f(ny)\;y^s\;\frac{dy}{y} + \int_1^\infty \sum_{1}^\infty \hat{f}(ny) \;y^{1-s}\;\frac{dy}{y} + \frac{\hat{f}(0)}{2(s-1)} - \frac{f(0)}{2s}\\
&= \int_1^\infty \left[\sum_{n=1}^\infty f(ny)\;y^s + \sum_{1}^\infty \hat{f}(ny) \;y^{1-s}\right] \;\frac{dy}{y} + \frac{\hat{f}(0)}{2(s-1)} - \frac{f(0)}{2s}
\end{align*}
$$
If we let $s \mapsto 1-s$ and $f \rightarrow \hat{f}$, I claim that the above expression is invariant. This completes the proof.

#### Riemann's Extension

$$
f(s) = \pi^{-\frac{s}{2}} \Gamma\left(\frac{s}{2}\right) \zeta(s) = f(1-s)
$$

I claim that $f(s)$ has simple poles at $s = 0,1$ and no other poles.
$$
\underbrace{\Res_{s=1} \;f(s)}_{\Res_{s=0}\;f(s)} = \Res_{s=1}\; \pi^{-\frac{s}{2}} \;\Gamma\left(\frac{s}{2}\right) \;\zeta(s) = \pi^{-\frac{1}{2}}\;\Gamma\left(\frac{1}{2}\right) = 1
$$

$$
\Res_{s=0} \; f(s) = 1 = \Res_{s=0} \;\Gamma\left(\frac{s}{2}\right) \cdot \zeta(0) = 2 \cdot \underbrace{\frac{1}{2}}_{\zeta(0)} = 1
$$

We have that $\zeta(s)$ decays faster than $\Gamma\left(\frac{s}{2}\right)$ blows up. The trivial zeroes of $\zeta(s)$ are at
$$
s = -2,\;-4,\; -6,\;\dots
$$
We also now that all zeroes of the $\zeta$ function must be in the <u>critical strip</u> and lie on the line $s=\frac{1}{2}$. 

### A. Weil Explicit Formula

**Details:** Relates primes and zeroes of $\zeta(s)$.

**Proof (Outline):** Let $f \in \mathcal{S}$ where $\tilde{f}(s) = \tilde{f}(-s)$. 
$$
z(s) = \pi^{-\frac{s}{2}} \;\Gamma\left(\frac{s}{2}\right)\; \zeta(s) = z(1-s)
$$
This means that $\frac{z'}{z}(s) = \frac{d}{ds} \left(\log z(s)\right) = \frac{d}{ds}\left[-\frac{s}{2} \log \pi + \log \Gamma\left(\frac{s}{2}\right) + \log \zeta(s)\right]$.
$$
= -\frac{\log \pi}{2} + \frac{1}{2} \cdot \frac{\Gamma'}{\Gamma} \left(\frac{s}{2}\right) + \frac{\zeta'}{\zeta}(s)
$$

$$
\frac{z'}{z}(s) = -\frac{z'}{z}(1-s)
$$

Thus, we have the setup for the following formula.
$$
\frac{1}{2\pi i } \int_{2-i\infty}^{2+i\infty} \frac{z'}{z}\left(\frac{1}{2} + s\right) \tilde{f}(s) \;ds
$$

$$
= \frac{1}{2\pi i } \int_{2-i\infty}^{2+i\infty} \left[\frac{-\log \pi}{2} + \frac{1}{2} \cdot \frac{\Gamma'}{\Gamma}\left(\frac{\frac{1}{2} + s}{2}\right) + \frac{\zeta'}{\zeta}\left(\frac{1}{2} + s\right)\right] \tilde{f}(s)\;ds
$$

$$
\frac{1}{2\pi i } \int_{2-i\infty}^{2+i\infty} -\frac{\log \pi}{2} \tilde{f}(s)\;ds + \frac{1}{4\pi i} \int_{2-i\infty}^{2+i\infty} \frac{\Gamma'}{\Gamma}\left(\frac{\frac{1}{2} + s}{2}\right) \tilde{f}(s)\;ds + \frac{1}{2\pi i } \int_{2-i\infty}^{2+i\infty} -\sum_{n=1}^\infty \frac{\Lambda(n)}{n^{\frac{1}{2} + s}} \tilde{f}(s)\;ds
$$

$$
= -\frac{\log\pi}{2} f(1) + \frac{1}{4\pi i} \int_{2-i\infty}^{2+i\infty} \frac{\Gamma'}{\Gamma}\left(\frac{\frac{1}{2} + s}{2}\right) \tilde{f}(s)\;ds - \underbrace{\sum_{n=1}^\infty \frac{\Lambda(n)}{n^{\frac{1}{2}}} \cdot f(n)}_{\sum_p \sum_{k=1}^\infty \frac{\log p}{p^{k/2}} \cdot f(p^k)}
$$

The explicit formula will be completed next time.