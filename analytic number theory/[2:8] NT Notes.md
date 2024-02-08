# [2/8] NT Notes

### Theorem (Riemann)

The function $\zeta(s) = \sum_{n=1}^\infty \frac{1}{n^s}$ has meromorphic continuity to all of $\mathbb{C}$ with a simple pole at $s = 1$ with $\Res = 1$ and satisfies the functional equation
$$
\pi^{-\frac{s}{2}} \Gamma\left(\frac{s}{2}\right) \zeta(s) = \pi^{-\frac{1-s}{2}} \Gamma\left(\frac{1-s}{2}\right) \zeta(1-s)
$$
 **Last Time:** We proved that the functional equation of $\theta(y)$ is the following.
$$
\theta(y) = \sum_{n=-\infty}^\infty e^{-\pi n^2 y}
$$

$$
\sum_{n=-\infty}^\infty e^{-\pi n^2 y} = \sqrt{y} \sum_{n=1}^\infty e^{-\pi n^2 y} + \frac{\sqrt{y}}{2} - \frac{1}{2}
$$

We've also proven the following.
$$
\sum_{n=1}^\infty \int_0^\infty e^{-\pi n^2 y} y^s \frac{dy}{y} = \pi^{-s} \cdot \zeta(2s) \cdot \Gamma(s)
$$

---

**Goal:** Next, we evaluate the LHS for the equation above in a different way.

To do so, let's transform the LHS.
$$
\sum_{n=1}^\infty \int_0^\infty e^{-\pi n^2 y} y^s \frac{dy}{y} = \underbrace{\sum_{n=1}^\infty \int_1^\infty e^{-\pi n^2 y} \;y^s \;\frac{dy}{y}}_{I_1}  + \underbrace{\sum_{n=1}^\infty \int_0^1 e^{-\pi n^2 y} \;y^s \;\frac{dy}{y}}_{I_2}
$$
Let's first evaluate $I_1$. 
$$
I_1 \ll \sum_{n=1}^\infty e^{-\pi n^2 y}\;y^\sigma \;\frac{dy}{y}
$$
Since $F \in \mathcal{S}$, it is a Schwartz function. The rest will be left to a HW problem.
$$
\implies \sum_{n=1}^\infty \int_1^\infty F(ny) \;y^s\;\frac{dy}{y} = \text{holomorphic everywhere}
$$
Let's also define the term inside the sum $I_1$ as $H(s)$. 
$$
\sum_{n=1}^\infty \int_0^1 \underbrace{e^{-\pi n^2 y}\;y^s\;\frac{dy}{y}}_{y\rightarrow \frac{1}{y}} = \sum_{n=1}^\infty \int_1^\infty e^{-\frac{\pi n^2}{y}} y^{-s}\;\frac{dy}{y}
$$
Now, we use the functional equation specificied in Part (1). We now that
$$
\begin{align*}
&= \int_1^\infty \sqrt{y} \sum_{n=1}^\infty e^{-\pi n^2 y} \;y^{-s}\;\frac{dy}{y} + \overbrace{\int_1^\infty \left(\frac{\sqrt{y}}{2} - \frac{1}{2}\right)\;y^{-s}\;\frac{dy}{y}}^{\text{These have poles}}\\
&= \int_1^\infty \sum_{n=1}^\infty e^{-\pi n^2 y} \;y^{\frac{1}{2}-s}\; \frac{dy}{y} + \frac{1}{2} \cdot \left(\frac{1}{s-\frac{1}{2}}\right) - \frac{1}{2s}
\end{align*}
$$
The conclusion of these calculations is the following.
$$
\pi^{-s} \;\Gamma(s) \;\zeta(2s) = \underbrace{H(s) + H\left(\frac{1}{2}-s\right) + \frac{1}{2}\left(\frac{1}{s-\frac{1}{2}} - \frac{1}{s}\right)}_{\text{Invariant under } s\rightarrow \frac{1}{2}-s}
$$

### Tate's Generalization

We want to study the transformation.
$$
\int_0^\infty * \;y^s \;\frac{dy}{y}
$$
**Definition:** Let $f: \mathbb{R} \rightarrow \mathbb{C}$ be a smooth function. Then, we define the Mellin transform of $f$ (denoted $\tilde{f}(s)$) by the following integral:
$$
\int_{0}^{^\infty} f(y) \;y^{s} \frac{dy}{y}
$$
This is assuming the integral converges.

<u>Example</u>: Consider $\psi(x) = e^{-\pi x}$ . The Mellin transform $\tilde{\psi}(s) = \Gamma(s)$. 

**Proposition:** (Inverse Mellin Transform) Let $\tilde{f}(s) = \int_0^\infty f(y)\;y^s\;\frac{dy}{y}$ be the Mellin transform of $f$. This means that
$$
f(y) = \frac{1}{2\pi i} \int_{\sigma - i\infty}^{\sigma + i\infty} \tilde{f}(w)y^{-w}\;dw = \frac{1}{2\pi i} \int_{\sigma - i\infty}^{\sigma + i\infty} \tilde{f}''(w) \frac{y^{2-w}}{(1-w)(2-w)} \quad \quad \sigma > \sigma_0
$$
**Proof (1):** This method does not work.
$$
\begin{align*}
f(y) &= \frac{1}{2\pi i} \int_{\sigma - i\infty}^{\sigma + i \infty} \left(\int_0^\infty f(x) \;x^w \;\frac{dx}{x} \right)  y^{-w}\;dw\\
&= \frac{1}{2\pi i}\int_0^\infty f(x)\cdot \int_{\sigma - i\infty}^{\sigma + i\infty} \left(\frac{x}{y}\right)^w  \;dw
\end{align*}
$$
**Proof (2):** This method does work.
$$
\begin{align*}
\tilde{f}(s) &= \int_0^\infty f''(x) \frac{x^{s+1}}{s(s+1)}\;dx\\
&= \frac{1}{2\pi i}\int_{\sigma - i\infty}^{\sigma + i\infty} \tilde{f}(w) \;x^{-w}\;dw \\
&= \frac{1}{2\pi i} \int_{\sigma - i\infty}^{\sigma + i\infty} \int_0^\infty f''(x) \frac{x^{w+1}}{w(w+1)}\;dx\;y^{-w}\;dw\\
&= \int_0^\infty f''(x) \cdot x \cdot \frac{1}{2\pi i} \int_{\sigma - i\infty}^{\sigma + i\infty} \left(\frac{x}{y}\right)^w\; \frac{dw}{w(w+1)} \;dx
\end{align*}
$$
Now, let's evaluate only the inner integral.
$$
\frac{1}{2\pi i} \int_{\sigma - i\infty}^{\sigma + i\infty} \left(\frac{x}{y}\right)^w\; \frac{dw}{w(w+1)} = 1 - \frac{y}{x}
$$
This is because $\Res_{w=-1} \frac{\left(\frac{x}{y}\right)^w}{w(w+1)} = \frac{\left(\frac{x}{y}\right)^{-1}}{-1}$. For $x \geq y$, we have the following integral (once we plug in our result).
$$
\begin{align*}
	&= \int_y^\infty f''(x) \cdot x \cdot \left(1-\frac{y}{x}\right)\;dx\\
	&= - \int_y^\infty f''(x)\left(x-y\right)\;dx \\
	&= \int_y^\infty f'(x) \cdot 1\;dx = f(y)
\end{align*}
$$

---

**Goal:** We want to show that the Fourier transform and the Mellin transform are the same.
$$
\hat{f}(y) = \int_{-\infty}^\infty f(t)\;e^{-2\pi i ty}\;dt
$$

$$
f(y) = \frac{1}{2\pi i }\int_{\sigma - i\infty}^{\sigma + i\infty} \tilde{f}(w) \;y^{-w}\;dw
$$

If we let $y = e^{2\pi y'}$, then we have.
$$
\frac{1}{2\pi i }\int_{\sigma - i\infty}^{\sigma + i\infty} \tilde{f}(w) \;y^{-w}\;dw = \frac{1}{2\pi i} \int_{-i\infty}^\infty \tilde{f}(u) e^{-2\pi i u y'} \; du
$$
Now, define some function as follows $F(y) = f(e^{2\pi y})$ and examine its Mellin transform.
$$
\tilde{F}(s) = \int_0^\infty F(t) \;t^s \frac{dt}{t} = \int_{-\infty}^\infty F(e^{2\pi y}) \cdot e^{2\pi y s} \;dy
$$
The rest of the proof will be posted.





