#Definition #ProbabilityTheory 

> [!definition]
> Let $X:\Omega\to \mathbb{R}$ be a [[random variable]] in $(\Omega,\mathcal{A},\mathbb{P})$. A ***regular conditional probability*** for $\mathbb{P}$ given $X$ is a function: $$\mathcal{\mathcal{A}}\times \mathbb{R}\to [0,+\infty],\quad (A,x)\mapsto \mathbb{P}^X(A|x)$$such that:
> 1. $A\mapsto \mathbb{P}^X(A|x)$ is a probability measure on $(\Omega,\mathcal{A})$ for all $x\in \mathbb{R}$. 
> 2. $x\mapsto \mathbb{P}^X(A|x)$ is $\mathcal{B}_{\mathbb{R}}$-measurable for all $A\in \mathcal{A}$.
> 3. for any $A\in \mathcal{A}$ and $B\in \mathcal{B}_{\mathbb{R}}$, we have that: $$\int_B\mathbb{P}^X(A|x)  \, d\mathbb{P}_{X}(x)=\mathbb{P}(A\cap \{ X\in B \}) $$
- **Remark**: $\mathbb{P}^X$ is unique in the sense that $\mathbb{P}^X(\cdot|x)=\tilde{\mathbb{P}}^X(\cdot|x)$ for $\mathbb{P}_{X}$-almost every $x$.
- **Related definition**: For another real random variable $Y$, the regular conditional distribution of $Y$ given $X$ is given by: $\mathbb{P}_{X|Y}(B|x):=\mathbb{P}^X(Y\in B|x)$
---
##### Properties
> [!lemma] Proposition 1
> For any $A\in \mathcal{A}$, we have that: $$\mathbb{E}[\mathbb{1}_{A}|X]=\mathbb{P}^X(A|X)$$

> [!proof]-
>We have for any $B\in \mathcal{B}_{\mathbb{R}}$,  $$\begin{align}\mathbb{E}[\mathbb{P}^X(A|X)\cdot \mathbb{1}_{X ^{-1}(B)}]&=\int_{B}\mathbb{P}^X(A|x)  \, d\mathbb{P}_{X}(x) \\&=\mathbb{P}(A\cap X ^{-1}(B))\\&=\mathbb{E}[\mathbb{1}_{A}\cdot \mathbb{1}_{X ^{-1}(B)}]\\&=\mathbb{E}[\mathbb{E}[\mathbb{1}_{A}|X]\cdot \mathbb{1}_{X ^{-1}(B)}]\end{align}$$Therefore, by uniqueness of conditional expectation, we have the statement.
---
> [!lemma] Proposition 2
> For $A,B\in \mathcal{B}_{\mathbb{R}}$, we have: $$\int_{A}^{} \mathbb{P}_{Y|X}(B|x) \, d\mathbb{P}_{X}(x)=\mathbb{P}(X\in A,Y\in B) $$

> [!proof]-
> We have:
> $$ \begin{align}\int_{A}^{} \mathbb{P}_{Y|X}(B|x) \, d\mathbb{P}_{X}(x)&=\int_{A}^{} \mathbb{P}^X(Y\in B|x) \, d\mathbb{P}_{X}(x)\\&=\mathbb{P}(X\in A,Y\in B)\end{align}$$
---
