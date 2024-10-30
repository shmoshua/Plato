#definition #GraphTheory 

> [!lemma] Theorem 1
> Let $G(n,1 / 2)$ be a random graph. 
> 1. there exists $k_0$ s.t. with high probability $\omega(G(n, 1/2))\in \{k_{0}-1,k_{0}\}$.

> [!proof]+
> Let $G=G(n,1/2)$. For a positive integer $k$, let $X_{k}$ be the number of cliques of size $k$ in $G$. Then, $X_{k}=\sum_{S}^{}X_{S}$ where $S$ iterates over all $k$-element subsets of the vertices and $X_{S}$ is the indicator variable if $S$ spans a clique or not. Then,
> $$\mu_{k}:=\mathbb{E}[X_{k}]={n \choose k}\left( \frac{1}{2} \right) ^{k \choose 2}$$If $k \sim 2\log_{2}n$ then $\mu_{k}<1$. Also, $$\frac{\mu_{k}}{\mu_{k+1}}=2^k \frac{k+1}{n-k}\leq n^{1-o(1)}$$
> Let $k_{0}$ be the first value s.t. $\mu_{k_{0}}\leq n^{1/2}$. Then, we have $$\mu_{k_{0}+1}\leq \frac{n^{1/2}}{n^{1-o(1)}}\leq n^{-1/2+o(1)}$$By Markov, $$\mathbb{P}(X_{k_{0}+1}\geq 1)\leq \mu_{k_{0}+1}\leq n^{-1/2+o(1)}$$
> On the other hand, let $k:=k_{0}-1$ and $\mu_{k}\geq \sqrt{ n }$ which goes to infinity. Hence, $$\mathbb{P}(X_{k}=0)\leq \frac{\text{Var}(X_{k})}{(\mathbb{E}[X_{k}])^{2}}$$Here, $$\text{Var}(X_{k})=\sum_{S,T}\text{Cov}(X_{S},X_{T})$$