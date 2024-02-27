# [2/27] Number Theory

#### Hadamard's Product Formula

**Theorem:** Let $f: \mathbb{C} \rightarrow \mathbb{C}$ be an entire function of Hadamard order $0 \leq \alpha < \infty$. Let $f(z)$ vanish at $z = 0$ with multiplicity $r$. Let $\rho_1, \rho_2, \dots$ be the other zeroes of $f(z)$ listed with multiplicity and $|\rho_1| \leq |\rho_2| \leq \dots$ 

Set $a = \lfloor a \rfloor$. Then,
$$
f(z) = e^{p(z)} \cdot z^r \cdot \prod_{k=1}^\infty \left(1-\frac{z}{\rho_k}\right) e^{\sum_{\ell = 1}^a \frac{(z/\rho_k)^\ell}{\ell}}
$$
Furthermore, the product converges for all $z \in \mathbb{C}$ and $p(z)$ is a polynomial with $\deg(p) \leq a$.  

**Corollary:** Let $f(z)$ be entire of aribtrary order $\alpha \geq 0$ and doesn't vanish. This implies that, for some polynomial $p(z)$ where $p(z) = c_0 + c_1z + \cdots + c_az^a$ and $a = \lfloor \alpha \rfloor$,
$$
f(z) = e^{p(z)}
$$

---

<u>Example</u>: What is the Hadamard product for $\sin(\pi z)$ ?

<u>Solution</u>: We have already shown that $\sin(\pi z)$ has Hadamard order $=1 \implies r =1$. We also know that $p(z) = A + Bz$ for some $A,B \in \mathbb{C}$. Finally, we have that $\sin(\pi z) = 0$ for $z = \pm \mathbb{N}$. 
$$
\begin{align*}
\implies \sin(\pi z) &= e^{A+Bz} \cdot (\pi z)\cdot \prod_{n\neq 1} (1-\frac{z}{n})e^{\frac{z}{n}}\\
&= e^{A+Bz} \cdot (\pi z)\cdot \prod_{n=1}^\infty \left(1-\frac{z^2}{n^2}\right) 
\end{align*}
$$
We want to know show that $A = B = 0$. We will use the Taylor-series expansion of $\sin(\pi z)$ to show that $A = 0$.
$$
\sin (\pi z) = \pi z - \frac{(\pi z)^3}{3!} + \frac{(\pi z)^5}{5!} + \cdots \implies \lim_{z\rightarrow 0} \frac{\sin(\pi z)}{\pi z} = 1
$$
Now, we are left with the expression only in terms of $B$.
$$
e^{Bz} \cdot (\pi z)\cdot \prod_{n=1}^\infty \left(1-\frac{z^2}{n^2}\right)
$$
The rest is left as an exercise.

----

**Proof (of Corollary):** Let $f$ have order $=0$. Define $g(z) = \log f(z)$. Since $f(z) \neq 0 \implies g$ is entire! 
$$
\implies f(z) = e^{g(z)}
$$
It remains to prove that $g(z) = p(z)$ where $p$ is a polynomial of order $a =\lfloor \alpha\rfloor$. Now, we know that $f$ has order $= \alpha \implies \Re(g(z)) = \log f(z) \ll R^{\alpha + \epsilon}$ for $R \rightarrow \infty$. 

Since $g(z)$ is entire, it has a Taylor series which converges $\forall\;z \in \mathbb{C}$. 
$$
g(z) = \sum_{m=0}^\infty c_m z^m
$$
Let's choose $z = Re^{i\theta} \implies |z| = R$ such that the folllowing is true.
$$
\Re(g(z)) = \sum_{m=0}^\infty \big(\alpha_m R^m \cos(m\theta) - \beta_m R^m \sin(m\theta)\big)
$$
We can use Fourier theory to pick out the $m$-th coefficient such that the following equation is true.
$$
\pi \alpha_m R^m  = \int_0^{2\pi} \Re(g(Re^{i\theta})) \cos m(\theta)\;d\theta \ll R^{\alpha + \epsilon}
$$
If we let $R \rightarrow \infty$, then we have $\alpha_m = 0$ for all $m > a$. 

---

**Proof (of Hadamard Theorem):** For entire functions of order $=1$. 

<u>Goal</u>: ($*$) We want to prove that this holds.
$$
f(z) = e^{A+Bz} \cdot z^r \cdot \prod_{k=1}^\infty \left(1-\frac{z}{\rho_k}\right) e^{\frac{z}{\rho_k}}
$$
**STEP 1**: We first prove that this product $\prod_{k=1}^\infty (1-\frac{z}{\rho_k}) e^{\frac{z}{\rho_k}}$ converges absolutely for all $z \in \mathbb{C}$. 

Assume that the $|z| = R$. It's enough to prove the following converges absolutely.
$$
\prod_{|\rho_k| > 2R} \left(1-\frac{z}{\rho_k}\right) e^{\frac{z}{\rho_k}}
$$
First, we take the log of the product and notice that $\left|\frac{z}{\rho_k}\right| < \frac{1}{2}$. 
$$
\begin{align*}
\left|\log \left(\prod_{|\rho_k| > 2R} \left(1-\frac{z}{\rho_k}\right) e^{\frac{z}{\rho_k}}\right)\right| &= \sum_{|\rho_k| > 2R} \left|\left(\log\left(1-\frac{z}{\rho_k}\right) + \frac{z}{\rho_k} \right)\right|\\
&= \sum_{|\rho_k| > 2R} \left|\left(\frac{z}{\rho_k} - \frac{\frac{z}{\rho_k}^2}{2} + \frac{\frac{z}{\rho_k}^3}{3} \dots\right) + \frac{z}{\rho_k} \right|\\
&\ll \sum_{\rho_k - 2R} \left|\frac{z}{\rho_k}\right|^2 < \infty
\end{align*}
$$
This is a result from a theorem in class where we stated that if $f$ has order $=1$, then that implies the following result of convergence.
$$
\sum_{k=1}^\infty \frac{1}{|\rho_k|^{1+\epsilon}} < \infty
$$
**STEP 2**: Let $P(z) = \prod_{k=1}^\infty \left(1-\frac{z}{\rho_k}\right) e^{\frac{z}{\rho_k}}$. 

<u>Claim</u>: For a suitable sequence of $R \rightarrow \infty$,
$$
\left|P(z)\right| > e^{-R^{1+\epsilon}}
$$
Assuming this claim, we can quickly prove Hadamard's product Theorem. In other words, the proof of the claim implies $(*)$. 

The proof would continue as follows. Let $|z| = R$. Let $F(z) := \frac{f(z)}{z^r \cdot P(z)}$. Consider $|F(z)|$. 
$$
|F(z)| \ll \frac{e^{R^{1+\epsilon}}}{P(z)} \ll e^{R^{1+2\epsilon}}
$$
**STEP 3:** Proof of Claim.

---

<u>Lemma 1</u>: (Choosing a sequence $R \rightarrow \infty$) 

There exist arbitrarily large values of $R$ such that $\left|R - |\rho_{k}|\right| > |\rho_k|^{-2}$ for all $k = 1,2,3,\dots$​ 

<u>Proof</u>: (Lemma 1)
$$
\sum_{k=1}^\infty \frac{1}{|\rho_k|^2} < \infty
$$
This implies that the total length of all intervals $I$ where $I = \left[|\rho_k| - |\rho_k|^{-2}, |\rho_k|+ |\rho_k|^{-2}\right]$ is finite. Now, let
$$
P(z) = P_1(z) \cdot P_2(z) \cdot P_3(z)
$$
We define the terms of the product as follows.
$$
P_1(z) = \prod_{|\rho_k| < \frac{R}{2}} \left(1-\frac{z}{\rho_k}\right) e^{\frac{z}{\rho_k}}
$$

$$
P_2(z) = \prod_{\frac{R}{2} < |\rho_k| < 2R} \left(1-\frac{z}{\rho_k}\right) e^{\frac{z}{\rho_k}}
$$

$$
P_3(z) = \prod_{2R < |\rho_k| } \left(1-\frac{z}{\rho_k}\right) e^{\frac{z}{\rho_k}}
$$

------

We will now show that each $P_i$ satisfies the bound set up in the claim. Start with $P_1(z)$ where $|z| = R$ and $|\rho_k| < \frac{R}{2}$. 
$$
\left|1 -\frac{z}{\rho_k}\right| \cdot e^{\frac{|z|}{|\rho_k|}} > \left|\frac{z}{\rho_k} - 1\right| e^{\frac{-R}{|\rho_k|}}
$$
Now, we look at the sum and complete the proof of the bound.
$$
\sum_{|\rho_k| < \frac{R}{2}} |\rho_k|^{-1} < \left(\frac{R}{2}\right)^{\epsilon} \sum_{k=1}^\infty |\rho_k|^{-1-\epsilon} \implies |P_1(z)| > e^{-R^{1+2\epsilon}}
$$
Next, for $P_2(z)$, we approach from a different direction for some $c > 0$.
$$
\left|1-\frac{z}{\rho_k}\right|\cdot  e^{\left|\frac{z}{\rho_k}\right|} \geq \left|\frac{R-\rho_k}{\rho_k}\right| \cdot e^{\frac{R}{|\rho_k|}} \geq \frac{e^{-2}|R - \rho_k|}{2R}  > c\frac{1}{R^3}
$$
Thus, we have the folllowing bound.
$$
P_2(z) > \left|cR^{-3}\right|^{R^{1+\epsilon}} > e^{-R^{1+2\epsilon}}
$$
Proving $P_3(z)$ bound will be a homework problem.