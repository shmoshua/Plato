#Definition #Algorithms 

> [!definition]
> For a universe $U$, let $S\subseteq U$ be a cache s.t. $\left| S \right|\leq k$. 
> 1. The ***paging problem*** aims to find an optimal algorithm s.t. for a finite sequence $u_{1},\dots,u_{m}\subseteq U$ and $S_{0}=\varnothing$, 
> 	$$(S^\text{OPT}_{n})_{n}\in \underset{\begin{subarray}{l}S_{1},\dots,S_{m}\subseteq U\\\left| S_{n} \right| \leq k, S_{n} \backslash S_{n-1}=\{ u_{n} \} \end{subarray} }{ \arg\min }\sum_{n=1}^{m}\underbrace{ 1-\chi_{S_{n-1}}(u_{n}) }_{ =:\text{cost}(u_{n}) }$$where $S_{n-1}$ is output before $u_{n}$ is input. 

^8651de

- **Related Definition**: A paging algorithm is called ***conservative*** if for any $i<j$ with $\left| \{ u_{i},\dots,u_{j} \} \right|\leq k$,  $\text{cost}_{\mathcal{A}}(\{ u_{i},\dots, u_{j} \})\leq k$. ^8c42a1
---
##### Properties
> [!lemma] Theorem 1
> Every conservative paging algorithm $\mathcal{A}$ is [[Competitive Online Algorithm|$k$-competitive]]. 

^7371ed

> [!proof]-
> Let $\sigma:=(u_{n})_{n}\subseteq U$. We define $a_{0}:=0$. Inductively, $$a_{i}:=\max \{ a_{i}>a_{i-1}:\left| \{ u_{a_{i-1}+1},\dots,u_{a_{i}} \} \right|\leq k  \}$$
> Let $\sigma$ be finite with length $N$ and let $p\in \mathbb{N}$ s.t. $u_{a_{p}}=u_{{N}}$. Then, 
> 1. $\text{cost}_{\mathcal{A}}(\sigma)\leq k\cdot p$.
> 2. $\text{cost}_{\text{OPT}}(\sigma)\geq p$ as $u_{a_{i}+1}\notin S_{a_{i}}^{\text{OPT}}$.
> 
> Hence, $\text{cost}_{\mathcal{A}}(\sigma)\leq k\cdot p\leq k\cdot \text{cost}_{\text{OPT}}(\sigma)$.

^0e131a

---
> [!lemma] Theorem 2
> For $\varepsilon>0$ and a deterministic algorithm $\mathcal{A}$, $\mathcal{A}$ is not $(k-\varepsilon)$-competitive.

^4e0de5

> [!proof]-
> Let $U:=[k+1]$. Let the adversary pick an input sequence $\sigma:=(u_{n})_{n}$ s.t. $u_{n}\notin S_{n-1}$. Hence, 
> 1. $\text{cost}_{\mathcal{A}}(\sigma)=\left| \sigma \right|=:m$. 
> 
> However, for the optimal algorithm, 
> 1. $\text{cost}_{\text{OPT}}(\sigma)= m/k$ as $\text{OPT}$ can look into the future and at every eviction choose an element that doesn't appear in the next $k$ rounds. 

^547661

---
> [!lemma] Theorem 3 (Randomized Marking Algorithm)
>  ```pseudo
>    \begin{algorithm} \caption{RMA($u_{1},\dots,u_{m}$)} 
>    \begin{algorithmic}
>    \State $S_{0}\gets \varnothing$
>    \State $v\gets 0$
>    \For{$i\in[m]$}
>    \If{$u_{i}\notin  S_{i-1}$}
>    \If{$v(u_{j})=1$ for all $u_{j}\in S_{i-1}$}
>    \State $v(u_{j})\gets 0$ for all $u_{j}\in S_{i-1}$
\EndIf
>    \State $u\gets$ choose an unmarked item from $S_{i-1}$ uniformly at random.
>    \State $S_{i}\gets S_{i-1} \backslash \{ u \}\cup \{  u_{i}\}$
\EndIf
> 	\State $v(u_{i})\gets 1$
>    \EndFor
>    \Return $S_{1},\dots,S_{m}$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
>    
>    The $\text{RMA}$ algorithm is $\text{O}(\log k)$-competitive in expectation against an oblivious adversary.

^0ffb3f

> [!proof]-
> Assume that $i\in [m]$ s.t. $v=0$ before iteration $i$. Let: $$j:=\min\{  j>i: \|v_{j}\| =k \}$$where $v_{j}$ denotes $v$ at iteration $j$. Then, let $P:=\{ u_{i},\dots,u_{j} \}$. We define:
> 1. $m:=\left| \{ u_\ell\in P:u_{\ell}\notin S_{i} \} \right|$ the number of unique new requests
> 2. $o:=\left| \{ u_\ell\in P:u_{\ell}\in S_{i} \} \right|$ the number of unique old requests
>  
>  Then, by construction $m+o=k$. We order the old requests as $x_{1},\dots,x_{o}$ by their first occurrence in $P$. Further, let $\ell_{j}$ be the number of distinct new requests before $x_{j}$. At the first time $x_{j}$ is requested, there are $\ell_{j}+j-1$ marked pages in the cache. The other $k-\ell_{j}-(j-1)$ pages in the cache are a subset of the $k-(j-1)$ pages in $P$ that have not been queried yet in this phase. Since the adversary is oblivious, all these pages have the same probability still to be in the cache. Since $x_{j}$ is one of them, the probability that $x_{j}$ is still in the cache is $\frac{k-\ell_{j}-(j-1)}{k-(j-1)}$. Then, $$\begin{align}\mathbb{E}[\text{cost}_{\text{RMA}}(o)]&=\sum_{\ell=1}^{o}\mathbb{P}(x_{j}\text{ is not in cache when requested})\\&=\sum_{\ell=1}^{o}\frac{\ell_{j}}{k-(j-1)}\\&\leq \sum_{\ell=1}^{o} \frac{m}{k-(j-1)}\\&\leq\sum_{\ell=1}^{k} \frac{m}{k-(j-1)}\\&=m\sum_{\ell=1}^{k} \frac{1}{\ell}\\&=m\cdot H_{k}\end{align}$$
>  Hence, $\mathbb{E}[\text{cost}_{\text{RMA}}(u_{i},\dots,u_{j})]=m+m\cdot H_{k}$. Let $P$ be one phase and for phase $q$, we have $m_{q}$ as the number of unique new requests. Then, in Phase $q$ and Phase $q+1$, there are at least $k+m_{q+1}$ new requests. Therefore, $\text{cost}_{\text{OPT}}(\text{Phase}_{q}+ \text{Phase}_{q+1})\geq m_{q+1}$. Hence, $$2\cdot c_{\text{OPT}}(\sigma)\geq \sum_{i}^{}m_{i}$$Finally, $$\mathbb{E}[\text{c}_{\text{RMA}}(\sigma)]\leq \sum_{i}^{}m_{i}(1+H_{k})=\text{O}(\log k)\sum_{i}^{}m_{i}\leq \text{O}(\log k)\cdot c_{\text{OPT}}(\sigma)$$

^7391c2

---
> [!lemma] Theorem 4
> Every randomized algorithm $\mathcal{A}$ for paging is $\Omega(\log k)$-competitive against an oblivious adversary.
---
