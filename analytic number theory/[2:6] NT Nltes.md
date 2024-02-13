# [2/6] Number Theory

### Review

#### Fourier Transform

**Definition:** Fourier transform is defined as follows.
$$
\hat{f}(y) = \int_{-\infty}^\infty f(t) e^{-2\pi i ty}\;dt
$$

----

### Lecture

**Definition (Schwartz Space):** The Schwartz Space is the set of all smooth functions $f: \mathbb{R} \rightarrow \mathbb{C}$ satisfying 
$$
\left|x^n \left(\left(\frac{d}{dx}\right)^m f(x)\right)\right| = \mathcal{O}_{m,n}(1)
$$
This means that the LHS will be bounded for all $x \in \mathbb{R}$ where $m,n \in \mathbb{Z}^+$. 

**Example:** One of the simplest examples of a Schwartz function is $e^{-x^2}$ (Gaussian). 

**Proposition:** Let $\phi(x) := e^{-\pi x^2}$. Then, $\hat{\phi}(x) = \phi(x)$. 

<u>Question</u>: Let $\phi_0(x) = e^{-x^2}$. What is the fourier transform of $\phi_0$? 
$$
\begin{align*}
\phi_0(x) &= \int_{0}^\infty \underbrace{e^{-t^2} e^{-2\pi i t x}}_{t\rightarrow\sqrt{\pi}t}\;dt\\
&= \int_0^\infty e^{-\pi t^2} e^{-2\pi i t x \sqrt{\pi}} \sqrt{\pi}\;dt\\
&= \pi \hat{\phi}(x \sqrt{\pi}) \\
&= \sqrt{\pi} e^{-\pi^2x^2}
\end{align*}
$$
 **Proof (Proposition):** $\phi(x) = \int_{-\infty}^\infty e^{-\pi t^2}e^{-2\pi i t x}\;dt$ 

We want to prove that $\hat\phi(x)$ satisfies the same differential equation as $\phi(x)$. 
$$
\begin{align*}
	\frac{d}{dx}\phi (x) = \frac{d}{dx} e^{-\pi x^2} = -2\pi x e^{-\pi x^2} \implies \frac{d}{dx} \phi(x) = -2\pi x \cdot \phi(x)
\end{align*}
$$
I claim that $\frac{d}{dx} \hat{\phi(x)} = -2\pi x \cdot \phi(x)$. 
$$
\begin{align*}
	\frac{d}{dx} \hat{\phi}(x) &= \int_{-\infty}^\infty e^{-\pi t^2}(-2\pi i t) e^{-2\pi i t x}\;dt \\
	&= \int_{-\infty}^\infty \left((-2\pi t) e^{-\pi t^2}\right) e^{-2\pi i t x}\;dt \\
	&= -i\int_{-\infty}^\infty e^{-\pi t^2} (-2\pi i x)(e^{-2\pi i t x})\;dt \\
	&= -2\pi x\cdot \hat{\phi}(x)
\end{align*}
$$
By law from ODEs, we know that the solution to this first order is unique and has solution $ce^{-\pi x^2}$. Now, it's left to prove that $c = \hat{\phi}(0) = 1$, and we are complete.
$$
\hat{\phi}(0) = \int_{-\infty}^{\infty} e^{-\pi t^2} \;dt = \frac{1}{\sqrt{\pi}} \int{-\infty}^\infty e^{-t^2}\;dt
$$
 We need to show that $\int_{-\infty}^\infty e^{-t^2}\;dt = \sqrt{\pi}$. If we square the term, we get
$$
\begin{align*}
	\left(\int_{-\infty}^\infty e^{-t^2}\;dt\right)^2 &= \int_{-\infty}^\infty \int_{-\infty}^\infty e^{u^2 + t^2}\;du\;dt\\
\end{align*}
$$
Now, change to polar coordinates such that $u = r\cos\theta$ and $t = r\sin \theta$ and $du \;dt = r\;dr\;d\theta$. 
$$
\begin{align*}
\int_{-\infty}^\infty \int_{-\infty}^\infty e^{u^2 + t^2}\;du\;dt &= \int_{\theta = 0}^{2\pi} \int_{r = 0}^\infty e^{-r^2} r \;dr\;d\theta\\
&= 2\pi \eval{\frac{e^{-r^2}}{2}}_{0}^\infty  = \pi
\end{align*}
$$
**Proposition (Schwartz):** Let $f \in \mathcal{S}$. Then, the integral defining $\hat{f}$ converges absolutely and $\hat{f} \in \mathcal{S}$. 

**Proof:** We start as follows.
$$
\hat{f}(x) = \int_{-\infty}^\infty f(t)e^{-2\pi i t x}\;dt
$$
The proof uses a standard trick from analysis (integration by parts many times).
$$
\begin{align*}
x^m \cdot \frac{d^n}{dx^n} \hat{f}(x) &= x^m \int_{-\infty}^\infty f(t)(-2\pi i t)^n e^{-2\pi i t x}\;dt\\
&= x^m \int_{-\infty}^\infty \frac{d^l}{dt^l} f(t) \cdot (-2\pi i t)^n \cdot \frac{e^{-2\pi i t x}}{(-2\pi i x)^l}\;dt
\end{align*}
$$
This implies that $|x^m| \cdot \left|\frac{d^n}{dx^n} \hat{f}(x)\right| = \mathcal{O}_{m,n}(1)$.

---

**Theorem (Poisson Summation Formula):** Let $f \in \mathcal{S}$, which means $f$ is in the Schwartz Space. Then,
$$
\sum_{n=-\infty}^\infty f(n) = \sum_{n=-\infty}^\infty \hat{f}(n)
$$
**Proof:** Define a new function $G(x) = \sum_{k=-\infty}^\infty f(x+k)$. This converges since it is in the Schwartz space. Note that $G(x+1) = G(x)$ for all $x \in \mathbb{R}$. 

We also know that $G$ is smooth since $f \in \mathcal{S}$. This implies that $G$ has a Fourier expansion.
$$
G(x) = \sum_{\ell=-\infty}^{\infty} \hat{G}_\ell e^{2\pi i \ell x} \quad \text{ where } \quad \hat{G}_\ell = \int_0^1 G(t) e^{-2\pi i t \ell}\;dt
$$
This means that we can show the following.
$$
\begin{align*}
\hat{G}_n &= \int_0^1 \sum_{k=-\infty}^\infty \underbrace{f(t+k) e^{-2\pi i \ell t}}_{t' = t + k}\;dt\\
&= \sum_{k=-\infty}^\infty \int_k^{k+1} f(t') \underbrace{e^{-2\pi i \ell (t' - k)}}_{e^{2\pi i l k} = 1}\;dt'\\
&= \sum_{k=-\infty}^\infty \int_{k}^{k+1} f(t)e^{-2\pi i \ell t}\;dt\\
&= \int_{-\infty}^\infty f(t)e^{-2\pi i \ell t}\;dt \\
&= \hat{f}(\ell)
\end{align*}
$$
Essentially, we have shown.
$$
\sum_{k=-\infty}^\infty f(x+k) = G(x) = \sum_{\ell = -\infty}^\infty \hat{f}(l) e^{2\pi i \ell x}
$$
 Let $x = 0$, and we have completed the proof.

**Laplace Operator:** $T = \frac{d^2}{dx^2}$,  $T e^{2\pi i n x} = -4\pi^2 n^2 e^{2\pi i n x}$. We basically learn that $Tf = \underbrace{\lambda}_{\text{eigenv}} \overbrace{f}^{\text{eigenf}}$

**Corollary:** Let $y > 0$.
$$
\sum_{n=-\infty}^\infty f(ny) = \frac{1}{y} \sum_{n=-\infty}^\infty \hat{f}\left(\frac{n}{y}\right)
$$
If we define some $F_y(x) = f(xy)$, then we can use the above to show the following.
$$
\sum_{n=-\infty}^\infty F_y(n) = \sum_{n=-\infty}^\infty \hat{F}_y(n)
$$
**Proof:** First, we compute $\hat{F}_y(n)$. 
$$
\hat{F}_y(n) = \int_{-\infty}^\infty F_y(t) e^{-2\pi i n t} \;dt = \int_{-\infty}^\infty f(yt) e^{-2\pi i n t}\;dt
$$
Doing a simple change of variables $t \rightarrow \frac{t}{y}$, we can complete the proof.

---

**Definition (Theta Function):** Below is the definition of Reimann's theta function.
$$
\theta(y) = \sum_{n=-\infty}^\infty e^{-\pi n^2 y}
$$
**Theorem:** For $y > 0$, we have the functional equation.
$$
\theta(y) = \frac{1}{\sqrt{y}} \theta\left(\frac{1}{y}\right)
$$
Let $f(y) = e^{-\pi y^2}$ and $\hat{f}(y) = f(y)$. Let's use the above proof and $f(y)$ to show the desired formula.
$$
\sum_{n=-\infty}^\infty e^{-\pi n^2y^2} = \frac{1}{y} \sum e^{-\pi \frac{n^2}{y^2}} \implies \underbrace{\sum_{n=-\infty}^\infty e^{-\pi n^2y}}_{\theta(y)} = \frac{1}{\sqrt{y}} \underbrace{\sum e^{-\pi \frac{n^2}{y}}}_{\theta\left(\frac{1}{y}\right)}
$$
We also have the following functional equation.
$$
2\sum_{n=1}^\infty e^{-\pi n^2y} + 1 = \frac{2}{\sqrt{y}} \sum_{n=1}^\infty e^{-\pi n^2 \cdot \frac{1}{y}}
$$

$$
\sum_{n=1}^\infty e^{-\pi n^2y} = \frac{1}{\sqrt{y}} \sum_{n=1}^\infty e^{\frac{-\pi n^2}{y}} + \frac{1}{2\sqrt{y}} - \frac{1}{2}
$$

To get $\zeta(s)$, Riemann integrates the above with respect to $y$ and introduces $s \in \mathbb{C}$ with $\Re(s) > 1$. The left hand side is as follows. Employing a change of variables, we have
$$
\begin{align*}
\int_0^\infty \sum_{n=1}^\infty \underbrace{e^{-\pi n^2y} \cdot y^s}_{y \mapsto \frac{y}{\pi n^2}} \;\frac{dy}{y} &= \sum_{n=1}^\infty \frac{1}{(\pi n^2)^s} \int_0^\infty e^{-y}y^s\;\frac{dy}{y}\\
&= \pi^{-s} \zeta(2s) \cdot \Gamma(s)
\end{align*}
$$
The RHS will be done next class!