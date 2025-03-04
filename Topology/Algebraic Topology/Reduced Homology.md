#Definition #AlgebraicTopology 

> [!definition]
> Let $X$ be a [[topological space]] and $G$ an abelian group.
> 1. the ***augmented chain complex*** $\mathcal{C}$ of $X$ is a [[chain complex]] given as: $$\cdots \to S_{2}(X;G)\xrightarrow{\partial}S_{1}(X;G)\xrightarrow{\partial}S_{0}(X;G)\xrightarrow{\varepsilon}G\to 0 \to \cdots$$where $S_{p}(X)$ denotes the [[p-Simplex|singular $p$-chains]] of $X$ and $$\varepsilon:S_{0}(X)\to G,\quad \sum_{x\in X}^{}g_{x}x\mapsto \sum_{x\in X}^{}g_{x}$$
> 2. the ***reduced homology*** of degree $p\in \mathbb{Z}$ is given as $\tilde{H}_{p}(X;G):=H_{p}(\mathcal{C})$.

^5ea9ed

- **Remark**: If $X=\varnothing$, then $S_{p}(X;G) =0$ for all $p\geq 0$. Hence, $$\tilde{H}_{p}(X)=\begin{cases}G&p=-1\\0&p\neq-1\end{cases}$$ ^561e7f
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. the augmented chain complex is a well-defined chain complex. 

^61ad56

> [!proof]-
> We have to show that:
> 1. We need that $\varepsilon \circ\partial = 0$. Let $\sigma:\Delta_{1}\to X$ be a $1$-simplex and $g\in G$. Then, $$\varepsilon(\partial (g\sigma))=\varepsilon(g\sigma(1)-g\sigma(0))=g-g=0$$ Hence, $\varepsilon(\partial gc) = 0$ for all $1$-chain $c$ and $g\in G$.

^da0adf

---
> [!lemma] Theorem 2
> Let $X\neq \varnothing$ and $G$ an abelian group. Then,
> 1. $\tilde{H}_{p}(X;G)=H_{p}(X;G)$ for $p\geq 1$.
> 2. $\tilde{H}_{0}(X;G)=\text{ker }\varepsilon_{*}$ where $\varepsilon_{*}:H_{0}(X)\to G$.
> 3. $\tilde{H}_{p}(X;G)=\text{ker }f_{*}$ where $f$ is a chain map s.t. $f_{0}= \varepsilon$ and $f_{p}=0$ otherwise.
> 4. $\tilde{H}_{0}(X;G)=0$ if $X$ is [[Path-Connected Space|path-connected]].

^f3d014

> [!proof]-
> We have that, 
> 1. for $p\geq 1$, $$\tilde{H}_{p}(X;G)=Z_{p}(\mathcal{S}(X;G)) / B_{p}(\mathcal{S}(X;G))=H_{p}(X;G)$$
> 2. for $p\geq 1$, we have that: $$\tilde{H}_{p}(X)= Z_{p}(X) / B_{p}(X)=H_{p}(X)$$
> 3. Let $c\in \text{ker }\varepsilon$. Then, $\varepsilon_{*}([c])=[\varepsilon(c)]=[0]=0$ and $[c]\in \text{ker }\varepsilon_{*}$. Let: $$\phi: \text{ker }\varepsilon\to \text{ker } \varepsilon_{*},\quad c \mapsto [c]$$Then, $\text{ker }\phi=\{ c\in \text{ker }\varepsilon :c\in  \text{im}(\partial) \}=\text{im}(\partial)$. Lastly, we have that $\phi$ is a projection and hence is surjective. Hence, we have that: $$\tilde{H}_{0}(X)= \text{ker }\varepsilon / \text{im }\partial \cong \text{ker }\varepsilon_{*}$$
> 4. As we have $\varepsilon \circ \partial = 0$, 
> $$\begin{CD}\cdots @>>> S_{2}(X) @>\partial>> S_{1}(X)@>\partial>> S_{0}(X)@>>> 0@>>>\cdots\\&@VVV@VVV@V\varepsilon VV@VVV\\\cdots@>>> 0@>>>0@>>>\mathbb{Z}@>>>0@>>>\cdots\end{CD}$$the following diagram commutes. Let $\mathcal{A}$ be the lower chain complex, i.e. $A_{0}=\mathbb{Z}$ and $A_{p}=0$ for all $p\neq 0$. Then, we can write a chain map $f:\mathcal{S}(X)\to \mathcal{A}$ where $f_{0}=\varepsilon$ and $f_{p}=0$ for all $p\neq 0$.
> 
>    Therefore, $f_{*}:H_{p}(X)\to H_{p}(\mathcal{B})$ is a group homomorphism where: $$H_{p}(\mathcal{B}):=\begin{cases}\mathbb{Z}&p=0\\0&p\neq 0\end{cases}$$Hence, we have that $\tilde{H}_{p}(X)=\text{ker }\varepsilon_{*}=\text{ker }f_{*}$ if $p=0$ and if $p\neq 0$, we have that: $$\tilde{H}_{p}(X)=H_{p}(X)=\text{ker }f_{*}$$
>1. Consider a singular $0$-simplex $\sigma$ in $X$. Then, as $\Delta_{0}$ is a point, $S_{0}(X;G)$ is a set a finite formal sum of points in $X$. 
>   
>    From Proposition 1, we have that $\varepsilon \partial=0$. Hence, $\varepsilon(B_{0}(X;G))=0$ and we have that: $$\varepsilon _{*}:H_{0}(X;G)\to G$$is a homomorphism.
>    
>    Now, clearly, $\varepsilon_{*}([gx])=g\in G$ and $\varepsilon_{*}$ is surjective. To show that it is also injective, let $x_{0}\in X$ and for all $x\in X$, let $\lambda_{x}:I\to X$ be a path from $\lambda_{x}(0)=x_{0}$ and $\lambda_{x}(1)=x$. By viewing these paths as singular $1$-simplices, we have that: $$\partial(g\lambda_{x})=gx-gx_{0}\in S_{0}(X;G)$$Let $c\in S_{0}(X;G)$ with $c=\sum_{x}^{}g_{x}x$ be a $0$-chain and assume that $\varepsilon_{*}([c])=0$. Then, for $d:=\sum_{x}^{}g_{x}\lambda_{x}\in S_{1}(X;G)$, we have that: $$\partial d=\sum_{x}^{}g_{x}(x-x_{0})=\sum_{x}^{}g_{x}x-\varepsilon_{*}([c])x_{0}=c$$Hence, $c\in B_{0}(X;G)$ and $\varepsilon_{*}([c])=0$.

^c5acbf

---
