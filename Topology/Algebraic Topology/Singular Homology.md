#Definition #AlgebraicTopology 

> [!definition]
> Let $G$ be an [[abelian group]]. A ***singular homology*** $H(\cdot;G)$ with [[Homology Theory|coefficients group]] $G$ is defined as follows. For $X$ a [[topological space]]:
> 1. $\mathcal{S}(X;G)$ is the graded abelian group with $S_{p}(X;G):=\bigoplus_{\sigma:\Delta_{p}\to X}G\sigma$.
> 2. $\partial:S_{p}(X;G)\to S_{p-1}(X;G)$ extending $\partial(g\sigma):=\sum_{i=0}^{p}(-1)^ig \sigma \circ F_{i}^p$ where for all [[p-Simplex|singular $p$-simplex]] $\sigma:\Delta_{p}\to X$:$$(-1)^ig:=\begin{cases}g&i\text{ is even}\\-g&i\text{ is odd}\end{cases}$$and $F_{i}^p:\Delta_{i-1}\to\Delta_{i}$ is the [[p-Simplex|$i$-th face map]].
> 3. $H_{p}(X,G):=H_{p}(\mathcal{S}(X;G))$ and for $A\subseteq X$, $H_{p}(X,A;G):=H_{p}(\mathcal{S}(X,A;G))$ where $\mathcal{S}(X,A;G):=\mathcal{S}(X;G) / \mathcal{S}(A;G)$.
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\partial^{2}=0$, i.e. $\mathcal{S}(X;G)$ is a [[chain complex]].
> 2. For a point space $X$, $$H_{i}(X;G)\cong\begin{cases}G&i=0\\0&i\neq 0\end{cases}$$

> [!proof]-
> We have:
> 1. Follows from [[p-Simplex|boundary lemma]].
> 2. We have that the only singular $p$-simplex $\sigma_{p}:\Delta_{p}\to X$ is the constant map. Therefore, $S_{p}(X;G)\cong G$. 
>    
>    Now, for $p> 0$, we have that for $p$-simplex $\sigma:\Delta_{p}\to X$: $$\partial (g\sigma)=\begin{cases}0&p\text{ is odd}\\g\sigma_{p-1}&p\text{ is even}\end{cases}$$Hence, $$\text{ker }\partial \cong\begin{cases}G&p>0\text{ odd or }p=0\\0&\text{otherwise}\end{cases}$$
>    $$B_{p}(X;G) \cong\begin{cases}G&p>0\text{ odd}\\0&\text{otherwise}\end{cases}$$It follows that $H_{p}(X;G)\cong G$ if and only if $p=0$ and $0$ otherwise. 
---
> [!lemma] Theorem 2
> Let $X$ be a [[contractible space]]. Then, $H_{n}(X)=0$ for all $n\neq 0$.

> [!proof]+
> As $X$ is contractible, we have a homotopy $F:X\times I\to X$ s.t. $$F(x,0)=x,\quad F(x,1)=x_{0},\quad \forall x\in X$$where $x_{0}\in X$. Now, let $\sigma:\Delta_{n-1}\to X$ be a singular $(n-1)$-simplex. Then, we will define $$D\sigma:\Delta_{n}\to X,\quad \sum_{i=0}^{n}\lambda_{i}e_{i}\mapsto \begin{cases}F\left( \sigma\left( \sum_{i=1}^{n}\frac{\lambda_{i}}{1-\lambda_{0}}e_{i-1} \right) ,\lambda_{0}\right)&\lambda_{0}\neq 1\\x_{0}&\lambda_{0}=1\end{cases}$$Then, $D\sigma$ is continuous and we can extend $D$ linearly to a homomorphism $\mathcal{S}_{n-1}(X)\to \mathcal{S}_{n}(X)$ for all $n\geq 1$. For $n=0$, we set $D\equiv 0$. 
> 
> Now, we wish to compute $\partial D+D\partial$. 
> 1. For $n\geq 2$ and $\sigma:\Delta_{n-1}\to X$, we have that
> 	1. $(D\sigma)^{(0)}=\sigma$ as we have that: $$\begin{align}(D\sigma)^{(0)}(\lambda_{1}e_{0}+\dots+\lambda_{n}e_{n-1})&=(D\sigma)(\lambda_{1}e_{1}+\dots+\lambda_{n}e_{n})=F\left( \sigma\left( \sum_{i=1}^{n}\lambda_{i}e_{i-1} \right),0 \right)\\&=\sigma\left( \sum_{i=1}^n\lambda_{i}e_{i-1} \right)\end{align}$$
> 	2. $(D\sigma)^{(i)}=D(\sigma^{(i-1)})$ as we have that: $$\begin{align}(D\sigma)^{(i)}\left( \sum_{k=0}^{n-1}\lambda_{k}e_{k} \right)&=D\sigma \left( \sum_{k=0}^{i-1}\lambda_{k}e_{k} +\sum_{k=i+1}^{n}\lambda_{k-1}e_{k}\right) \end{align}$$If $\lambda_{0}=1$, then $(D\sigma)^{(i)}\left( \sum_{k=0}^{n-1}\lambda_{k}e_{k} \right)=x_{0}=D\left( \sigma\left( \sum_{k=0}^{i-2}\lambda_{k}e_{k}+\sum_{k=i}^{n}\lambda_{k-1}e_{k} \right) \right)$. Otherwise, $$\begin{align}(D\sigma)^{(i)}\left( \sum_{k=0}^{n-1}\lambda_{k}e_{k} \right)&=F\left(\sigma \left(  \sum_{k=1}^{i-1}\frac{\lambda_{k}}{1-\lambda_{0}}e_{k-1}+\sum_{k=i+1}^{n}\frac{\lambda_{k-1}}{1-\lambda_{0}}e_{k-1}\right) ,\lambda_{0}\right)\\&=F\left(\sigma \left(  \sum_{k=1}^{i-1}\frac{\lambda_{k}}{1-\lambda_{0}}e_{k-1}+\sum_{k=i+1}^{n}\frac{\lambda_{k-1}}{1-\lambda_{0}}e_{k-1}\right) ,\lambda_{0}\right)\\&=F\left(\sigma\left( \sum_{k=0}^{i-2}\frac{\lambda_{k+1}}{1-\lambda_{0}}e_{k}+\sum_{k=i}^{n-1}\frac{\lambda_{k}}{1-\lambda_{0}}e_{k}\right),\lambda_{0} \right)\\&=F\left( \sigma^{(i-1)}\left( \sum_{k=0}^{n-2}\frac{\lambda_{k+1}}{1-\lambda_{0}}e_{k}\right),\lambda_{0} \right)\\&=F\left( \sigma^{(i-1)}\left( \sum_{k=1}^{n-1}\frac{\lambda_{k}}{1-\lambda_{0}}e_{k-1}\right),\lambda_{0} \right)\\&=D\left( \sigma^{(i-1)}\left( \sum_{k=0}^{n-1}\lambda_{k}e_{k} \right) \right)\end{align}$$
> 
> 	Therefore, $$\partial(D\sigma)=\sigma+\sum_{i=1}^{n}(-1)^iD(\sigma^{(i-1)})=\sigma-\sum_{i=0}^{n-1}(-1)^iD(\sigma^{(i)})=\sigma-D\partial\sigma$$Hence, $\partial D+D\partial=\text{id}$.
> 2. For $n=1$, let $\sigma$ is a $0$-simplex and let $\sigma_{0}:\Delta_{0}\to X$ be the $0$-simplex corresponding to $x_{0}$
---
> [!lemma] Theorem 3
> The singular homology $H(\cdot;G)$ is a [[homology theory]] with coefficient group $G$.

> [!proof]+
> 
---
