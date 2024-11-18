#Definition #Algorithms 

> [!definition]
> Given an undirected [[graph]] $G=(V,E)$, a ***tree embedding*** is a [[probability space]] $(\mathcal{T},\Sigma,\mathbb{P})$ where $\mathcal{T}:=\{ T_{1},\dots,T_{p} \}$ where $T_{i}$ is a [[tree]] on $V$ s.t.
> 1. for all $u,v\in V$, $d_{G}(u,v)\leq d_{T_{i}}(u,v)$.
> 2. there exists a $c>0$ s.t. for all $u,v\in V$, $\mathbb{E}[d_{T}(u,v)]\leq c\cdot d_{G}(u,v)$