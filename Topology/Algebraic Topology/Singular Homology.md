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

> [!proof]-
> As $X$ is contractible, we have a homotopy $F:X\times I\to X$ s.t. $$F(x,0)=x,\quad F(x,1)=x_{0},\quad \forall x\in X$$where $x_{0}\in X$. Now, let $\sigma:\Delta_{n-1}\to X$ be a singular $(n-1)$-simplex. Then, we will define $$D\sigma:\Delta_{n}\to X,\quad \sum_{i=0}^{n}\lambda_{i}e_{i}\mapsto \begin{cases}F\left( \sigma\left( \sum_{i=1}^{n}\frac{\lambda_{i}}{1-\lambda_{0}}e_{i-1} \right) ,\lambda_{0}\right)&\lambda_{0}\neq 1\\x_{0}&\lambda_{0}=1\end{cases}$$Then, $D\sigma$ is continuous and we can extend $D$ linearly to a homomorphism $\mathcal{S}_{n-1}(X)\to \mathcal{S}_{n}(X)$ for all $n\geq 1$. For $n=0$, we set $D\equiv 0$. 
> 
> Now, we wish to compute $\partial D+D\partial$. 
> 1. For $n\geq 2$ and $\sigma:\Delta_{n-1}\to X$, we have that
> 	1. $(D\sigma)^{(0)}=\sigma$ as we have that: $$\begin{align}(D\sigma)^{(0)}(\lambda_{1}e_{0}+\dots+\lambda_{n}e_{n-1})&=(D\sigma)(\lambda_{1}e_{1}+\dots+\lambda_{n}e_{n})=F\left( \sigma\left( \sum_{i=1}^{n}\lambda_{i}e_{i-1} \right),0 \right)\\&=\sigma\left( \sum_{i=1}^n\lambda_{i}e_{i-1} \right)\end{align}$$
> 	2. $(D\sigma)^{(i)}=D(\sigma^{(i-1)})$ as we have that: $$\begin{align}(D\sigma)^{(i)}\left( \sum_{k=0}^{n-1}\lambda_{k}e_{k} \right)&=D\sigma \left( \sum_{k=0}^{i-1}\lambda_{k}e_{k} +\sum_{k=i+1}^{n}\lambda_{k-1}e_{k}\right) \end{align}$$If $\lambda_{0}=1$, then $(D\sigma)^{(i)}\left( \sum_{k=0}^{n-1}\lambda_{k}e_{k} \right)=x_{0}=D\left( \sigma\left( \sum_{k=0}^{i-2}\lambda_{k}e_{k}+\sum_{k=i}^{n}\lambda_{k-1}e_{k} \right) \right)$. Otherwise, $$\begin{align}(D\sigma)^{(i)}\left( \sum_{k=0}^{n-1}\lambda_{k}e_{k} \right)&=F\left(\sigma \left(  \sum_{k=1}^{i-1}\frac{\lambda_{k}}{1-\lambda_{0}}e_{k-1}+\sum_{k=i+1}^{n}\frac{\lambda_{k-1}}{1-\lambda_{0}}e_{k-1}\right) ,\lambda_{0}\right)\\&=F\left(\sigma \left(  \sum_{k=1}^{i-1}\frac{\lambda_{k}}{1-\lambda_{0}}e_{k-1}+\sum_{k=i+1}^{n}\frac{\lambda_{k-1}}{1-\lambda_{0}}e_{k-1}\right) ,\lambda_{0}\right)\\&=F\left(\sigma\left( \sum_{k=0}^{i-2}\frac{\lambda_{k+1}}{1-\lambda_{0}}e_{k}+\sum_{k=i}^{n-1}\frac{\lambda_{k}}{1-\lambda_{0}}e_{k}\right),\lambda_{0} \right)\\&=F\left( \sigma^{(i-1)}\left( \sum_{k=0}^{n-2}\frac{\lambda_{k+1}}{1-\lambda_{0}}e_{k}\right),\lambda_{0} \right)\\&=F\left( \sigma^{(i-1)}\left( \sum_{k=1}^{n-1}\frac{\lambda_{k}}{1-\lambda_{0}}e_{k-1}\right),\lambda_{0} \right)\\&=D\left( \sigma^{(i-1)}\left( \sum_{k=0}^{n-1}\lambda_{k}e_{k} \right) \right)\end{align}$$
> 
> 	Therefore, $$\partial(D\sigma)=\sigma+\sum_{i=1}^{n}(-1)^iD(\sigma^{(i-1)})=\sigma-\sum_{i=0}^{n-1}(-1)^iD(\sigma^{(i)})=\sigma-D\partial\sigma$$Hence, $\partial D+D\partial=\text{id}$.
> 2. For $n=1$, let $\sigma$ is a $0$-simplex and let $\sigma_{0}:\Delta_{0}\to X$ be the $0$-simplex corresponding to $x_{0}$. Then,
> 	1. $\partial(D\sigma)=\sigma-\sigma_{0}$ and 
> 	2. $D(\partial\sigma)=D(0)=0$. 
> 
> Therefore, we have that: $$D\partial(\sigma)+\partial D(\sigma)=\begin{cases}\sigma&n\geq 2\\\sigma-\sigma_{0}&n=1\\ 0&n\leq 0\end{cases}$$Consider the map $\varepsilon:S_{n}(X)\to S_{n}(X)$ s.t. $\varepsilon=0$ for $n\geq 1$ and for $n=0$, $\varepsilon\left( \sum_{}^{}n_{x}x \right)=\sum_{}n_{x} x_{0}$Then, $\varepsilon$ is of course a chain map and $D\partial+\partial D=\text{id}-\varepsilon$ and $\text{id}\sim \varepsilon$. Hence, $\varepsilon_{*}=\text{id}_{H_{*}(X)}$. However, $\text{id}=\varepsilon_{*}:H_{n}(X)\to H_{n}(X)=0$ for all $n>0$ and we get that $H_{n}(X)=0$ for all $n\neq 0$.
---
> [!lemma] Theorem 3 (Cross Product)
> Let $X,Y$ be topological spaces. There exists a family of bilinear map $$\times:S_{p}(X)\times S_{q}(Y)\to S_{p+q}(X\times Y),\quad \forall p,q\geq 0,X,Y$$with the following properties:
> 1. For all $x\in X$ and $y\in Y$, $\sigma:\Delta_{p}\to X$ and $\tau:\Delta_{q}\to Y$ simplices, we have that: $$\sigma \times y:\Delta_{p}\to X\times Y, \quad w\mapsto (\sigma(w),y),\quad x \times \tau:\Delta_{q}\to X\times Y, \quad w\mapsto (x,\tau(w))$$
> 2. For continuous maps $f:X\to X'$ and $g:Y\to Y'$,  $f\times g:X\times Y\to X'\times Y'$ satisfies: $$(f\times g)_{c}(a\times b)=f_{c}(a)\times g_{c}(b),\quad \forall a\in S_{p}(X),b\in S_{q}(Y)$$
> 3. Leibniz Formula: $$\partial(a\times b)=\partial a\times b+(-1)^pa\times \partial b,\quad \forall a\in S_{p}(X),b\in S_{q}(Y) $$

> [!proof]+
> We have that:
> 1. Assume that $p=0$. We define: $$\left( \sum_{x}^{}n_{x}x \right)\times\left( \sum_{\tau:\Delta_{q}\to Y}^{}n_{\tau}\tau \right)=\sum_{x}\sum_{\tau:\Delta_{q}\to Y}^{}n_{x}n_{\tau} (x \times \tau)$$
>    Then, 1 obviously holds and we have that: $$\begin{align}(f\times g)_{c}\left( \sum_{x}^{}\sum_{\tau:\Delta_{q}\to Y}^{}n_{x}n_{\tau}x \times \tau\right)&=\sum_{x}n_{x}\sum_{\tau:\Delta_{q}\to Y}^{}n_{\tau}(f\times g)\circ (x \times\tau)\\&= \sum_{x}^{}n_{x}\sum_{\tau:\Delta_{q}\to Y}^{}n_{\tau}(f(x)\times (g \circ  \tau))\\&=\left( \sum_{x}n_{x}f(x) \right) \times \left( \sum_{\tau:\Delta_{q}\to Y}^{}n_{\tau}(g\circ \tau) \right) \\&=f_{c}\left( \sum_{x}^{}n_{x}x \right)\times g_{c}\left( \sum_{\tau:\Delta_{q}\to Y}^{}n_{\tau}\tau \right)\end{align}$$Further, for the Leibniz formula, $$\begin{align}\partial \left( \sum_{x}\sum_{\tau:\Delta_{q}\to Y}^{}n_{x}n_{\tau} (x \times \tau) \right) &=\sum_{x}\sum_{\tau:\Delta_{q}\to Y}^{}n_{x}n_{\tau} \sum_{i=0}^{q}(-1)^i(x \times \tau)^{(i)}\\&=\sum_{x}\sum_{\tau:\Delta_{q}\to Y}^{}n_{x}n_{\tau} (x \times \partial \tau)\\&= \left( \sum_{x}^{}n_{x}x \right) \times \partial \left( \sum_{\tau :\Delta_{q}\to Y}^{}n_{\tau}\tau \right)\end{align}$$
>    Similarly, it holds for $q=0$. 
>  2. Now, we will show it for general $p,q\geq 0$ by induction over $\ell:=p+q$.
> 	 1. If $\ell=0$ or $\ell=1$, then either $p=0$ or $q=0$ and we have the statement.
> 	 2. Let $\ell\geq 2$. Assume that the statement holds for all $X,Y$ and $p+q\leq \ell-1$. Consider $i_{p}:\Delta_{p}\to\Delta_{p}$ and $i_{q}:\Delta_{q}\to\Delta_{q}$ simplices and define: $$\eta:=\partial i_{p}\times i_{q}+(-1)^p i_{p}\times \partial i_{q}\in S_{\ell-1}(\Delta_{p}\times\Delta_{q})$$which is already defined. Then, by Leibniz$$\begin{align}\partial \eta&=\underbrace{ \partial \partial i_{p} }_{ =0 }\times i_{q}+(-1)^{p-1}\partial i_{p}\times \partial i_{q}+(-1)^p(\partial i_{p}\times \partial i_{q}+(-1)^p(i_{p}\times \underbrace{ \partial \partial i_{q} }_{ =0 }))\\&=0\end{align}$$Therefore, $\eta\in Z_{\ell-1}(\Delta _{p}\times\Delta_{q})$. However, as $\Delta_{p}\times\Delta_{q}$ is contractible, $$Z_{\ell-1}(\Delta _{p}\times\Delta_{q}) / B_{\ell-1}(\Delta _{p}\times\Delta_{q}) = H_{\ell-1}(\Delta_{p}\times\Delta_{q})=0$$ and $\eta\in B_{\ell-1}(\Delta_{p}\times\Delta_{q})$. Hence, there exists $i_{p}\times i_{q}\in S_{\ell}(\Delta_{p}\times\Delta_{q})$ s.t. $\partial(i_{p}\times i_{q})=\eta$.
> 	    
> 	    Now, for $\sigma:\Delta_{p}\to X$ and $\tau:\Delta_{q}\to Y$, we define $$\sigma \times \tau:=(\sigma \times \tau)_{c}(i_{p}\times i_{q})$$
> 	    Firstly, this is well-defined as for $X=\Delta_{p}$ and $Y=\Delta_{q}$, $i_{p}\times i_{q}=(i_{p}\times i_{q})_{c}(i_{p}\times i_{q})$.
> 	    
> 	    We are left to show that 2 and 3 hold. 
> 		   1. for $f:X\to X'$ and $g:Y\to Y'$, $$(f\times g)_{c}(\sigma \times \tau)=(f\times g)_{c}\circ (\sigma \times \tau)_{c}(i_{p}\times i_{q})=(f\circ \sigma)\times(g \circ  \tau)=f_{c}(\sigma)\times g_{c}(\tau)$$
> 		   2. we have: $$\begin{align}\partial(\sigma \times \tau)&=\partial((\sigma \times \tau)_{c}(i_{p}\times i_{q}))=(\sigma \times \tau)_{c}(\partial(i_{p}\times i_{q}))\\&=(\sigma \times \tau)_{c}\left( \partial i_{p}\times i_{q}+(-1)^p i_{p}\times \partial i_{q} \right)\\&=\sigma_{c}(\partial i_{p})\times \tau_{c}(i_{q})+(-1)^p\sigma_{c}(i_{p})\times \tau_{c}(\partial i_{q}) \\&=\partial\sigma_{c}( i_{p})\times \tau_{c}(i_{q})+(-1)^p\sigma_{c}(i_{p})\times \partial \tau_{c}(i_{q})\\&=\partial\sigma \times \tau+(-1)^p\sigma \times \partial \tau \end{align}$$where $\sigma_{c}(i_{p})=\sigma \circ i_{p}=\sigma$ and $\tau_{c}(i_{q})=\tau$.
---
> [!lemma] Theorem 3
> The singular homology $H(\cdot;G)$ is a [[homology theory]] with coefficient group $G$.

> [!proof]+
> 
---
