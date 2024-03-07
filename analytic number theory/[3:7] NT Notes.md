# [3/7] NT Notes

#### Dirichlet Characters

Dirichlet Characters ($\text{mod} \;q$) $\chi : \mathbb{Z} \rightarrow \mathbb{C}$ 

1. $\chi( a + q) =  \chi (a)$ 
2. $\chi(ab) = \chi(a)\chi(b)$ 
3. $\chi(a) = 0$ iff $(a,q) > 1$​ 

For example, we have $\chi \text{ mod } 4$. 

- $\chi(1) = 1, \chi(2) = 0, \chi(3) = -1, \chi(4) = 0$ 
- Trivial Character: $\chi_0(1) = 1, \chi_0(2) = 0, \chi_0(3) = 1, \chi_0(4) = 0$. 

<u>Note</u>: $L(s,\chi) = \sum_{n=1}^\infty \frac{\chi(n)}{n^s}$ 
$$
\begin{align*}
L(s,\chi) &= \sum_{n=1}^\infty \frac{\chi(n)}{n^s} = 1 - \frac{1}{3^s} + \frac{1}{5^s} - \frac{1}{7^s} + \cdots\\
&= \prod_p \left(1 - \frac{\chi(p)}{p^s}\right)^{-1}
\end{align*}
$$

$$
\begin{align*}
L(s,\chi_0) &= 1 + \frac{1}{3^s} + \frac{1}{5^s} + \frac{1}{7^s} + \cdots\\
&= \prod_{p\neq 2} \left(1-\frac{1}{p^s}\right)^{-1} \\
&= \zeta(s) \left(1-\frac{1}{2^s}\right)
\end{align*}
$$

**Proof:** Dirichlet's proof that $\sum_{p \equiv 1 \text{ mod } 4} \frac{1}{p} = \infty$ 
$$
\lim_{s\rightarrow 1} \left(\log L (s, \chi_0) + \log L(s,\chi_1)\right) \quad \quad s>1
$$
We also know that following.
$$
\begin{align*}
\log L(s,\chi) &= -\sum_{p\neq 2} \log\left(1 - \frac{\chi(p)}{p^s}\right) = \sum_{p\neq 2} \frac{\chi(p)}{p} + \mathcal{O}(1)\\
&= \sum_{p \neq 2} \frac{\chi_1(p)}{p^s} + \mathcal{O}(1)
\end{align*}
$$

$$
\begin{align*}
\log L(s,\chi_0) = \log \zeta(s) + \mathcal{O}(1) &= \frac{1}{s-1} + \mathcal{O}(1)\\
&= \sum_{p\neq 2} \frac{1}{p^s} + \mathcal{O}(1)
\end{align*}
$$

This allows us to evaluate the original expression.
$$
\begin{align*}
\lim_{s\rightarrow 1} \left(\log L (s, \chi_0) + \log L(s,\chi_1)\right) &= \lim_{s\rightarrow 1}\; \log \zeta(s) + \sum_{p\neq 2} \frac{\chi(p)}{p} + \mathcal{O}(1)\\
&= \lim_{s\rightarrow 1} 2 \sum_{p \equiv 1 \text{ mod }4} \frac{1}{p^s}
\end{align*}
$$
We also know that $\lim_{s \rightarrow 1} \log L(s,\chi_0) = \infty$. If $L(1, \chi_1) > 0$, then we just need to prove that $\sum_{p \equiv 1 \text{ mod } 4} = \infty$. Since the term looks like the following,
$$
\begin{align*}
L(1,\chi_1) &= 1 - \frac{1}{3} + \frac{1}{5} - \frac{1}{7} + \frac{1}{9} - \frac{1}{11} \cdots\\
&= \int_0^1 (1 - t^2 + t^4 - t^6 + \dots)\;dt\\
&= \int_0^1 \frac{dt}{1+t^2} = \frac{\pi}{4}
\end{align*}
$$
**Proof:** We do the same thing but for $\chi \text{ mod } 3$. 

|          | 1    | 2    | 3    |
| -------- | ---- | ---- | ---- |
| $\chi_0$ | 1    | 1    | 0    |
| $\chi_1$ | 1    | -1   | 0    |

We also know the following $L$ definitions:
$$
L(s,\chi_1) = 1 -\frac{1}{2^s} + \frac{1}{4^s} - \frac{1}{5^s} + \frac{1}{7^s} \cdots
$$
The prove that there are infinitely many primes $p \equiv 1 \text{ mod } 3$, we just needto show that $L(1,\chi_1) > 0$. 
$$
\lim_{s\rightarrow 1} \left(\log L(s,\chi_0) + \log L(s,\chi_1)\right) = 2\left(\frac{1}{4^s} + \frac{1}{7}^s + \cdots\right) + \mathcal{O}(1)
$$
Thus, we also have the following.
$$
\begin{align*}
L(1,\chi_3) &= \int_0^1 \left(1 - t + t^3 - t^4 + t^6 - t^7\cdots \right)\;dt\\
&= \int_0^1 (1-t)\left(1 + t^3 + t^6 + \dots\right)\;dt
\end{align*}
$$
**Proof:** Now, let's look at a case where Euclid breaks down where $p \equiv 1 \text{ mod } 5$. 

|          | 1    | 2    | 3    | 4    | 5    |
| :------- | ---- | ---- | ---- | ---- | ---- |
| $\chi_0$ | 1    | 1    | 1    | 1    | 0    |
| $\chi_1$ | 1    | -1   | -1   | 1    | 0    |
| $\chi_2$ | 1    | $i$  | $-i$ | -1   | 0    |
| $\chi_3$ | 1    | $-i$ | $i$  | 1    | 0    |

Now, let's exam the following term.
$$
\begin{align*}
\lim_{s\rightarrow 1} \left(\log L(s,\chi_0) + \log L(s,\chi_1) +\log L(s,\chi_2) + \log L(s,\chi_3) \right)  &= \cdots\\
&= \sum_{p\neq s} \left(\frac{1}{p^s} + \frac{\chi_1(p)}{p^s} + \frac{\chi_2(p)}{p^s} + \frac{\chi_3(p)}{p^s}\right)  + \mathcal{O}(1)\\
&= 4 \cdot \sum_{p \equiv 1 \text{ mod } 5} \frac{1}{p^s}
\end{align*}
$$
We want to show that the RHS $\rightarrow \infty$ as $s \rightarrow 1$. We know that $\lim_{s\rightarrow 1} L(s, \chi_0) = \infty$. 
$$
\begin{align*}
L(1,\chi_1) &= 1- \frac{1}{2}  - \frac{1}{3} + \frac{1}{4} + \cdots \\
&> 0
\end{align*}
$$
 If we show that one has real and imaginary parts $> 0$, then we can show the other.
$$
\begin{align*}
L(1,\chi_2) &= 1 + \frac{i}{2} - \frac{i}{3} - \frac{1}{4} + \cdots\\
&= 1 - \frac{1}{4} + i\left(\frac{1}{2} - \frac{1}{3}\right) + \cdots\\
&> 0
\end{align*}
$$

#### Orthogonality Relations for Dirichlet Characters

**First Relation:** Image $\chi$ is a Dirichlet character of mod $q$. 
$$
\frac{1}{\phi(q)} \sum_{n=1}^q \chi(n) = \begin{cases} 1 & \chi=\chi_0\\
0 & \chi \neq \chi_0
\end{cases}
$$
This is the idea that all things add up across rows! If $\chi \neq \chi_0 \implies \chi_n$ takes a value $a$ where $\chi(a) \neq 0,1$. 
$$
\chi(a) \cdot S = \frac{1}{\phi(q)} \sum_{n=1}^q \chi(an) = S \implies S = 0
$$
**Second Relation:** We have the following.
$$
\frac{1}{\phi(q)} \sum_{\chi \text{ mod }q} \chi(n) \equiv \begin{cases}
1 & n = 1 \text{ mod }q\\
0 & \text{otherwise}
\end{cases}
$$
<u>Case</u>: Take $q = p^k$ and $p$ is odd. Look at the set $G_{p^k} = \{a_1, a_2, \dots, a_{\phi(q)}\}$. For example, $G_9 = \{1,2,4,5,7,8\}$. Let $g$ be a generator for this group $G_{p^k}$. Now, define some character $\chi_a(g) = e^{\frac{2\pi i a}{\phi(q)}}$ where $\chi_b \cdot \chi_a = \chi_{a+b}$. 

<u>Proof</u>: Pick some character $\chi'(n)$. Now, construct the following
$$
\chi'(n) \cdot S = \frac{1}{\phi(q)} \sum_{\chi \text{ mod }q} \chi'\chi(n) = S
$$
In this case, we know that $\chi'(n) \neq 1$, but in every other case, we know that there is some $\chi \neq 1$. 

**Third Relation:** We have the following where we assume $(a,q) = 1$ and $(n,q) = 1$. 
$$
\frac{1}{\phi(q)} \sum_{\chi \text{ mod }q} \chi(n) \cdot \overline{\chi}(a) = \begin{cases}
1 & a \equiv n \text{ mod }q\\
0 & \text{otherwise}
\end{cases}
$$
We want to examine this expression for $s > 1$
$$
\begin{align*}
\frac{1}{\phi(q)} \sum_{\chi \text{ mod }q} \left(\log L(s,\chi) \right) \overline{\chi}(a) &= \frac{1}{\phi(q)} \sum_{\chi} \sum_{p} \frac{\chi_{p}}{p^s} \;\overline{\chi}(a) + \mathcal{O}(1)\\
&= \frac{1}{\phi(q)} \sum_{p} \frac{1}{p^s} \sum_{\chi \mod q} \chi(p) \overline{\chi}(a) = \sum_{p \equiv a \text{ mod }q} \frac{1}{p^s}
\end{align*}
$$
To prove infinitely many $p \equiv a \text{ mod }q$, we need to show $L(1,\chi) \neq 0$ for all $\chi \text{ mod }q$.  

---

**Proposition:** Let $\chi \neq \chi_0$. Then $L(s,\chi)$ is holomorphic for $\Re(s) > 0$. 

**Abel Summation:** Let $a_n, b_n \in \mathbb{C}$ where $n \in \mathbb{N}$. Next, let $S(x) = \sum_{n\leq x} b_n$. Then, $\sum_{n \leq N} a_nb_n =a_N S(N) + \sum_{n=1}^{N-1} (a_n - a_{n+1}) S(n)$.  

**Proof:** Abel Summation!
$$
\begin{align*}
\sum_{n=1}^N a_nb_n &= \sum_{n=1}^N a_n(S(n) - S(n-1))\\
&= \sum_{n=1}^N a_nS(n) - \sum_{n=2}^N \underbrace{a_n S(n-1)}_{n\;\mapsto \;m+11}\\
&= \sum_{n=1}^N a_n S(n) - \sum_{m=1}^{N-1} a_{m+1} S(m)\\
&= a_N S(N) + \sum_{n=1}^{N-1} (a_n - a_{n+1}) S(n)
\end{align*}
$$
Now, let's use Abel Summation to prove the proposition.

**Proof:** Proposition.
$$
\sum_{n=1}^q \chi(n) = 0
$$
Let $S(N) = \sum_{n=1}^N \chi(n) \implies |S(N)| \leq q$. This means that we can express the following where $s = \sigma + it$ 
$$
\begin{align*}
L(s,\chi) &= \lim_{ N\rightarrow \infty}\sum_{n-1}^N n^{-s} \cdot \chi(n)\\
&\leq \lim_{N\rightarrow\infty} \left(N^{-\sigma}q) + \sum_{n=1}^{N-1} \left(n^{-\sigma} - (n+1)^{-\sigma}\right)\cdot q\right)\\
&= q \lim_{N\rightarrow\infty} \sum_{n=1}^{N-1} \frac{(n+1)^{\sigma} - n^\sigma}{n^\sigma (n+1)^\sigma}\\
&= q \lim_{N\rightarrow\infty} \sum_{n=1}^{N-1} \frac{\left(1+\frac{1}{n}\right)^\sigma - 1}{(n+1)^\sigma}\\
&\ll q \sum_{n=1}^\infty \frac{\sigma}{n(n+1)^\sigma} \ll q \cdot \sigma
\end{align*}
$$
This is beacuse $\left(1 + \frac{1}{n}\right)^\sigma - 1 \ll \frac{\sigma}{n}$. 