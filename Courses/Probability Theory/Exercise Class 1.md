#ExerciseClass

##### 0. Organisatory stuff

---
##### 1. Introduction to Probability Theory
1. **How can we mathematically model non-deterministic statements and variables?**
   In probability theory, non-deterministic statements are expressed as events. Non-deterministic variables are expressed using random variables. 
2. **Extending the Sample Space**
   Outcome of a single dice throw $X$. Then, $$\Omega:=\{ 1,2,\dots,6 \}$$as sample space and $X$ as identity. 
	1. The sample space $\Omega$ stays ambient. Most manipulations are done using a random variable.
	2. $E$ be the event that $X$ is even, then $\mathbb{P}(E)=\frac{1}{2}$. 
	3. However, if we want to throw our dice again and let $Y$ be the second dice throw, $\Omega$ is not enough to express our outcomes.
	4. $\Omega':=\Omega \times\Omega$ is a valid sample space with $p\equiv \frac{1}{36}$. Now, the random variables are extended as $X'(i,j)=i$ and $Y(i,j)=j$.
	5. $X=Y$ and $X\leq Y$ are events that now "makes sense".

##### 2. Measure Theory and Sigma Algebra
1. **Why do we need measures?**
	1. $\mu(\varnothing)=0$ and sigma additivity. What are "good sets"?
		$$\mathbb{P}\left( \bigcup_{i=1}^{\infty}A_{i} \right)=\lim_{ n \to \infty } \mathbb{P}\left( \bigcup_{i=1}^{n}A_{i} \right)=\lim_{ n \to \infty } \sum_{i=1}^{n}\mathbb{P}(A_{i})=\sum_{i=1}^{\infty}\mathbb{P}(A_{i})$$
2. **Why do we need sigma algebra?**
3. **Random Variable Jargons**


##### 3. Examples
1. Trivial sigma algebra $\{ \varnothing,\Omega \}$ is the coarsest sigma algebra.
2. Discrete $2^\Omega$. 
3. for an uncountable set $X$: $$\{ A\subseteq X:A \text{ or }A^c\text{ is countable} \}$$
4. arbitrary intersections of sigma algebras are a sigma algebra.
5. generated sigma algebra
6. Borel sigma algebra - Lebesgue Measure

7. measurable functions

8. Properties (monotonicity, union bound)

Let us choose $n$ numbers from $\{ 1,2,3 \}$ with replacement u.a.r. 

Probability that there exists a $3$ in the sequence? $$1-\left( \frac{2}{3} \right)^n$$
Probability that there exists a series of 33 in the sequence? $$\leq (n-1) \frac{1}{9}$$
Probability that there are two sereis of 33. 


---
