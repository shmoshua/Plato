#Definition #Algorithms 

> [!definition]
> Given an undirected [[graph]] $G=(V,E)$, a ***tree embedding*** is a [[probability space]] $(\mathcal{T},\Sigma,\mathbb{P})$ where $\mathcal{T}:=\{ T_{1},\dots,T_{p} \}$ where $T_{i}$ is a [[tree]] on $V$ s.t.
> 1. for all $u,v\in V$, $d_{G}(u,v)\leq d_{T_{i}}(u,v)$.
> 2. there exists a $c>0$ s.t. for all $u,v\in V$, $\mathbb{E}[d_{T}(u,v)]\leq c\cdot d_{G}(u,v)$
---
##### Properties
> [!lemma] Theorem 1 (Low Diameter Decomposition)
> Let $G=(V,E)$ be an undirected graph and $\delta:=\text{diam}(G)$.
> ```pseudo
> \begin{algorithm}
> \begin{algorithmic}
> \end{algorithmic}
> \end{algorithm}
> ```
> 
> Then, the algorithm outputs a partition $V=\bigsqcup_{i\in[p]}^{} C_{i}$ s.t. 
> 1. for all $i\in[p]$, $\text{diam}(C_{i})\leq\delta$
> 2. there exists $\alpha>0$ s.t. for all $v\in V$ and $r\geq 0$, $\mathbb{P}(\forall i:B_{\leq r}(v)\nsubseteq C_{i})\leq \alpha r / \delta$.