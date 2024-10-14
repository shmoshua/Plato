#Definition #Algorithms 

> [!definition]
> For a universe $U$, let $S\subseteq U$ be a cache s.t. $\left| S \right|\leq k$. 
> 1. The ***paging problem*** aims to find an optimal algorithm s.t. for a finite sequence $u_{1},\dots,u_{m}\subseteq U$ and $S_{0}=\varnothing$, 
> 	$$(S^\text{OPT}_{n})_{n}\in \underset{\begin{subarray}{l}S_{1},\dots,S_{m}\subseteq U\\\left| S_{n} \right| \leq k, S_{n} \backslash S_{n-1}=\{ u_{n} \} \end{subarray} }{ \arg\min }\sum_{n=1}^{m}\underbrace{ 1-\chi_{S_{n-1}}(u_{n}) }_{ =:\text{cost}(u_{n}) }$$where $S_{n-1}$ is output before $u_{n}$ is input. 
- **Related Definition**: A paging algorithm is called ***conservative*** if for any $i<j$ with $\left| \{ u_{i},\dots,u_{j} \} \right|\leq k$,  $\text{cost}_{\mathcal{A}}(\{ u_{i},\dots, u_{j} \})\leq k$.
---
##### Properties
> [!lemma] Theorem 1
> Every conservative paging algorithm $\mathcal{A}$ is $k$-competitive. 

> [!proof]-
> Let $\sigma:=(u_{n})_{n}\subseteq U$. We define $a_{0}:=0$. Inductively, $$a_{i}:=\max \{ a_{i}>a_{i-1}:\left| \{ u_{a_{i-1}+1},\dots,u_{a_{i}} \} \right|\leq k  \}$$
> Let $\sigma$ be finite with length $N$ and let $p\in \mathbb{N}$ s.t. $u_{a_{p}}=u_{{N}}$. Then, 
> 1. $\text{cost}_{\mathcal{A}}(\sigma)\leq k\cdot p$.
> 2. $\text{cost}_{\text{OPT}}(\sigma)\geq p$ as $u_{a_{i}+1}\notin S_{a_{i}}^{\text{OPT}}$.
> 
> Hence, $\text{cost}_{\mathcal{A}}(\sigma)\leq k\cdot p\leq k\cdot \text{cost}_{\text{OPT}}(\sigma)$.
---
> [!lemma] Theorem 2
> For $\varepsilon>0$ and a deterministic algorithm $\mathcal{A}$, $\mathcal{A}$ is not $(k-\varepsilon)$-competitive.

> [!proof]-
> Let $U:=[k+1]$. Let the adversary pick an input sequence $\sigma:=(u_{n})_{n}$ s.t. $u_{n}\notin S_{n-1}$. Hence, 
> 1. $\text{cost}_{\mathcal{A}}(\sigma)=\left| \sigma \right|=:m$. 
> 
> However, for the optimal algorithm, 
> 1. $\text{cost}_{\text{OPT}}(\sigma)= m/k$ as $\text{OPT}$ can look into the future and at every eviction choose an element that doesn't appear in the next $k$ rounds. 

---
> [!lemma] Theorem 3 (Randomized Marking Algorithm)
>  ```pseudo
>    \begin{algorithm} \caption{RMA($u_{1},\dots,u_{m}$)} 
>    \begin{algorithmic}
>    \State $S_{0}\gets \varnothing$
>    \For{$i\in[m]$}
>    \If{$u_{i}\notin  S_{i-1}$}
>    \If{}
\EndIf
\EndIf
>    \EndFor
>    \end{algorithmic}
>    \end{algorithm}
>    ```
> 