#Definition #Algorithms 
> [!definition]
> For $\mathcal{S}:=[n]$, let $p:[n]\to \mathbb{R}_{\geq 0}$   be the processing time for each job $i\in[n]$. 
> 1. For a given $m$, the ***minimum makespan scheduling problem*** aims to find: $$\text{OPT}(I)\in\underset{ {B_{1}\sqcup\dots\sqcup B_{m}=[n]} }{ \arg\min }\max_{{i\in[m]}}\sum_{j\in B_{i}}^{}p_{j}$$
- **Remark**: For the optimal makespan $t_{\text{OPT}}$, $p_{\max}\leq t_{\text{OPT}}$ and $\frac{1}{m}\sum_{i=1}^{n}p_{i}\leq t_{\text{OPT}}$.
---
##### Properties
> [!lemma] Theorem 1 (Graham)
> Consider the algorithm:
> ```pseudo
> \begin{algorithm}\caption{Graham($I=\{ p_{1},\dots,p_{n},m \}$)}
> \begin{algorithmic} 
> \State $B_{1},\dots,B_{m}\gets \varnothing$
> \For{$t\in[n]$}
> \State $i\gets \arg\min_{i\in[m]}\sum_{j\in B_{i}}^{}p_{j}$
> \State $B_{i}\gets B_{i}\cup \{ t \}$\EndFor
> \Return $B_{1},\dots,B_{m}$
> \end{algorithmic}
> \end{algorithm}
> ```
> $\text{Graham}$ is a 2-[[approximation algorithm]].

> [!proof]-
> Let $t$ be the job that finishes last and assume that $t\in B_{i}$. Then, define $T:=\sum_{j\in B_{i}}^{}p_{j}-p_{t}$. Then, we have that: 
> 1. $\left| \text{Graham}(I) \right|=T+p_{t}$ and
> 2. $T\leq \frac{1}{ m}\sum_{i=1}^{n}p_{i}\leq t_{\text{OPT}}$. 
> 
> Hence, $\left| \text{Graham}(I) \right|\leq 2 t_{\text{OPT}}$.

---