#Definition #Algorithms 
> [!definition]
> For $\mathcal{S}:=[n]$, let $p:[n]\to \mathbb{R}_{\geq 0}$   be the processing time for each job $i\in[n]$. 
> 1. For a given $m$, the ***minimum makespan scheduling problem*** aims to find: $$\text{OPT}(I)\in\underset{ {B_{1}\sqcup\dots\sqcup B_{m}=[n]} }{ \arg\min }\max_{{i\in[m]}}\sum_{j\in B_{i}}^{}p_{j}$$
- **Remark**: For the optimal makespan $t_{\text{OPT}}$, $p_{\max}\leq t_{\text{OPT}}$ and $\frac{1}{m}\sum_{i=1}^{n}p_{i}\leq t_{\text{OPT}}$.