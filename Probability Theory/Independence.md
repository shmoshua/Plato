#Definition #ProbabilityTheory 

> [!definition]
> Let $(\Omega,\mathcal{A},\mathbb{P})$ be a [[probability space]]. 
> 1. Events $A_{1},\dots,A_{n}\in \mathcal{A}$ are ***independent*** if $$\mathbb{P}\left( \bigcap_{i\in J}^{}A_{i} \right)=\prod_{i\in J}^{}\mathbb{P}(A_{i}),\quad \forall J\subseteq[n]$$
> 2. Sub-[[Sigma Algebra|$\sigma$-algebras]] $\mathcal{B_{1},\dots,B}_{n}\subseteq \mathcal{A}$ are ***independent*** if: $$\mathbb{P}(A_{1}\cap A_{2}\cap\dots \cap A_{n})=\prod_{i\in[n]}^{}\mathbb{P}(A_{i}),\quad \forall A_{i}\in \mathcal{B}_{i}$$
> 3. [[Random Variable|Random variables]] $X_{1},..,X_{n}$ taking values in $(E_{i},\mathcal{E}_{i})$ are ***independent*** if $\sigma(X_1),\dots,\sigma(X_{n})$ are independent, i.e. $$\mathbb{P}(X_{1}\in F_{1},\dots,X_{n}\in F_{n})=\mathbb{P}(X_{1}\in F_{1})\dots \mathbb{P}(X_{n}\in F_{n}),\quad \forall F_{i}\in \mathcal{E}_{i}$$
- **Remark**: Pairwise independence is not enough to guarantee independence.
- **Remark**: if $\mathcal{B}_{1},\dots,\mathcal{B}_{n}\subseteq \mathcal{A}$ are independent, $X_{1},\dots,X_{n}$ are independent if $X_{i}$ is $\mathcal{B}_{i}$-measurable.
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
> [!lemma] Theorem 2
> Let $X_{1},\dots,X_{n}$ be random variables taking values in $(E_{1},\mathcal{E}_{1}),\dots,(E_{n},\mathcal{E}_{n})$. 
> 1. $X_{1},\dots,X_{n}$ are independent if and only if $\mathbb{P}_{(X_{1},\dots,X_{n})}=\mathbb{P}_{X_{1}}\otimes\dots \otimes \mathbb{P}_{X_{n}}$.
> 2. If $X_{1},\dots,X_{n}$ are independent, $\mathbb{E}\left[ \prod_{i=1}^{n}f_{i}(X_{i}) \right]=\prod_{i=1}^{n}\mathbb{E}[f_{i}(X_{i})]$ where $f_{i}$ is a non-negative measurable function on $(E_{i},\mathcal{E}_{i})$

> [!proof]-
> We have:
> 1. Let $F_{i}\in \mathcal{E}_{i}$. Then, $$\mathbb{P}_{(X_{1},\dots,X_{n})}(F_{1}\times\dots \times F_{n})=\mathbb{P}(X_{1}\in F_{1},\dots,X_{n}\in F_{n})$$On ther other hand, $$\mathbb{P}_{X_{1}}\otimes \dots \otimes \mathbb{P}_{X_{n}}(F_{1}\times\dots \times F_{n})=\prod_{i=1}^{n}\mathbb{P}_{X_{i}}(F_{i})=\prod_{i=1}^{n}\mathbb{P}(X_{i}\in F_{i})$$This proves the statement as the product measure is characterized by its values on the "box-sets".
> 2. Using Fubini, we have: $$\begin{align}\mathbb{E}\left[ \prod_{i=1}^{n}f_{i}(X_{i}) \right] &=\int_{E_{1}\times\dots \times E_{n}}f_{1}(x_{1})\dots f_{n}(x_{n}) \, d\mathbb{P}_{X_{1}}(x_{1})\dots d\mathbb{P}_{X_{n}}(x_{n}) \\&=\prod_{i=1}^{n}\int_{E_{i}}f_{i}(x_{i}) \, d\mathbb{P}_{X_{i}}(x_{i})\\&=\prod_{i=1}^{n}\mathbb{E}[f_{i}(X_{i})] \end{align}$$
- **Remark**: We can extend $f_{i}$ to real- and complex functions, if $\mathbb{E}[\left| f_{i}(X_{i}) \right|]<+\infty$ for all $i$.
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