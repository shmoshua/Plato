#Definition 

> [!definition]
> Let $R\in \{ 0,1 \}^N$ a random subset with $\mathbb{P}(R_{i}=1)=p_{i}$ independently. Further, let $S_{1},\dots,S_{k}\in \{ 0,1 \}^N$.
> 1. $A_{i}$ denotes the event that $S_{i}\subseteq R$, i.e. $S_{i}\leq R$.
> 2. $X:=\sum_{i\in[k]}^{}\mathbb{1}_{A_{i}}$
> 3. $\mu:=\mathbb{E}\left[ \sum_{i\in[k]}^{}\mathbb{1}_{A_{i}} \right]=\sum_{i\in[k]}^{}\mathbb{P}(S_{i}\subseteq R)$
> 4. $\Delta:=\sum_{(i,j):i \sim j}^{}\mathbb{P}(A_{i}\cap A_{j})=\sum_{(i,j):i \sim j}^{}\mathbb{P}(S_{i}\cup S_{j}\subseteq R)$ where $i\sim j$ iff $i\neq j$ and $S_{i}\cap S_{j}\neq \varnothing$. 
---
##### Properties
> [!lemma] Theorem 1 (Janson Inequality I)
> We have that:
> 1. $\mathbb{P}(X=0)\leq \exp \left( -\mu+\frac{\Delta}{2} \right)$

> [!proof]+
> We have that: $$\begin{align}\mathbb{P}(X=0)&=\mathbb{P}\left( \bigcap_{i\in[k]}^{}A_{i}^c \right)=\mathbb{P}(A_{1}^c)\mathbb{P}(A^c_{2}|A_{1}^c)\dots \mathbb{P}(A_{k}^c|A_{1}^c,\dots,A_{k-1}^c)\end{align}$$