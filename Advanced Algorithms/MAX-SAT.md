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
> [!lemma] Proposition 2
> Consider the following algorithm:
>    ```pseudo
>    \begin{algorithm} \caption{RandomMonteCarlo($I$)} 
>    \begin{algorithmic}
>    \State Sample $n$ times from $\{ 0,1 \}$ uniformly at random, independently. 
>    \State
>    \State Pick $\alpha(x_{i})$ from $\{ 0,1 \}$ uniformly at random.
>    \Return $\alpha$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
> 
> Then, 
> 1. $\mathbb{P}(\alpha \text{ satisfies }c_{j})=1-2^{-\left| c_{j} \right|}$ for all $j\in[m]$.
> 2. $\text{Random}$ is a 2-[[Approximation Algorithm|approximation algorithm]]. 

> [!proof]+
> Assume that $n$ is odd and let $x_{i1},\dots,x_{in}$ be the $n$ random variables from $\{ 0,1 \}$ chosen uniformly at random independently. Then, let: $$\alpha(x_{i})=1 \iff \sum_{k=1}^{n}x_{i k}\geq \left\lceil\frac{n}{2}\right\rceil $$Then, 
> 1. **Claim 1:**
> 	$$\begin{align}\mathbb{P}(\alpha \text{ doesn't satisfy }c_{j})&=\prod_{\ell=1}^{\left| c_{j} \right| }\mathbb{P}(\alpha \text{ doesn't satisfy }\ell \text{-th literal in }c_{j})\\&=\prod_{\ell=1}^{\left| c_{j} \right| }\mathbb{P}\left( X_{i}\geq \left( 1+\frac{1}{n} \right) \frac{n}{2}\right)\\&\leq \prod_{\ell=1}^{\left| c_{j} \right| } \frac{1}{\left( 1+\frac{1}{n} \right)}\\&\leq\exp \left( -\frac{\left| c_{j} \right| }{6n} \right) \\&\leq \exp \left( -\frac{1}{6n} \right) \end{align}$$
> 2. Claim 2: $$\mathbb{E}[w(S(\alpha))]\geq\sum_{j=1}^{m}w_{j}\left( 1- \exp \left( -n \right) \right) $$
---
