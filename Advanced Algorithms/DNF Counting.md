#Definition #Algorithms 

> [!definition]
> Let $X=\bigvee_{i=1}^m\bigwedge_{j} F_{j}$ be a formula in [[Disjunctive Normal Form|disjunctive normal form (DNF)]]. 
> 1. The ***DNF counting problem*** aims to find the number $N_{\text{OPT}}$ of satisfying assignments.
- **Remark**: Sampling with random assignments depend heavily on the number of satisfying assignment (e.g. if $N_{\text{OPT}} / 2^n$ is very small) 
---
##### Properties
> [!lemma] Theorem 1 (Sampling)
> Let $s:m$
>    ```pseudo
>    \begin{algorithm} \caption{FirstFit($\mathcal{S},s$)} 
>    \begin{algorithmic}
>    \State Sample a 1-entry in a matrix uniformly randomly. (Pick a row and pick randomly)
>    \State Check if it is the top most entry by bruteforcing $O(m)$.
>    \State Repeat for $O\left( m\cdot \frac{\log(1 / \delta)}{\varepsilon^{2}} \right)$ rounds
>    \end{algorithmic}
>    \end{algorithm}
>    ```
> We have that 
> 1. $\text{FirstFit}$ is a $2$-[[approximation algorithm]].

> [!proof]+
> We have that: $$\mathbb{P}\left(  \left| fM-N \right| >\varepsilon \cdot N\right) =\mathbb{P}\left( \left| f-\frac{N}{M} \right| >\varepsilon \cdot \frac{N}{M} \right)\leq \frac{1}{\delta}$$Then, $$\begin{align}\mathbb{P}(\text{Entry is in }i\text{-th row}|\text{Entry is }1)=\mathbb{P}(\text{1-entry is in }i\text{-th row})=\frac{2^{n-\left| C_{i} \right| }}{M}\end{align}$$