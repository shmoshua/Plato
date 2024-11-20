#Definition #GraphTheory 

##### Properties

> [!lemma] Theorem 1 (Bollobas)
> With high probability, $$\chi(G(n,1/2))\sim \frac{n}{2\log_{2}n}$$

> [!proof]+
> Let $G=G(n, 1/2)$ and $\mu_{k}:=\mathbb{E}[\#\text{ independent sets of size }k]$. Then, $$\mu_{k}={n \choose k}2^{-{k \choose 2}}$$
> Now, let $k_{0}$ s.t. $\mu_{k_{0}-1}\geq 1 > \mu_{k_{0}}$. Then, 
> 1. Claim 1: $\mathbb{P}(G\text{ has no independent set of size }k)\leq \exp\left( -n ^{2-\text{o(1)}}\right)$
> 
> Then, let $m:=\left\lceil n / \log^2 n\right\rceil$ and let $k'\sim 2 \log_{2}m\sim 2 \log_{2}n\sim k$. 