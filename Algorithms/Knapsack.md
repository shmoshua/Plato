#Definition #Algorithms 

> [!definition]
> Let $\mathcal{S}:=[n]$ with a size function $s:\mathcal{S}\to \mathbb{Z}_{\geq0}$ and a profit function $p:\mathcal{S}\to \mathbb{Z}_{\geq 0}$. Given a budget $B\in \mathbb{Z}$, the **Knapsack problem** $I:=(\mathcal{S},s,p,B)$ aims to find: $$\text{OPT}(I)\in \underset{ J\subseteq \mathcal{S}, \sum_{i\in J}^{}s_{i}\leq B }{ \arg\max }\sum_{i\in J}^{}p_{i}$$

^fca662

- **Related notation**: In ILP it can be written as: 
  $$\begin{array}{rl}\text{max}&\sum_{i\in [n]}^{}p_{i}x_{i}\\\text{subject to}&\sum_{i\in[n]}^{} s_{i}x_{i}\leq B\\&x_{i}\in \{ 0,1 \}&\forall i\in[n]\end{array}$$
- **Related notation**: We extend $s:\mathcal{P}(\mathcal{S})\to \mathbb{Z}_{\geq 0},\mathcal{U}\mapsto \sum_{i\in \mathcal{U}}^{}s_{i}$. Analogously with $p$. 
- **Remark**: As any $i\in \mathcal{S}$ with $s_{i}>B$ cannot be chosen, wlog we assume that $s_{i}\leq B$.  
- **Remark**: It is clear that $\max_{i}p_{i}\leq p(\text{OPT}(I))\leq n\cdot \max_{i}p_{i}$. 
---
##### Properties
> [!lemma] Theorem 1 (Dynamic Programming)
> We define the DP as $\text{DP}[i,p]:=\min_{{J\subseteq[i]},p(J)\geq p}s(J)$ for all $i\in[n]$ and $p\in[np_{\max}]$.  Then, $$\text{DP}[i,p]=\min\{ \text{DP}[i-1,p],\text{DP}[i-1,p-p_{i}]+s_{i} \}$$solves the Knapsack problem in $O(n^2p_{\max})$.

^13ab4a

> [!proof]-
> To show correctness, let $J\in\arg\min_{{J\subseteq[i]},p(J)\geq p}s(J)$. 
> 1. If $i\notin J$ then $J\in\arg\min_{{J\subseteq[i-1]},p(J)\geq p}s(J)$. Otherwise, let $J'\subseteq[i-1]$ with $p(J')\geq p$ with $s(J')<s(J)$. Then, it is a contradiction to the definition of $J$. Hence, $\text{DP}[i,p]=s(J)=\text{DP}[i-1,p]$.
> 2. If $i\in J$ then $J \backslash\{ i \}\in \arg\min_{{J\subseteq[i-1]},p(J)\geq p-p_{i}}s(J)$. Therefore, $\text{DP}[i,p]=s(J\backslash \{ i \})+s_{i}=\text{DP}[i-1,p-p_{i}]+s_{i}$.
> 
> For the runtime, as there are $O(n^{2}p_{\max})$ entries with each entry computable in $O(1)$ time complexity, we have the statement.

^f19e50

---
> [!lemma] Theorem 2 (FPTAS Rounding)
> Consider the algorithm: 
> ```pseudo
> \begin{algorithm}\caption{Rounding($I,\varepsilon$)}
> \begin{algorithmic}
> \State $k\gets \max\{\left\lfloor\varepsilon p_{\max}/n\right\rfloor,1\}$
> \State $p_{i}'\gets k\left\lfloor p_{i }/k\right\rfloor$ and call the new instance $I'$.
> \Return $\text{DP}(I')$
> \end{algorithmic}
> \end{algorithm}
> ```
> Then, $\text{Rounding}$ is a [[FPTAS]].

^532344

> [!proof]-
> We have that: 
> 1. If $\varepsilon p_{\max} / n\leq 1$, then $p_{max}\leq n / \varepsilon$ and by Theorem 1, we have a $O(n^3 / \varepsilon)$ solution. 
> 2. If $\varepsilon p_{max} / n>1$, then $k=\left\lfloor \varepsilon p_{\max} / n\right\rfloor$ and $p(\text{OPT}(I'))\geq p'(\text{OPT}(I'))\geq p'(J)$ for any feasible $J\subseteq[n]$, i.e. $s(J)\leq B$. As $\text{OPT}(I)$ is a feasible solution, we have that: $$p(\text{OPT}(I'))\geq p'(\text{OPT}(I))= \sum_{i\in \text{OPT}(I)}^{}p_{i}'\geq \sum_{i\in \text{OPT}(I)}^{}(p_{i}-k)\geq p(\text{OPT}(I))-k\cdot n$$Then, $p(\text{OPT}(I'))\geq p(\text{OPT}(I))-\varepsilon \cdot p_{\max}=(1-\varepsilon)p(\text{OPT}(I))$. 
>    
>    Further, the runtime is given as $O(n^{2}\cdot p_{\max} / k)=O(n^3 / \varepsilon)$.

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
>    gives a $\frac{1}{2}$-approximation for the Knapsack problem.

^d138a3

> [!proof]-
> Let $S$ be the output of the algorithm and $S_{\text{OPT}}$ the optimal set. if $S=\mathcal{S}$, then $p(S)=p(S_{\text{OPT}})$ and we are done. Assume otherwise. 
> 1. **Claim 1: for $B':=s(a_{1},\dots,a_{k})$ the optimal solution $p(S'_{\text{OPT}})=p(a_{1},\dots,a_{k})$**.
>    The inequality $p(S'_{\text{OPT}})\geq p(a_{1},\dots,a_{k})$ holds trivially. For the other inequality, assume it is not true, i.e. $p(S'_{\text{OPT}})>p(a_{1},\dots,a_{k})$. Now, for every item $u\in S'_{\text{OPT}}$, we can replace it with $s(u)$ items of size 1 and price $p(u) / s(u)$. Let $x_{1},\dots,x_{\ell}$ for $\ell\leq B'$ be the replaced items in decreasing order of price. Similarly, we apply this on $a_{1},\dots,a_{k}$ and get $y_{1},\dots,y_{B'}$. As $p(S'_{\text{OPT}})>p(a_{1},\dots,a_{k})$, there exists $i$ s.t. $p(x_{i})>p(y_{i})$. Modulo reindexing this implying there exists $a_{\ell}\in S'_{\text{OPT}}$ with $k\leq \ell$ s.t. $p(a_{\ell}) / s(a_{\ell})> p(a_{k}) / s(a_{k})$. This is a contradiction.
>    
> 1. **Claim 2: $p(S_{\text{OPT}})\leq p(a_{1},\dots,a_{k})$**
>    This holds from the fact that $p(S_{\text{OPT}})\leq p(S_{\text{OPT}}')$ trivially, as otherwise $S'_{\text{OPT}}$ would not be an optimum. 
> 
> Therefore, we have that: $$p(S_{\text{OPT}})\leq p(a_{1},\dots,a_{k-1})+p(a_{k})\leq 2p(S)$$

^013fe1

---
