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
> [!lemma] Theorem 3
>    ```pseudo
>    \begin{algorithm} \caption{Algo($\mathcal{S},s,p,B$)} 
>    \begin{algorithmic}
>    \State $S\gets \empty$
>    \State Discard all elements larger than $B$ in $\mathcal S$. 
>    \State Sort $\mathcal{S}$ by $\frac{p}{s}$ in decreasing order, define them as $a_{1},\dots,a_{n}$.
>    \State $k\gets \min\left\{ i\in[n]:s(\{ a_{1},\dots,a_{i} \})>B \right\}$ or if doesn't exist, return $\mathcal{S}$.
>    \If{$p(\{ a_{1},\dots,a_{k-1} \})>p_{a_{k}}$}
>    \Return $\{ a_{1},\dots,a_{k-1} \}$
>    \Else \Return $\{ a_{k} \}$
>    \EndIf
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    gives a $2$-approximation for the Knapsack problem.

> [!proof]+
> Let $S$ be the output of the algorithm and $S_{\text{OPT}}$ the optimal set. if $S=\mathcal{S}$, then $p(S)=p(S_{\text{OPT}})$ and we are done. Assume otherwise. 
> 1. **Claim 1: for $B':=s(a_{1},\dots,a_{k})$ the optimal solution $p(S'_{\text{OPT}})=p(a_{1},\dots,a_{k})$**.
>    The inequality $p(S'_{\text{OPT}})\geq p(a_{1},\dots,a_{k})$ holds trivially. For the other inequality, assume it is not true, i.e. $p(S'_{\text{OPT}})>p(a_{1},\dots,a_{k})$. Now, for every item $u\in S'_{\text{OPT}}$, we can replace it with $s(u)$ items of size 1 and price $p(u) / s(u)$. Let $x_{1},\dots,x_{\ell}$ for $\ell\leq B'$ be the replaced items in decreasing order of price. Similarly, we apply this on $a_{1},\dots,a_{k}$ and get $y_{1},\dots,y_{B'}$. As $p(S'_{\text{OPT}})>p(a_{1},\dots,a_{k})$, there exists $i$ s.t. $p(x_{i})>p(y_{i})$. Modulo reindexing this implying there exists $a_{\ell}\in S'_{\text{OPT}}$ with $k\leq \ell$ s.t. $p(a_{\ell}) / s(a_{\ell})> p(a_{k}) / s(a_{k})$. This is a contradiction.
>    
> 1. **Claim 2: $p(S_{\text{OPT}})\leq p(a_{1},\dots,a_{k})$**
>    This holds from the fact that $p(S_{\text{OPT}})\leq p(S_{\text{OPT}}')$ trivially, as otherwise $S'_{\text{OPT}}$ would not be an optimum. 
> 
> Therefore, we have that: $$p(S_{\text{OPT}})\leq p(a_{1},\dots,a_{k-1})+p(a_{k})\leq 2p(S)$$
---
