#Definition #Algorithms 

> [!definition]
> For a universe $U$, let $S\subseteq U$ be a cache s.t. $\left| S \right|\leq k$. 
> 1. The ***paging problem*** aims to find an optimal algorithm s.t. for a sequence $(u_{n})_{n}\subseteq U$ and $S_{0}=\varnothing$, 
> 	$$(S^\text{OPT}_{n})_{n}\in \underset{ (S_{n})_{n}, S_{n}\subseteq U,\left| S_{n} \right| \leq k, u_{n}\in S_{n} }{ \arg\min }\sum_{n=1}^{\infty}1-\chi_{S_{n-1}}(u_{n})$$
- **Related Definition**: A paging algorithm is called ***conservative*** if for any $i<j$ with $\left| \{ u_{i},\dots,u_{j} \} \right|\leq k$,  $\text{cost}_{\mathcal{A}}(\{ u_{i},\dots, u_{j} \})\leq k$.
---
##### Properties
> [!lemma] Theorem 1
> Every conservative paging algorithm is $k$-competitive. 