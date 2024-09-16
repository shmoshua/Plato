#Definition #MeasureTheory 

> [!definition]
> Let $\mathcal{A}\subseteq \mathcal{P}(X)$ be an [[Boolean Algebra|algebra]] and $\mu:\mathcal{A} \to [0,+\infty]$ with $\mu(\varnothing)=0$.
> 1. $\mu$ is **additive**, if for any disjoint $A_{1},\dots,A_{n}\in \mathcal{A}$, i.e. $A_{i}\cap A_{j}=\varnothing$ for $i \neq j$, we have: $$\mu \left( \bigcup_{i=1}^{n}A_{i} \right) =\sum_{i=1}^{n}\mu(A_{i})$$
> 2. $\mu$ is **$\sigma$-additive**, if for any disjoint $(A_{n})_{n}\subseteq \mathcal{A}$, i.e. $A_{i}\cap A_{j}=\varnothing$ for $i \neq j$ s.t. $\bigcup_{n=1}^{\infty}A_{n}\in \mathcal{A}$, we have: $$\mu \left( \bigcup_{n=1}^{\infty}A_{n} \right) =\sum_{n=1}^{\infty}\mu(A_{n})$$
> 	Notice that the condition $\bigcup_{n=1}^{\infty}A_{n}\in \mathcal{A}$ always holds if $\mathcal{A}$ is a $\sigma$-algebra.
> 3. $\mu$ is **$\sigma$-subadditive**, if for any $(A_{n})_{n}\subseteq \mathcal{A}$ s.t. $\bigcup_{n=1}^{\infty}A_{n}\in \mathcal{A}$, we have: $$\mu \left( \bigcup_{n=1}^{\infty}A_{n} \right) \leq\sum_{n=1}^{\infty}\mu(A_{n})$$
> 	Notice that the condition $\bigcup_{n=1}^{\infty}A_{n}\in \mathcal{A}$ always holds if $\mathcal{A}$ is a $\sigma$-algebra.

- **Remark**: If $\mu$ is $\sigma$-additive, it is also additive.
- **Related definition**: A $\sigma$-additive function $\mu$ on algebra $\mathcal{A} \subseteq \mathcal{ P}(X)$ is said to be:
	1. ***finite***, if $\mu(X)<+\infty$.
	2. ***$\sigma$-finite***, if there exists a sequence $(A_{n})_{n}\subseteq \mathcal{A}$ s.t. $\bigcup_{n=1}^{\infty}A_{n}=X$ and $$\mu(A_{n})<+\infty$$
    
    for every $n$. We may assume wlog that the $A_{k}$'s are mutually disjoint.
---
##### Properties
> [!lemma] Theorem 1
> If $\mu$ is additive on $\mathcal{A}$, then it is also monotonous w.r.t inclusion.

>[!proof]-
>For $A,B\in \mathcal{A}$ s.t. $A \subseteq B$, we have: $\mu(B)=\mu(A)+\mu(B\backslash A)$. Therefore, $\mu(A)\leq \mu(B)$.
---
> [!lemma] Theorem 2
> An additive function $\mu$ on $\mathcal{A}$ is $\sigma$-subadditive if and only if it is also $\sigma$-additive.

>[!proof]-
>(=>): Let $(A_{n})_{n}\subseteq \mathcal{A}$ be a disjoint sequence, i.e. $A_{i}\cap A_{j}=\varnothing$ for $i \neq j$ s.t. $\bigcup_{n=1}^{\infty}A_{n}\in \mathcal{A}$. Then, from the subadditivity, we have: $$\mu \left( \bigcup_{n=1}^{\infty}A_{n} \right) \leq \sum_{n=1}^{\infty}\mu(A_{n})$$
>For every $m \geq 1$, we also have $\bigcup_{n=1}^{m}A_{n}\subseteq \bigcup_{n=1}^{\infty}A_{n}$.  Therefore, $$\mu \left( \bigcup_{n=1}^{\infty}A_{n} \right) \geq \mu \left( \bigcup_{n=1}^{m}A_{n} \right)=\sum_{n=1}^{m}\mu(A_{n})\xrightarrow{m \to \infty}\sum_{n=1}^{\infty}\mu(A_{n})$$
>Therefore, $\mu$ is also $\sigma$-additive.
>
>(<=): Let $(A_{n})_{n}\subseteq \mathcal{A}$ be a sequence s.t. $\bigcup_{n=1}^{\infty}A_{n}\in \mathcal{A}$. We can create a disjoint sequence out of it, i.e. we define $(B_{n})_{n}$ where: $B_{n}:= A_{n}\backslash \bigcup_{i=1}^{n-1}A_{i}$. Then, $\bigcup_{n=1}^{\infty}A_{n}=\bigcup_{n=1}^{\infty}B_{n}$ and therefore,
> $$\mu \left( \bigcup_{n=1}^{\infty}A_{n} \right) =\mu \left( \bigcup_{n=1}^{\infty}B_{n} \right) =\sum_{n=1}^{\infty}\mu(B_{n})\leq \sum_{n=1}^{\infty }\mu(A_{n})$$
> Therefore, $\mu$ is $\sigma$-subadditive.
---
##### Examples
1. For $X=\mathbb{N}$ and the algebra $\mathcal{A}:=\{  A\in \mathcal{P}(X):A \text{ or } A^c\text{ is finite} \}$, the function $\mu:\mathcal{A} \to[0,+\infty]$ defined as: $$\mu(A)=\begin{cases}|A|&A\text{ is finite}\\ \infty &A^c\text{ is finite}\end{cases}$$is $\sigma$-additive.
2. For the same algebra as above, the function $\mu:\mathcal{A} \to[0,+\infty]$ defined as: $$\mu(A)=\begin{cases}\sum_{n\in A} \frac{1}{2^n}&A\text{ is finite}\\ \infty &A^c\text{ is finite}\end{cases}$$is is additive but not $\sigma$-additive. Consider $(\{ n \})_{n}$. Then, $$\mu\left(\bigcup_{n=0}^{\infty}\{ n \}\right)=\mu(\mathbb{N})=\infty\neq 2=\sum_{n=0}^{\infty} \frac{1}{2^n}$$
---