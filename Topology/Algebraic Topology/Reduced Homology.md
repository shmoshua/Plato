#Definition #AlgebraicTopology 

> [!definition]
> Let $X$ be a [[topological space]]. 
> 1. the ***augmented chain complex*** $\mathcal{C}$ of $X$ is a [[chain complex]] given as: $$\cdots \to S_{2}(X)\xrightarrow{\partial}S_{1}(X)\xrightarrow{\partial}S_{0}(X)\xrightarrow{\varepsilon}\mathbb{Z}\to 0 \to \cdots$$where $S_{p}(X)$ denotes the [[p-Simplex|singular $p$-chains]] of $X$ and $$\varepsilon:S_{0}(X)\to \mathbb{Z},\quad \sum_{x\in X}^{}n_{x}x\mapsto \sum_{x\in X}^{}n_{x}$$
> 2. the ***reduced homology*** of degree $p\in \mathbb{Z}$ is given as $\tilde{H}_{p}(X):=H_{p}(\mathcal{C})$.

- **Remark**: If $X=\varnothing$, then $S_{p}(X) =0$ for all $p\geq 0$. Hence, $$\tilde{H}_{p}(X)=\begin{cases}\end{cases}$$