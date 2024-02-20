# [2/20] Number Theory

#### Stirling's Asymptotic Formula for $\Gamma$ 

First, consider $\Gamma(x)$ with $x \in \mathbb{R}$, $x \rightarrow +\infty$. 

**Theorem:** (Sterling)
$$
\Gamma(x+1) \backsim \sqrt{2\pi x} \cdot e^{x\log x - x}
$$
If we make a change of variables $x+1 \mapsto x$, we have the following
$$
\Gamma(x) \backsim \sqrt{2\pi x} e^{(x-1)\log x - x}
$$

$$
\Gamma(x) \backsim \frac{\sqrt{2\pi}}{\sqrt{x}} e^{x\log x - x}
$$

**Proof:** The key idea here is the maximum descent approach.
$$
\begin{align*}
\Gamma(x+1) &= \int_{0}^\infty e^{-u}u^x\;du\\
&= \int_0^\infty \underbrace{e^{-u - (\log u)x}\;du}_{u\mapsto xu}\\
&= x \cdot e^{x \log x} \int_0^\infty e^{-x (u -\log u)}\;du
\end{align*}
$$
Let $\phi(u) = (u - \log u)$. This means that $\phi'(u) = \left(1 - \frac{1}{u}\right)$ vanishes for $u = 1$ and that $\phi(u)$ has a global minimum at $u = 1$. This means that $\phi(1) = 1$. 

<u>Claim</u>: We have the following.
$$
\lim_{x\rightarrow \infty} \int_0^{1-\epsilon} e^{-x(u - \log u)} \; du = 0 \quad \quad \quad \lim_{x\rightarrow \infty} \int_{1+\epsilon}^{\infty} e^{-x(u - \log u)} \; du = 0
$$
The above claim implies the result.
$$
\implies \Gamma(x+1) \backsim xe^{x\log x} \int_{1-\epsilon}^{1+\epsilon} e^{-x (u-\log u)}\;du \quad \quad \text{as } x \rightarrow \infty
$$
Now, replace $u - \log u$ with the Taylor expansion around $1$, and we can develop an asymptopic formula for the behavior around $x = 1$ since the higher terms are less important. Let's consider only the first three terms (first derivative vanishes at $u = 1$).
$$
\phi(u) \backsim 1 + \frac{(u-1)^2}{2}
$$
 Using the above, we can show that as $\epsilon \rightarrow 0$.
$$
\begin{align*}
\Gamma(x+1) &\backsim xe^{x\log x} \int_{1-\epsilon}^{1+\epsilon} e^{-x \left(1+\frac{(u-1)^2}{2}\right)}\;du\\
&\backsim xe^{x\log x - x} \int_{1-\epsilon}^{1+\epsilon} e^{-x \frac{(u-1)^2}{2}}\;du\\
&\backsim xe^{x\log x - x} \int_{\infty}^{\infty} e^{-x \frac{(u-1)^2}{2}}\;du\\
\end{align*}
$$
Next, let $v = \sqrt{x} (u-1)$ such that $dv = \sqrt{x}\; du$. The first step is obvious, but the second step (exact formula) takes a bit more work!
$$
\begin{align*}
\Gamma(x+1) &\backsim \sqrt{x} e^{x \log x - x} \underbrace{\int_{-\infty}^\infty e^{-\frac{v^2}{2}}\;dv}_{\sqrt{2\pi}}\\
&= \sqrt{2\pi x} e^{x \log x - x} + \mathcal{O}\left(\frac{1}{x}\right)
\end{align*}
$$
**Theorem:** (Sterling) Let $s \in \mathbb{C}$ with $\Re(s) > 0$. Then, $\Gamma(s) = s \log s - s - \frac{1}{2} \log s + \frac{\log(2\pi)}{2} + O(1)$. 
$$
\Gamma(s) \backsim \sqrt{2\pi} \frac{e^{s \log s - s}}{\sqrt{s}}
$$
<u>Eurler's Product Formula for $\Gamma$</u>: This was proved in class.
$$
\Gamma(s) = \lim_{N\rightarrow \infty} \frac{N^s}{s} \prod_{k=1}^N \frac{k}{s+k}
$$
Now, take the $\log$ of the above formula to garner the following result.
$$
\begin{align*}
\log \Gamma(s) &= \lim_{N\rightarrow \infty} s \log N - \log s + \sum_{k=1}^N \left(\log k - \log (s + k)\right) \\
\frac{d}{ds} \log \Gamma(s) &= \lim_{N\rightarrow \infty} \left(\log N - \frac{1}{s} - \sum_{k=1}^N \frac{1}{s+k}\right)\\
\frac{d^2}{ds^2} \log \Gamma(S) &= \sum_{k=0}^\infty \frac{1}{(s+k)^2} 
\end{align*}
$$
Next, we can say that the sum can be rewritte as follows.
$$
\sum_{k=0}^\infty \frac{1}{(s+k)^2} = \frac{1}{2s^2} - \frac{1}{2\pi i} \int_{-i\infty}^{+i\infty} \frac{\pi \cot(\pi w)}{(s+w)^2}\;dw
$$
The way we derive this is via the complex conversion for $\cot$.
$$
\cot(\pi w) = \frac{\cos(\pi w)}{\sin(\pi w)} = i\frac{1+e^{-2\pi i w}}{1- e^{-2\pi i w}}
$$
We integrate along this contour $\mathcal{R}_T$.

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-02-20 at 3.21.20 PM.png" alt="Screenshot 2024-02-20 at 3.21.20 PM" style="zoom:50%;" />

In this case, we want to look at the integral.
$$
\frac{1}{2\pi i} \int_{\partial \mathcal{R}_T} \frac{\pi \cot(\pi w)}{(s+w)^2}\;dw = \sum_{\text{residues}}
$$

$$
\Res_{s=k} \frac{\pi \cot(\pi w)}{(s+w)^2} = \frac{1}{(s+k)^2} \quad \quad k=1,2,3,4,5\dots
$$



---

The way the semicircle behaves gives us "half the residue".
$$
\frac{1}{2\pi i} \int_{|z| = 1}\frac{dz}{z} = 1 \implies z = e^{i \theta} \implies \frac{1}{2\pi i} \int_{0}^{2\pi} \frac{e^{i\theta} i}{e^{i\theta}}\;d\theta = 1
$$
If we pick the bounds from $[0,\pi]$, that's how we get a $\frac{1}{2s^2}$ for the residue at $s = 0$.

---

Now, we have the formula, and let $w = iu$. 
$$
\begin{align*}
\sum_{k=0}^\infty \frac{1}{(s+k)^2} &= \frac{1}{2s^2} - \frac{1}{2\pi i} \int_{-i\infty}^{+i\infty} \frac{\pi \cot(\pi w)}{(s+w)^2}\;dw\\
&= \frac{1}{2s^2} - \frac{1}{2\pi i} \int_{\infty}^{\infty} \frac{\pi \cot(\pi i u)}{(s+iu)^2}\;i\;du\\
&= \dots + \int_{-\infty}^{0} \dots + \int_0^{\infty} \dots
\end{align*}
$$
This means that we get the following.
$$
\begin{align*}
\frac{d^2}{ds^2} \log \Gamma(s) &= \sum_{k=0}^\infty \frac{1}{(s+k)^2} = \frac{1}{2} \int_0^\infty \cot(\pi iu)\left(\frac{1}{(s+iu)^2} - \frac{1}{(s-iu)^2}\right)\;du\\
&= \int_0^\infty \cot(\pi i u) \frac{2us}{(u^2 + s^2)^2}\;du\\
&= \int_0^\infty \left(1+\frac{2}{e^{2\pi u}-1}\right)\frac{2us}{(u^2 + s^2)^2}\;du\\
&= \frac{1}{s} + \frac{1}{2s^2} + \int_1^\infty \frac{4u s}{(u^2 + s^2)^2} \;\frac{du}{e^{2\pi u}-1}
\end{align*}
$$
Next, we want to integrate both sides with respect to $s$.
$$
\frac{d}{ds} \log \Gamma(s) = C + \log(s) - \frac{1}{2s} - \int_0^\infty \frac{2u}{(u^2 + s^2)} \;\frac{du}{e^{2\pi u} -1}
$$
Next, you need to integrate by parts.
$$
\int_0^\infty \frac{2u}{(u^2 + s^2)} \;\frac{du}{e^{2\pi u} -1} = -\frac{1}{\pi} \int_0^\infty \frac{s^2 - u^2}{(u^2 + s^2)^2} \left(1-e^{-2\pi u}\right)\;du
$$
This gives us the complete formula.
$$
\frac{d}{ds} \log \Gamma(s) = C + \log(s) - \frac{1}{2s} + \frac{1}{\pi} \int_0^\infty \frac{s^2 - u^2}{(u^2 + s^2)^2} \left(1-e^{-2\pi u}\right)\;du
$$
Integrate both sides, and we get the following identity.
$$
\log \Gamma(s) = C' + Cs + \left(s- \frac{1}{2}\right)\log s + \frac{1}{\pi} \int_0^\infty \underbrace{\frac{s}{u^2 + s^2} \log\left(\frac{1}{1-e^{-2\pi u}}\right)}_{\text{small as }|s| \rightarrow \infty}\;du
$$
We can match up terms to get the constants $C', C$. Furthermore, we can get the following asymptotic relatinoships from simple derivation.
$$
\left|\Gamma(\sigma + it)\right| \backsim|t|^{\sigma - \frac{1}{2}} e^{\frac{\pi}{2}(t)} \quad \quad \quad |t|\rightarrow \infty
$$

#### Hadamard's Theory of Entire Functions of Finite Order

**Definition:** (Entire function of order $\alpha \geq 0$) The order of an entire function $f: \mathbb{C} \rightarrow \mathbb{C}$ is the smallest $\alpha \geq 0$ such that for any fixed $\epsilon > 0$ and for all $z \in \mathbb{C}$, 
$$
|f(z)| \ll_{\epsilon} e^{|z|^{\alpha + \epsilon}}
$$
<u>Question 1</u>: Polynomials $a_0 + a_1z + a2 z^2 + \dots + a_nz^n$ where $a_1 \in \mathbb{C}$ have order $=0$. 

<u>Question 2</u>: What is the order of $\sin (z)$ ? This has order $= 1$. 

<u>Question 3</u>: Can you give an example of an entire function of order $= 2$. Examples include $\sin(z)^2, e^z$.

<u>Question 4</u>: Is there an entire function of infinite order? $e^{e^z}$ 