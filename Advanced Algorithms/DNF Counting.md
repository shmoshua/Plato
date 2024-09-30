#Definition #Algorithms 

> [!definition]
> Let $X=\bigvee_{i=1}^m\bigwedge_{j} F_{j}$ be a formula in [[Disjunctive Normal Form|disjunctive normal form (DNF)]]. 
> 1. The ***DNF counting problem*** aims to find the number $N_{\text{OPT}}$ of satisfying assignments.
- **Remark**: Sampling with random assignments depend heavily on the number of satisfying assignment (e.g. if $N_{\text{OPT}} / 2^n$ is very small) 
---
##### Properties
> [!lemma] Theorem 1 (Sampling)
> Let $X=\bigvee_{i=1}^mC_{i}$ and let $s:[m]\times \{ 0,1 \}^n\to \{ 0,1 \}$ denote the satisfiability matrix, i.e. $$s(i,j)=1\iff C_{i}\text{ is satisfiable with assignment }j$$Then, 
>    ```pseudo
>    \begin{algorithm} \caption{Sampling($I$)} 
>    \begin{algorithmic}
>    \For {$t\in[k]$}
>    \State Sample $i\gets [m]$ with probability $2^{n-\left| C_{i} \right|} / M$ for $i$.
>    \State Sample a satisfying assignment for $C_{i}$ uniformly at random. 
>    \For{$j\in[i-1]$}
>    \State Check if 
> \EndFor
> \EndFor
>    
>    \State Check if it is the top most entry by bruteforcing $O(m)$.
>    \State Repeat for $O\left( m\cdot \frac{\log(1 / \delta)}{\varepsilon^{2}} \right)$ rounds
>    \end{algorithmic}
>    \end{algorithm}
>    ```
> We have that 
> 1. $\text{FirstFit}$ is a $2$-[[approximation algorithm]].

> [!proof]-
> Uniformly random sampling.
> 
> We have that: $$\mathbb{P}\left(  \left| fM-N \right| >\varepsilon \cdot N\right) =\mathbb{P}\left( \left| f-\frac{N}{M} \right| >\varepsilon \cdot \frac{N}{M} \right)\leq \delta$$Then, $$\begin{align}\mathbb{P}(\text{Entry is in }i\text{-th row}|\text{Entry is }1)=\mathbb{P}(\text{1-entry is in }i\text{-th row})=\frac{2^{n-\left| C_{i} \right| }}{M}\end{align}$$
---
##### Examples
> [!h] Example 1
> Let $G$ be a connected graph and $E'\subseteq E(G)$ where: $$\mathbb{P}(e\in E')=p, \quad \forall e\in E$$
> We would like to compute $P:=\mathbb{P}(G\backslash E'\text{ is disconnected})$.
> 1. $G \backslash E'$ is disconnected if and only if $E'$ contains a [[Cut (Graph)|cut set]].
> 2. $G \backslash E'$ is disconnected if and only if: $$\bigvee_{\text{cut set }C}\bigwedge_{e\in C}\neg e\text{ is satisfied}$$
> 3. If $p^s\geq \frac{1}{n^4}$, then we can use $O(n^4 \log(1 / \delta) / \varepsilon^{2})$ samples to approximate it. 
> 4. if $p^s\leq \frac{1}{n^4}$, we ignore the cuts of size $4s$. 
> 	$$\mathbb{P}(\exists \text{cut of size }\geq 4s\text{ is in }E')\leq \sum_{i=4s}^{\infty}\#\text{cuts of size }i\cdot  p^i=\sum_{i=4s}^{\infty}(n^{2 / s}\cdot  p)^i\leq \sum_{i=4s}^{\infty}p^{i/2}=(p^{1/2})^{4s}\cdot \Theta(1)\leq p ^{2s}\leq p\cdot \frac{1}{n^2}$$

> [!proof]+
> 