# [1/24] Math Seminar

### General Notes

- Every class is two parts: 1 talk before the break, 1 talk after the break

### Giving + Attending Talks

**Attending Talks:**

- Try to refocus
- Notes
- Questions
  - What is the main question the talk is trying to answer?
  - Why are we trying to answer this question?
  - How does the talk answer the question?
  - What is the answer to the question?
- Get one thing out of the talk
  - Definition, Theorem, Technique
- Formulate a Question

**Giving Talks:**

- Structure
  - Connect the talk to a future/past talk
  - Summarize (in proportion)
- Know Your Audience 
- Prepare (give a practice talk)
- Engagement/Audience Interaction

**Dual Concepts to Attending:**

- Limit details within reason
- Timing (end on time)
  - Don't talk too fast (also don't talk too slowly)
- Sources + Questions

**Slides:**

- Cover Material
- Images, Graphs, Long Formulas

- (Chalk Talk): Worry about speed, flexible, 
- Slides also give you a set of notes!

### Number Theory

**Fundamental Theorem of Arithmetic:** Every positive integer has a unique prime factorization.

**Prime Number Theorem:** We define $\pi(x) - \text{number of primes up to } x$. 
$$
\lim_{x \rightarrow \infty} \frac{\pi(x)}{\frac{x}{\log(x)}} = 1
$$
**Linear Algebra**: We define $M_{m \times n} (R)$ where this is the set of $m \times n$ matrices over a ring $R$. 

Consider the determinant map $\det: M_{m \times n}(R) \rightarrow R$. We know that $A$ is invertible iff $\det(A) \in R^x$. 

**Group Theory:** 

- $GL_n(R)$ is the group of invertible matrices over $R$. 
- $SL_n(R) \subset GL_n(R)$ is the group of matrices with $\det(A) = 1$, which implies invertibility

### Lagranges Theorem

**Theorem:** Every $n \geq 1$ can be written as the sum of $4$ squares.
$$
n = (x_1)^2 + (x_2)^2 + (x_3)^2 + (x_4)^2
$$
**Setup:** If $P(m)$ and $P(n)$, then we know that $P(n \times m)$. If $P(p)$ holds for all primes $p$, then we have that $P(n)$ for all numbers $n$ by the FTA. 

<u>Step 1</u>: $P$ multiplicative

<u>Step 2:</u> $P(p)$ for all primes $p$ 

**Proof:** Use Euler's identity.
$$
\begin{align*}
P(m)P(n) &= \overbrace{\left(x_1^2 + x_2^2 + x_3^2 + x_4^2 \right)}^m \overbrace{\left(y_1^2 + y_2^2 + y_3^2 + y_4^2 \right)}^n\\
&= \underbrace{(x_1y_1 + x_2y_2 + x_3y_3)^2 + (x_1y_2 - x_2y_1 - x_3y_4 + x_4y_3)^2 + \dots}_{4\;\text{total square terms}}\\
&= P(m \cdot n)
\end{align*}
$$
First, we show that $P(2) = 1^2 + 1^2$ and $P(1) = 1^2$ . Now, we want to show this proof in two steps. First, we must show that $\exists \;n$ such that $P(np)$ is true. The second step will be to show that $n \in \{n : P(np)\} = S$ and $\min(S) = 1$. 

 

