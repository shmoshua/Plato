#Definition #AlgebraicTopology 

> [!definition]
> Let $X$ be a non-empty [[topological space]] and $G$ an [[abelian group]].
> 1. the ***augmented chain complex*** $\mathcal{C}$ of $X$ is a [[chain complex]] given as: $$\cdots \to S_{2}(X;G)\xrightarrow{\partial}S_{1}(X;G)\xrightarrow{\partial}S_{0}(X;G)\xrightarrow{\varepsilon}G\to 0 \to \cdots$$where $S_{p}(X)$ denotes the [[p-Simplex|singular $p$-chains]] of $X$ and $$\varepsilon:S_{0}(X)\to G,\quad \sum_{x\in X}^{}g_{x}x\mapsto \sum_{x\in X}^{}g_{x}$$
> 2. the ***reduced cohomology*** of degree $p\in \mathbb{Z}$ is given as $\tilde{H}^p(X;G):=H^p(\mathcal{C}^{*})$ where $\mathcal{C}^{*}$ is the dual of augmented chain complex $\mathcal{C}$.

---
##### Properties
> [!lemma] Proposition 1
> We have that:
> $$\tilde{H}^n(X;G)\cong \begin{cases}H^n(X;G)&n>0\\\text{Hom}(\tilde{H}_{0}(X),G)&n=0\end{cases}$$

> [!proof]+
> We have that:
> 1. For $n>0$, the dual of augmented chain complex is the same as the dual of the singular chain complex. 
> 2. For $n=0$ we have that the dual of the augmented chain 