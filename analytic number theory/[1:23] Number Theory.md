# [1/23] Number Theory

### Updates

- [HW 1] is posted in Courseworks (2/6 Due Date 11:59 PM)

### Gamma Function (Euler)

**Definition (Last Time):** The Gamma Function
$$
\Gamma(z) = \int_0^\infty e^{-u}u^z \;\frac{du}{u} \quad \quad \Gamma(z+1) = z \cdot \Gamma(z)
$$

* The only requirement for convergence is that $\Re(z) > 0$ 

### Euler's Definition of $\Gamma$ 

**Definition:** Euler's original definition.
$$
\begin{align*}
\Gamma^*(z) &= \lim_{n\rightarrow\infty} \frac{1 \cdot 2 \cdot 3 \cdots n}{z \cdot (z+1) \cdot (z+2) \cdots (z+n)} \cdot n^z\\
&= \lim_{n\rightarrow\infty} \frac{n^z}{z} \left(\frac{1}{1+z}\right) \cdot \left(\frac{1}{1+\frac{z}{2}}\right)\cdot \left(\frac{1}{1+\frac{z}{3}}\right) \cdots \left(\frac{1}{1+\frac{z}{n}}\right)
\end{align*}
$$
**Claim:** $\Gamma^*(z+1) = z \cdot \Gamma^*(z)$ 

**Proof:** 
$$
\begin{align*}
	\Gamma^*(z+1) &= \lim_{n\rightarrow\infty} \frac{1 \cdot 2 \cdot 3 \cdots n}{(z+1) \cdot (z+2) \cdots (z+n+1)} \cdot n^{z+1}\\
	&= \lim_{n\rightarrow\infty} \frac{z \cdot 1 \cdot 2 \cdot 3 \cdots n \cdot (n+1)}{z \cdot (z+1) \cdot (z+2) \cdots (z+n+1)} \cdot n^z \\
	&= z \cdot \Gamma^*(z)
\end{align*}
$$
**Theorem:** $\Gamma^*(z) = \Gamma(z)$ 

**Proof:** Define $F(z,n) = \int_0^n \left(1-\frac{u}{n}\right)^n u^z \;\frac{du}{u}$ and assume that $z \in \mathbb{C}$, $\Re(z) > 0$, and $n \rightarrow \infty$. First, we have to show that
$$
\lim_{n\rightarrow\infty} \left(1 - \frac{u}{n}\right)^n = \lim_{n\rightarrow\infty} e^{\log\left(1-\frac{u}{n}\right) \cdot n} = \lim_{n\rightarrow\infty} e^{\left(\frac{-u}{n}-\frac{u^2}{2n^2}-\frac{u^3}{3n^3} \cdots\right) \cdot n} = \lim_{n\rightarrow\infty} e^{-u} = e^{-u}
$$
This result suggest that $\Gamma(z) = F(z,\infty)$. 

Next, we need to relate this function to $\Gamma^*(z)$. Start with the original function.
$$
F(z,n) = \int_0^n \left(1-\frac{u}{n}\right)^n u^z \;\frac{du}{u} \implies {\frac{u}{n}=v} \implies F(z,n) = n^z \int_0^1 (1-v)^n \cdot  v^z \frac{dv}{v}
$$
Now, use integration by parts to conver to the $\Gamma$ expression.
$$
\begin{align*}
&= \eval{\left(n^z \cdot (1-v)^n \frac{v^z}{z}\right)}_0^1 + n^z \frac{n}{z} \int_0^1 (1-v)^{n-1} v^{z}\;dv
\end{align*}
$$
We know that the left of the sum goes to zero, so we simply have the right part of the sum. If we integrate by parts $n-1$ more times, we get the following result.
$$
F(z,n) = n^z \cdot \frac{n (n-1) (n-2)\cdots(2)(1)}{z(z+1)(z+2)\cdots(z+n-1)} \cdot \int_0^1 v^{z+n-1}\;dv
$$
The integral part of the above product is equal to $\int_0^1 v^{z+n-1}\;dv = \frac{1}{z+n}$. Thus, we can conclude that
$$
F(z,n) = \Gamma^*(z) = \Gamma(z)
$$
**Theorem (Euler):** $G(z) = \Gamma(z)\Gamma(1-z) = \frac{\pi}{\sin(\pi \cdot z)}$ 

- $\Gamma(z) \neq 0$
- $\sin(\pi \cdot z)$ = $\sin(\pi(z+2)) \implies \Gamma(z+2)\Gamma(-1-z) = \Gamma(z)\Gamma(-1-z)$  
- $\Gamma(z+1) = z\Gamma(z)$
- $\Gamma(z-1) = \frac{\Gamma(z) }{z-1}$ 

Start with the above equations, to deduce the following.
$$
\begin{align*}
G(z+2) = (z+1)(z)\cdot\Gamma(z) \cdot \frac{\Gamma(-z)}{-z-1}  = z \cdot \Gamma(z) \frac{\Gamma(1-z)}{-z}
\end{align*}
$$
**Theorem (Euler):**
$$
\sin(\pi \cdot z) = \pi z \cdot \prod_{n=1}^\infty \left(1 - \frac{z^2}{n^2}\right)
$$
**Corrollary:** $\Gamma(z) \Gamma(1-z) = \frac{\pi}{\sin(\pi z)}$ 

**Proof:** We want to prove $\sin(\pi z)= \frac{\pi}{z\Gamma(z)\Gamma(-z)}$
$$
\begin{align*}
\frac{\pi}{z\Gamma(z)\Gamma(-z)} &= \frac{\pi}{-z \cdot \left(\frac{1 \cdot 2 \cdots n}{z \cdot (z+1) \cdots (z+n)}\right) \cdot \left(\frac{1 \cdot 2 \cdots n}{-z \cdot (-z+1) \cdots (-z+n)}\right)}\\
&= \pi z \left(1-z^2\right) \left(1-\frac{z^2}{2^2}\right) \left(1-\frac{z^2}{3^2}\right) \cdots \left(1-\frac{z^2}{n^2}\right)
\end{align*}
$$
This allows us to show that $\Gamma\left(\frac{1}{2}\right) = \sqrt{\pi}$. 

**Proof of the Product Formula ($\sin(\pi z)$​):** First, I claim the following proposition.
$$
\frac{\pi^2}{\sin^2(\pi z)} = \sum_{n \in \mathbb{Z}} \frac{1}{(z-n)^2}
$$
Let $f(z) := \frac{\pi^2}{\sin^2(\pi z)} - \sum_{n=-\infty}^\infty \frac{1}{(z-n)^2}$. We know that the function $f$ converges absolutely for all $z \notin \mathbb{Z}$. 
$$
f(z) := \frac{\pi^2}{\sin^2(\pi z)} - \sum_{n=-\infty}^\infty \frac{1}{(z-n)^2} = \frac{\pi^2}{\sin^2(\pi z)} - \frac{1}{z^2} + \sum_{n=1}^\infty \left(\frac{1}{z-n} + \frac{1}{z+n}\right)
$$
The above function is holomorphic (has no poles). Now, use the Taylor series expansion.
$$
\begin{align*}
\frac{\pi^2}{\sin^2(\pi z)} &= \frac{\pi^2}{\left(\pi z - \frac{(\pi z)^3}{3!} + \cdots\right)^2}
\end{align*}
$$
For $z\rightarrow 0$, we know that $\frac{\pi^2}{\sin^2(\pi z)} \rightarrow \frac{1}{z^2}$, which is how we can prove holomorphism. It is also bounded, since $\sin$ is periodic and we know that it never blows up. 

**Corrollary:**  This is a bounded holomorphic function, and using Liouiville's Theorem, we know that the difference between functions is $0$. Thus, we have that
$$
\frac{\pi^2}{\sin(\pi z)} = \frac{1}{z^2} + \sum_{n=1}^\infty \left(\frac{1}{z-n} + \frac{1}{z+n}\right)
$$
Now, we have the following.
$$
\frac{\pi^2}{\sin^2(\pi z)} = \frac{d}{dz} \left(-\pi \cot(\pi z)\right) = \frac{1}{z^2} + \sum_{n=1}^\infty \left(\frac{1}{z-n} + \frac{1}{z+n}\right)
$$
If you integrate both sides, we have the desired result.
$$
-\pi \cot(\pi z) = \frac{1}{z} + \sum_{n=1}^\infty \left(\frac{1}{z-n} + \frac{1}{z+n}\right)
$$
However, we want to prove the original theorem.
$$
\begin{align*}
\frac{d}{dz} \log(\sin(\pi z)) &= \pi \cot(\pi z)\\
&= C + \log(z) + \sum_{n=1}^\infty \log\left(1-\frac{z^2}{n^2}\right)\\
\sin(\pi z) &= e^C \cdot z \cdot \prod_{n=1}^\infty \left(1-\frac{z^2}{n^2}\right)
\end{align*}
$$
**Theorem (Euler):** We want to show that
$$
\zeta(2) = \frac{\pi^2}{6}
$$
**Proof:** 
$$
\begin{align*}
\sin(\pi z) &= \pi z \cdot (1-z^2) \cdot \left(1-\frac{z^2}{4}\right) \cdot \left(1-\frac{z^2}{9}\right) \cdot \left(1-\frac{z^2}{16}\right) \cdots\\
&= \pi \left(z - \zeta(2)z^3 + \text{``higher power of } z \text{''}\right)
\end{align*}
$$
Since we know that $\sin(x) = x - \frac{x^3}{3!} + \frac{x^5}{5!} + \cdots$ , we can show the following.
$$
\sin(\pi z) = \pi z - \frac{(\pi z)^3}{3!} + \text{``higher powers''} \implies \zeta(2) = \frac{\pi^2}{6}
$$
