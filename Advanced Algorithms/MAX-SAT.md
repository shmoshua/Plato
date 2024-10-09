#Definition #Algorithms 

> [!definition]
> Let $x_{1},\dots,x_{n}$ be variables and $c_{1},\dots,c_{m}$ be clauses on the variables. Further, let $w:[m]\to \mathbb{R}$ be the ***weight*** function. 
> 1. The ***MAX-SAT problem*** aims to find: $$\alpha_{\text{OPT}}\in \underset{ \alpha \text{ assignment} }{ \arg\max }\sum_{j:c_{j}\text{ satisfied by }\alpha}^{}w_{j}$$
---
##### Properties
> [!lemma] Proposition 1
> Consider the following algorithm:
>    ```pseudo
>    \begin{algorithm} \caption{Random($I$)} 
>    \begin{algorithmic}
>    \State Pick $\alpha(x_{i})$ from $\{ 0,1 \}$ uniformly at random.
>    \Return $\alpha$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
> 
> Then, 
> 1. $\mathbb{P}(\alpha \text{ satisfies }c_{j})=1-2^{-\left| c_{j} \right|}$ for all $j\in[m]$.
> 2. $\text{Random}$ is a 2-[[Approximation Algorithm|approximation algorithm]]. 

> [!proof]-
> We have that:
> 1. $\alpha$ does not satisfy $c_{j}$ if and only if $\alpha$ gives false to all literals in $c_{j}$. This happens with probability $\frac{1}{2^\left| c_{j} \right|}$. This proves the statement.
> 2. For an assignment $\alpha$, let $S(\alpha):=\{ j\in[m]:\alpha \text{ satisfies }c_{j} \}$. Then, $$\mathbb{E}[w(S(\alpha))]=\sum_{j=1}^{m}w_{j}\cdot \mathbb{P}(\alpha \text{ satisfies }c_{j})=\sum_{j=1}^{m}w_{j}\left( 1-\frac{1}{2^{\left| c_{j} \right| }} \right)\geq \frac{1}{2}\sum_{j=1}^{m}w_{j}\geq \frac{1}{2}w(S(\alpha_{\text{OPT}})) $$
---
