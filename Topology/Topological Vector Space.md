#Definition #Topology 

> [!definition]
> A ***topological vector space*** is a $\mathbb{K}$-vector space $V$ endowed with a [[Topological Space|topology]] s.t. 
> 1. $\mathbb{K}\times V\to V,(\lambda,v)\mapsto\lambda v$ is continuous and
> 2. $V\times V\to V,(x,y)\mapsto x+y$ is continuous.
> 
> For $\lambda\in \mathbb{K}$, we define the ***multiplication map***: $$\begin{array}{cccc} {M_{\lambda}:}&{V}&\to&{V}\\&{v} &\mapsto & {\lambda v} \end{array}{}$$and for $v\in V$, we define the ***translation map***: $$\begin{array}{cccc} {L_{v}:}&{V}&\to&{V}\\&{w} &\mapsto & {v+w} \end{array}{}$$
---
##### Properties
> [!lemma] Lemma 1
> For all $\lambda\neq 0$ and all $v\in V$, $M_{\lambda}$ and $L_{v}$ are [[homeomorphism|homeomorphisms]]. 

> [!proof]-
> We know that $M_{\lambda}$ is continuous with a continuous inverse $M_{\lambda ^{-1}}$, and $L_{v}$ is continuous with a continuous inverse $L_{-v}$.
---

