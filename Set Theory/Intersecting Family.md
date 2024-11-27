#Definition #SetTheory

> [!definition]
> Let $\mathcal{F}$ be a family of subsets of $[n]$. $\mathcal{F}$ is an ***intersecting family*** if 
> 1. for all $F,F'\in \mathcal{F}$, $F\cap F'\neq \varnothing$.

---
##### Properties
> [!lemma] Theorem 1
> We have that:
> 1. $\max_{\mathcal{F}\subseteq 2^{[n]}\text{ intersecting}}|\mathcal{F}|=2^{n-1}$
---
> [!lemma] Theorem 2
> We have that:
> 1. $\text{max}\{ \mathcal{F}:\mathcal{F}\text{ intersecting and }\forall F,F'\in \mathcal{F}:F\cup F'\neq[n] \}=2^{n-2}$

> [!proof]-
> Let $\Omega:=2^{[n]}$ with uniform probability measure. Then, $\mathbb{P}(\mathcal{F})=\left| \mathcal{F} \right| / 2^n$. For $\mathcal{F}\subseteq \Omega$, we define:
> 1. $\mathcal{F}_{1}:=\{ X\subseteq [n]: \exists F\in \mathcal{F}.X \supseteq F \}\supseteq \mathcal{F}$
> 2. $\mathcal{F}_{2}:=\{ X\subseteq [n]: \exists F\in \mathcal{F}.X \subseteq F \}\supseteq \mathcal{F}$
>    
>  Then, we identify that $\mathcal{F}_{1}$ is [[Increasing and Decreasing Property|increasing]], i.e. for any $X\subseteq Y$, if $X\in \mathcal{F}_{1}$, then there exists $F\in \mathcal{F}$ with $F\subseteq X\subseteq Y$ and hence $Y\in \mathcal{F}_{1}$. Similarly, $\mathcal{F}_{2}$ is decreasing. 
>  
>  Hence, $$\mathbb{P}(\mathcal{F})\leq \mathbb{P}(\mathcal{F}_{1}\cap \mathcal{F}_{2})\leq \mathbb{P}(\mathcal{F}_{1})\mathbb{P}(\mathcal{F}_{2})\leq \frac{1}{2}\cdot \frac{1}{2}=\frac{1}{4}$$
---
