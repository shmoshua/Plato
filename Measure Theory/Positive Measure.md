#Definition #MeasureTheory 

> [!definition]
> For a measurable space $(X,\mathcal{A})$, a ***(positive) measure*** is a map $\mu: \mathcal{A}\to [0,+\infty]$ s.t. 
> 1. $\mu(\varnothing)=0$ and
> 2. **$\sigma$-additive**: $\mu\left( \bigsqcup_{n=1}^{\infty}E_{n} \right)=\sum_{n=1}^{\infty}\mu(E_{n})$ for all disjoint $E_{1},E_{2},\dots\in \mathcal{A}$.


- **Remark**: The definition implies monotonicity and [[Additive Functions| $\sigma$-subadditivity]] of $\mu$.
- **Related definition**: A measure $\mu$ is said to be 
	1. ***finite***, if $\mu(X)<+\infty$
	2. ***$\sigma$-finite***, if there exists $(A_{n})_{n}\subseteq \mathcal{ P}(X)$ s.t. $\bigcup_{n=1}^{\infty}A_{n}=X$ and $$\mu(A_{n})<+\infty$$ for all $n$.
	3. a ***probability measure***, if $\mu(X)=1$.
	4. ***metric***, if $X=\mathbb{R}^n$  and for all $A,B \subseteq \mathbb{R}^n$, the distance: $$d(A,B):=\inf\{ |a-b|:a\in A,b\in B \}>0$$we have: $$\mu(A \cup B)=\mu(A)+\mu(B)$$
--- 
##### Examples
1. **Dirac Measure**: $\delta_{x}:\mathcal{P}(X)\to[0,+\infty]$ for $x\in X$, defined as: $$\delta_{x}(A)=\begin{cases}1&x\in A\\0&x\notin A\end{cases}$$
2. **Counting Measure**: $\mu:\mathcal{P}(X)\to[0,+\infty]$, defined as: $$\mu(A)=\begin{cases}|A|&A \text{ is finite}\\ +\infty &\text{otherwise}\end{cases}$$ For the counting measure, $\Sigma=\mathcal{P}(X)$.
3. Measure with $\Sigma=\{ \varnothing,X \}$: $\mu:\mathcal{P}(X)\to[0,+\infty]$, defined as: $$\mu(A)=\begin{cases}0&A=\varnothing\\ 1 &A \neq \varnothing\end{cases}$$ Then, $\Sigma=\{ \varnothing,X \}$.

---
##### Related Definitions
- [[Measurable Set]]
- [[Lebesgue Measure]]
- [[Jordan Measure]]
- [[Borel Measure]]
---