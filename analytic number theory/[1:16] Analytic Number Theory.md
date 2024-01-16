# [1/16] Analytic Number Theory

## Introduction

### Recomended Books:

- Davenport: "Multiplicative Number Theory"
- Serve: "A course in Arithmetic"

### Course Outline

1. Proof of Prime Number Theorem
2. Proof of Prine Number Theorem for Arithmetic Progressions

### Grading

1. (60%) HW every $2$ to $3$ weeks
2. (40%) Final Exam

### Prime Number Theorem (Intro)

**Definition:** The function $\pi(x)$ defines the number of prime numbers less than some number $x$. 

$$
\pi (x) := \sum_{p \leq x} 1
$$
**Prime Number Theorem:** As $x \rightarrow \infty$, we have that $\pi(x) \rightarrow \frac{x}{\log(x)}$.

### Arithmetic Progression

**Theorem:** Take any $a,q \in \mathbb{Z}$ and $\text{gcd} (a,q) = 1$. The arithmetic progression is defined as follows (progression 'mod' q):
$$
a,\; a+q, \;a+2q, \;a+3q, \;a+4q \dots
$$
There are infinitely many primes in an arithmetic progression. 

### Prime Number Theorem for Arithmetic Progressions

**Theorem:** $\pi(x,a,q) \rightarrow \frac{x}{\log(x) \cdot \phi(q)}$ where $\phi(q)$ is the number of cyclic generators (group theory).

## [1/16] Notes

### Euclid's Prime

**Theorem:** There exists infinitely many primes.

**Proof:** First, we start with the following lemma. 

- **Lemma:** Let $n > 1$, $n \in \mathbb{Z}$. Then $\exists$ a prime $p$ such that $n|p$ . 
- **Proof:** Lemma is true for $n=2$. Assume $n \geq 2$. For every $l \leq n$, we know that $l$ is divisble by a prime. For $n+1$, either $n+1$ is a prime number, which satisfies the lemma. Or, $n+1$ is not a prime which means that $n+1$ is divisible by some number, which is divisible by a prime. 

For the sake of contradiction, assume $\exists$ finitely many primes ($p_1, p_2, \dots, p_l$). Define some number $N$. 
$$
N := p_1 \cdot p_2 \cdots p_n + 1
$$
By our lemma, we know that there exists some prime $q$, which divides $n$. $N$ is not divisble by any of the smaller primes, which means that it is divisble by some larger prime. This proves that there are <u>infinitely many primes</u>.

**Proposition:** $\pi(x) \geq \log_2(\log_2(x))$ 

**Proof:** Let $p_1, p_2, p_3 \dots$ denote the primes in increasing order. Take the same defined $N$ from above. We know that the $p_{n+1} \leq N$. We also have that
$$
p_1 \cdot p_2 \cdots p_n + 1 \leq 2 \cdot (p_1 \cdot p_2 \cdots p_n)
$$
We can show the following pattern (proof by induction). We can do this by upper-bounding the $p_3 \geq 2 \cdot p_1p_2$ and continue the line of induction.  
$$
P_k \leq 2^{2^{k-1}}
$$
For each positive integer $n$, we know that the $n$-th prime is less than or equal to $2^{2^{k-1}}$, which means that for each $n$, we complete the proof. 
$$
\pi(2^{2^{n-1}}) \geq n
$$

### Arithmetic Progression

**Question:** Can we prove infinitely many primes for an arithmetic progression $a, \; a+q,\;a+2q,\; \dots$, using Euclid and his arguments?

**Answer:** Yes, but only in a few cases.

- There are infinitely many primes $p = 3+4l$ where $l \in \mathbb{Z}$.
  - **Proof:** Assume finite number of primes. Define some $N := 4 p_1 p_2 p_3 + 1$. Here, all $p_i$ are of the form $3 + 4l$ . We know that all primes are in form $p = 3+4l$ or $q = 1+4l$, and we know that not all primes can be of form $1+4l$. 

### Euler (Zeta)

**The Zeta Function:**
$$
\begin{align}
\zeta(s) &= 1 + \frac{1}{2^s} + \frac{1}{3^s} + \frac{1}{4^s} + \dots\\
&= \sum_{n=1}^\infty \frac{1}{n^s}
\end{align}
$$
**Theorem:** Let $f(x) > 0$ and $f$ is integrable. Assume $f(x)$ is decreasing for $x \geq 1$. Let $a_n = f(n)$ for $n = 1,2,3,\dots$ Then, $\sum_{n=1}^\infty a_n$ converges if and only if $\int_1^\infty f(x)\;dx$ converges.

**Corrollary:** If $s > 1$, the $\zeta(s)$ converges. Define some $f(x) = \frac{1}{x^s} \implies \int f(x)\;dx $ converges when $s > 1$.

**Corrollary 2:** Assume $s \in \mathbb{C}$ and define $s = \sigma + it$. 
$$
n^{-s} = n^{-\sigma - it} = n^{-\sigma} \cdot n^{-it} = n^{-\sigma} e^{-it(\log(n))}
$$
Use Euler's formula and bound by $|\cos(t) \pm i\sin(t)| = 1$. 
$$
n^{-\sigma} e^{-it(\log(n))} = n^{-\sigma} \left[\cos(t\log(n)) - i\sin(t\log(n))\right]
$$
If $s \in \mathbb{C}$, then we have that $\Re(s) = \sigma$ and $\Im(s) = t$.  If $\Re(s) > 1$, then the series defining $\zeta(s)$ converges absolutely.  

**Theorem (Euler):** $\zeta (2) = 1+ \frac{1}{4} + \frac{1}{9} + \frac{1}{16} + \dots = \frac{\pi^2}{6}$. 

### Riemann (1859)

**Top Level:** Riemann expressed that $\pi(x)$ can be expressed as a certain integral transform of $\zeta(s)$. 
