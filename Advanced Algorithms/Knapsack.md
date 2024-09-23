#Definition #Algorithms 

> [!definition]
> Let $\mathcal{S}:=[n]$ with a size function $s:\mathcal{S}\to \mathbb{Z}_{\geq0}$ and a profit function $p:\mathcal{S}\to \mathbb{Z}_{\geq 0}$. Given a budget $B\in \mathbb{Z}$, the **Knapsack problem** $I:=(\mathcal{S},s,p,B)$ aims to find: $$\text{OPT}(I)\in \underset{ J\subseteq \mathcal{S}, \sum_{i\in J}^{}s_{i}\leq B }{ \arg\max }\sum_{i\in J}^{}p_{i}$$

^fca662
- **Related notation**: We extend $s:\mathcal{P}(\mathcal{S})\to \mathbb{Z}_{\geq 0},\mathcal{U}\mapsto \sum_{i\in \mathcal{U}}^{}s_{i}$. Analogously with $p$. 
- **Remark**: As any $i\in \mathcal{S}$ with $s_{i}>B$ cannot be chosen, wlog we assume that $s_{i}\leq B$.  
- **Remark**: It is clear that $\max_{i}p_{i}\leq p(\text{OPT}(I))\leq n\cdot \max_{i}p_{i}$. 
---
##### Properties
> [!lemma] Theorem 1 (Dynamic Programming)
> In the DP algorithm, let $M\in \mathbb{R}^{n+1,np_{\max}+1}$. Then, let $M[i,p]$ denote the smallest size of subset form $[i]$ s.t. the total profit is at least $p$. Therefore,$$M[i,p]:=\min\{ M[i-1,p],s_{i}+M[i-1,p-p_{i}] \}$$solves the Knapsack problem in $\mathcal{O}(n^2p_{\max})$, i.e. a pseudo-polynomial algorithm.
> 

^13ab4a

---
> [!lemma] Theorem 2 (Rounding)
> The rounding algorithm works as follows:
> 1. Let $k:=\max(\varepsilon \cdot p_{\max} / n,1)$ and round down all profits to multiples of $k$, i.e. $\tilde{p}_{i}:=k \left\lfloor p_{i} / k\right\rfloor$.
> is a $(1+\varepsilon)$-[[approximation algorithm]] in runtime $O(n^3 / \varepsilon)$.

^532344

> [!proof]-
> Let $\text{OPT}(I')$ be the new setting. Then, $p(\text{OPT}(I'))\geq p'(\text{OPT}(I'))\geq p'(J)$ for any feasible $J\subseteq \mathcal{S}$, i.e. $s(J)\leq B$. As $\text{OPT}(I)$ is a feasible solution, we have that: $$p(\text{OPT}(I'))\geq p'(\text{OPT}(I))= \sum_{i\in \text{OPT}(I)}^{}p_{i}'\geq \sum_{i\in \text{OPT}(I)}^{}(p_{i}-k)\geq p(\text{OPT}(I))-k\cdot n$$Then, $p(\text{OPT}(I'))\geq p(\text{OPT}(I))-\varepsilon \cdot p_{\max}=(1-\varepsilon)p(\text{OPT}(I))$

^c811f3

---
