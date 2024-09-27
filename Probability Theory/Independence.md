#Definition #ProbabilityTheory 

> [!definition]
> Let $(\Omega,\mathcal{A},\mathbb{P})$ be a [[probability space]]. 
> 1. Events $A_{1},\dots,A_{n}\in \mathcal{A}$ are ***independent*** if $$\mathbb{P}\left( \bigcap_{i\in J}^{}A_{i} \right)=\prod_{i\in J}^{}\mathbb{P}(A_{i}),\quad \forall J\subseteq[n]$$
> 2. Sub-[[Sigma Algebra|$\sigma$-algebras]] $\mathcal{B_{1},\dots,B}_{n}\subseteq \mathcal{A}$ are ***independent*** if: $$\mathbb{P}(A_{1}\cap A_{2}\cap\dots \cap A_{n})=\prod_{i\in[n]}^{}\mathbb{P}(A_{i}),\quad \forall A_{i}\in \mathcal{B}_{i}$$
> 3. [[Random Variable|Random variables]] $X_{1},..,X_{n}$ taking values in $(E_{i},\mathcal{E}_{I})$ are ***independent*** if $\sigma(X_1),\dots,\sigma(X_{n})$ are independent. 
- **Remark**: Pairwise independence is not enough to guarantee independence.
---
##### Properties
> [!lemma] Proposition 1
> For $A_{1},\dots,A_{n}\in\mathcal{A}$ events, the following are equivalent.
> 1. $A_{1},\dots,A_{n}$ are independent.
> 2. $\mathbb{P}(B_{1}\cap\dots \cap B_{n})=\prod_{i=1}^{n}\mathbb{P}(B_{i})$ for $B_{i}\in \sigma(A_{i})=\{ \varnothing,A_{i},A_{i}^c,\Omega \}$, i.e. $\sigma(A_{i})$ are independent.

> [!proof]-
> We have:
> 1. (1=>2): This holds from the fact that if $A_{1},\dots,A_{n}$ are independent, then $A_{1}^c,A_{2},\dots,A_{n}$ are independent. Indeed, $$\begin{align}\mathbb{P}(A_{1}^c\cap A_{2}\cap\dots \cap A_{n})&=\mathbb{P}(A_{2}\cap\dots \cap A_{n})-\mathbb{P}(A_{1}\cap A_{2}\cap\dots \cap A_{n})\\&=(1-\mathbb{P}(A_{1}))\prod_{i=2}^{n}\mathbb{P}(A_{2})\\&=\mathbb{P}(A_{1}^c)\prod_{i=2}^{n}\mathbb{P}(A_{2})\end{align}$$
> 2. (2=>1): obvious.
---
##### Examples
##### Non-Examples
> [!h] Non-Example
> Consider two coin throws of a fair coin and the three events:
> 1. $A_{1}:=$ getting heads in the first trial.
> 2. $A_{2}:=$ getting heads in the second trial.
> 3. $A_{3}:=$ getting the same outcome in both trials.
> 
> Then, 
> 1. $A_{1},A_{2},A_{3}$ are pairwisely independent.
> 2. $A_{1},A_{2},A_{3}$ are not independent as $\mathbb{P}(A_{1}\cap A_{2}\cap A_{3})=\frac{1}{4}\neq \frac{1}{8}=\mathbb{P}(A_{1})\mathbb{P}(A_{2})\mathbb{P}(A_{3})$.
---