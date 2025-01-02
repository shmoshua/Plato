#Definition #AlgebraicTopology 

> [!definition]
> Let $X$ be a [[topological space]]. 
> 1. the ***augmented chain complex*** $\mathcal{C}$ of $X$ is a [[chain complex]] given as: $$\cdots \to S_{2}(X)\xrightarrow{\partial}S_{1}(X)\xrightarrow{\partial}S_{0}(X)\xrightarrow{\varepsilon}\mathbb{Z}\to 0 \to \cdots$$where $S_{p}(X)$ denotes the [[p-Simplex|singular $p$-chains]] of $X$ and $$\varepsilon:S_{0}(X)\to \mathbb{Z},\quad \sum_{x\in X}^{}n_{x}x\mapsto \sum_{x\in X}^{}n_{x}$$
> 2. the ***reduced homology*** of degree $p\in \mathbb{Z}$ is given as $\tilde{H}_{p}(X):=H_{p}(\mathcal{C})$.

- **Remark**: If $X=\varnothing$, then $S_{p}(X) =0$ for all $p\geq 0$. Hence, $$\tilde{H}_{p}(X)=\begin{cases}\mathbb{Z}&p=-1\\0&p\neq-1\end{cases}$$
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. the augmented chain complex is a well-defined chain complex. 

> [!proof]-
> We have to show that:
> 1. We need that $\varepsilon \circ\partial = 0$. Let $\sigma:\Delta_{1}\to X$ be a $1$-simplex. Then, $$\varepsilon(\partial\sigma)=\varepsilon(\sigma(1)-\sigma(0))=1-1=0$$ Hence, $\varepsilon(\partial c) = 0$ for all $1$-chain $c$. 

---
> [!lemma] Theorem 2
> Let $X\neq \varnothing$. Then,
> 1. $\tilde{H}_{p}(X)=H_{p}(X)$ for $p\geq 1$.
> 2. $\tilde{H}_{0}(X)=\text{ker }\varepsilon_{*}$ where $\varepsilon_{*}:H_{0}(X)\to \mathbb{Z}$.

> [!proof]+
> We have that, 
> 1. for $p\geq 1$, we have that: $$\tilde{H}_{p}(X)= Z_{p}(X) / B_{p}(X)=H_{p}(X)$$
> 2. Let $c\in B_{0}(X)$. Then, $$\varepsilon_{*}([])$$
> 3. As we have $\varepsilon \circ \partial = 0$, 
> $$\begin{CD}\cdots @>>> S_{2}(X) @>\partial>> S_{1}(X)@>\partial>> S_{0}(X)@>>> 0@>>>\cdots\\&@VVV@VVV@V\varepsilon VV@VVV\\\cdots@>>> 0@>>>0@>>>\mathbb{Z}@>>>0@>>>\cdots\end{CD}$$the following diagram commutes. Let $\mathcal{A}$ be the lower chain complex, i.e. $A_{0}=\mathbb{Z}$ and $A_{p}=0$ for all $p\neq 0$. Then, we can write a chain map $f:\mathcal{S}(X)\to \mathcal{A}$ where $f_{0}=\varepsilon$ and $f_{p}=0$ for all $p\neq 0$.
> 
>    Therefore, $f_{*}:H_{p}(X)\to H_{p}(\mathcal{B})$ is a group homomorphism where: $$H_{p}(\mathcal{B}):=\begin{cases}\mathbb{Z}&p=0\\0&p\neq 0\end{cases}$$Hence, 