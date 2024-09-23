#Definition #Algorithms 

> [!definition]
> Let $\mathcal{S}:=[n]$ with a size function $s:\mathcal{S}\to \mathbb{Z}_{\geq0}$ and a profit function $p:\mathcal{S}\to \mathbb{Z}_{\geq 0}$. Given a budget $B\in \mathbb{Z}$, the **Knapsack problem** $I:=(\mathcal{S},s,p,B)$ aims to find: $$\text{OPT}(I)\in \underset{ J\subseteq[n], \sum_{i\in J}^{}s_{i}\leq B }{ \arg\max }\sum_{i\in J}^{}p_{i}$$

^fca662

- **Remark**: As any $i\in \mathcal{S}$ with $s_{i}>B$ cannot be chosen, wlog we assume that $s_{i}\leq B$.  
- **Remark**: It is clear that $\max_{i}p_{i}\leq p(\text{OPT}(I))\leq n\cdot \max_{i}p_{i}$. 
---
##### Properties
> [!lemma] Theorem 1 (Dynamic Programming)
> In the DP algorithm, let $M\in \mathbb{R}^{n+1,np_{\max}+1}$. Then, let $M[i,p]$ denote the smallest size of subset form $[i]$ s.t. the total profit is at least $p$. Therefore,$$M[i,p]:=\min\{ M[i-1,p],s_{i}+M[i-1,p-p_{i}] \}$$solves the Knapsack problem in $\mathcal{O}(n^2p_{\max})$.
> 

^13ab4a

---