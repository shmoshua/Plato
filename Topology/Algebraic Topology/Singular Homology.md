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

> [!proof]-
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
> [!lemma] Theorem 4 (Relative Cross Product)
> For $X,Y$ topological spaces and $A\subseteq X,B\subseteq Y$ subspaces,
> $$\times:S_{p}(X,A)\times S_{q}(Y,B)\to S_{p+q}(X\times Y,(X\times B)\cup (A\times Y)),\quad([a],[b])=[a\times b]$$is a cross product, i.e. extends the three properties. 

> [!proof]-
> We first show that this is well-defined.
> 1. Let $a-a'\in S_{p}(A)$ and $b-b'\in S_{q}(B)$, $$\begin{align}a\times b-a'\times b'&=(a-a'+a')\times (b-b'+b')-a'\times b'\\&=\underbrace{ (a-a') \times(b-b') }_{ \in S_{p+q}(A\times B) }+\underbrace{ (a-a')\times b' }_{ \in S_{p+q}(A\times Y) }+\underbrace{ a'\times(b-b') }_{ \in S_{p+q}(X\times B) }\in S_{p+q}((X\times B)\cup (A\times Y))\end{align}$$
> 2. For continuous maps $f:(X,A)\to(X,A')$ and $g:(Y,B)\to(Y',B')$, we have that for all $[a]\in S_{p}(X,A)$ and $[b]\in S_{p}(Y,B)$, $$\begin{align}(f\times g)_{c}([a]\times [b])=(f\times g)_{c}[a\times b]=[f_{c}(a)\times g_{c}(b)]\end{align}$$
---
> [!lemma] Theorem 4
> Let $X$ be a topological space and $\mathcal{U}:=\{ U_{\alpha} \}_{\alpha\in \mathcal{A}}$ be a collection of subsets of $X$ s.t. $\{ U_{\alpha}^\circ \}_{\alpha\in \mathcal{A}}$ is a covering of $X$. We say that $Q\subseteq X$ is $\mathcal{U}$-small, if there exists $\alpha\in \mathcal{A}$ with $Q\subseteq U_{\alpha}$. Let: $$S^\mathcal{U}_{p}(X):=\left\{  \sum_{\sigma}^{}n_{\sigma}\sigma: \sigma(\Delta_{p})\text{ is }\mathcal{U}\text{-small}  \right\}\subseteq S_{p}(X)$$Then, $\partial(S_{p}^\mathcal{U}(X))\subseteq S_{p-1}^{\mathcal{U}}(X)$ as if $\sigma$ is $\mathcal{U}$-small then so is $\sigma^{(i)}$ for all $i\in[p]$. Therefore, $\mathcal{S}^{\mathcal{U}}(X)$ is a subcomplex of $\mathcal{S}(X)$. Let  be 
> 1. the inclusion $i^{\mathcal{U}}:\mathcal{S}^\mathcal{U}(X)\to \mathcal{S}(X)$ induces an isomorphism $i^\mathcal{U}_{*}:H_{p}(\mathcal{S}^\mathcal{U}(X))\to H_{p}(X)$

> [!proof]+
> Consider $\Delta_{q}\subseteq \mathbb{R}^{q+1}$. Let $L_{p}(\Delta_{q})\subseteq S_{p}(\Delta_{q})$ defined as the subgroup generated by affine singular $p$-simplices, i.e. $\sigma:\Delta_{p}\to\Delta_{q}$ where $\sigma=[v_{0},\dots,v_{p}]$ with $v_{0},\dots,v_{p}\in \Delta_{q}$ s.t.: $$\sigma\left( \sum_{i=0}^{p}\lambda_{i}e_{i} \right)=\sum_{i=0}^{p}\lambda_{i}v_{i}$$Then, $\partial\sigma=\sum_{j=0}^{p}(-1)^j\sigma^{(j)}=\sum_{j=0}^{p}(-1)^j[v_{0},\dots,\widehat{v_{j}},\dots,v_{p}]\in L_{p-1}(\Delta_{q})$ and $\mathcal{L}(\Delta_{q})\subseteq \mathcal{S}(\Delta_{q})$ is a subcomplex. 
> 
> Now, we define the cone operator. Fix $v\in \Delta_{q}$. For $\sigma=[v_{10},\dots,v_{p}]:\Delta_{p}\to\Delta_{q}$ an affine $p$-simplex, the cone of $\sigma$ is defined as: $v\sigma:=[v,v_{0},\dots,v_{p}]:\Delta_{p+1}\to\Delta_{q}$. Extending this linearly, we get that $L_{p}(\Delta_{q})\to L_{p+1}(\Delta_{q}),c\mapsto vc$ is a homomorphism. 
> 1. **Claim 1**: For all $c\in L_{p}(\Delta_{q})$, $\partial(vc)=\begin{cases}c-v(\partial c)&p>0\\c-\varepsilon(c)v&p=0\end{cases}$ where $\varepsilon:S_{0}(\Delta_{q})\to \mathbb{Z}$ is the augmenting map. 
> 	- For $p>0$, we have for $\sigma=[v_{0},\dots,v_{p}]$, $$\begin{align}\partial(v\sigma)&=\partial[v,v_{0},\dots,v_{p}]\\&=[v_{0},\dots,v_{p}]-\sum_{i=0}^{p}(-1)^i[v,v_{0},\dots,\widehat{v_{i}},\dots,v_{p}]\\&=\sigma-v(\partial\sigma)\end{align}$$by linearly extending the result, we have the statement for $p>0$.
> 	- If $p=0$, $\partial(v\sigma)=\partial([v,v_{0}])=\sigma-v$. Therefore, $$\begin{align}\partial\left( v\sum_{\sigma}n_{\sigma}\sigma \right)=\partial\left( \sum_{\sigma}^{}n_{\sigma}v\sigma \right)=\sum_{\sigma}^{}n_{\sigma}(\sigma-v)=c-\sum_{\sigma}^{}n_{\sigma}v=c-\varepsilon(c)v\end{align}$$
> 
> We now, define a homomorphism $\gamma:L_{p}(\Delta_{q})\to L_p(\Delta_{q})$ defined inductively as follows:
> 1. for $p=0$, $\gamma(c)=c$ for all $c\in L_{0}(\Delta_{q})$
> 2. for $p\geq 1$, let $\sigma\in L_{p}(\Delta_{q})$. Then, $\gamma(\sigma):=\sigma_{B}\gamma(\partial\sigma)$ where $\sigma_{B}:=\frac{1}{p+1}\sum_{i=0}^{p}v_{i}\in \Delta_{q}$. 
> 
> We have that:
> 1. **Claim 2**: $\gamma$ is a chain map. 
> 	- If $p=0$, $\gamma(\partial\sigma)=\gamma(0)=0$ and $\partial(\gamma(\sigma))=\partial\sigma=0$.
> 	- If $p=1$, $\gamma(\partial\sigma)=\partial\sigma$ and $$\partial(\gamma(\sigma))=\partial(\sigma_{B}\gamma(\partial\sigma))=\partial(\sigma_{B}\partial\sigma)=\partial\sigma-\sigma_{B}(\partial \partial\sigma)=\partial\sigma$$
> 	- If $p\geq 2$, assume the statement holds for $\leq p-1$. Then, $$\partial(\gamma(\sigma))=\partial(\sigma_{B}\gamma(\partial\sigma))=\gamma(\partial\sigma)-\sigma_{B}(\partial \gamma(\partial\sigma))=\gamma(\partial\sigma)-\sigma_{B}(\gamma(\underbrace{ \partial \partial\sigma }_{ =0 }))=\gamma(\partial\sigma)$$
> 2. **Claim 3**: $\gamma$ is chain homotopic to $\text{id}$. 
>    Define $T:L_{p}(\Delta_{q})\to L_{p+1}(\Delta_{q})$ inductively: 
> 	   - If $p=0$, $T=0$.
> 	   - If $p\geq 1$ and $T$ is defined for $\leq p-1$, then for $\sigma:\Delta_{p}\to\Delta_{q}$ affine singular simplex, $$T(\sigma):=\sigma_{B}()$$
>    

- **Corollary**: For $\mathcal{S}^\mathcal{U}(X,A):=\mathcal{S}^\mathcal{U}(X) / \mathcal{S}^{\mathcal{U}\cap A}(A)$, $i:\mathcal{S}^\mathcal{U}(X,A)\to \mathcal{S}(X,A)$ induces an isomorphism in homology as: $0\to \mathcal{S}^{\mathcal{U}\cap A}(A)\to \mathcal{S}^\mathcal{U}(X)\to \mathcal{S}^\mathcal{U}(X,A)\to 0$ is a SES and by [[Chain Complex|Theorem 3]] and [[Exact Sequence|5-lemma]], we have that the middle map is an isomorphism.
 ```tikz
\usepackage{tikz-cd}\begin{document}\begin{tikzcd} [column sep=tiny]{...} & {H_{p}(\mathcal{S}^{\mathcal{U}\cap A}(A))} & {H_{p}(\mathcal{S}^\mathcal{U}(X))} & {H_{p}(\mathcal{S}^{\mathcal{U}}(X,A))} & {H_{p-1}(\mathcal{S}^{\mathcal{U}\cap A}(A))} & {H_{p-1}(\mathcal{S}^\mathcal{U}(X))} & {...} \\ {...} & {H_p(A)} & {H_p(X)} & {H_p(X,A)} & {H_{p-1}(A)} & {H_{p-1}(X)} & {...} \arrow[from=1-1, to=1-2] \arrow[from=1-2, to=1-3] \arrow["{i_*}"', from=1-2, to=2-2] \arrow[from=1-3, to=1-4] \arrow["{i_*}"', from=1-3, to=2-3] \arrow[from=1-4, to=1-5] \arrow[from=1-4, to=2-4] \arrow[from=1-5, to=1-6] \arrow["{i_*}"', from=1-5, to=2-5] \arrow[from=1-6, to=1-7] \arrow["{i_*}"', from=1-6, to=2-6] \arrow[from=2-1, to=2-2] \arrow[from=2-2, to=2-3] \arrow[from=2-3, to=2-4] \arrow[from=2-4, to=2-5] \arrow[from=2-5, to=2-6] \arrow[from=2-6, to=2-7]\end{tikzcd}
\end{document} 
```

	
> 

---
> [!lemma] Theorem 3
> The singular homology $H(\cdot;G)$ is a [[homology theory]] with coefficient group $G$.

> [!proof]-
> We have that:
> 1. **Homotopy invariance**: Let $I:\Delta_{1}\to I$ be a 1-simplex to $I:=[0,1]$ that sends $(1,0)$ to $0$ and $(0,1)$ to $1$. Now, let $\varepsilon_{0},\varepsilon_{1}$ be $0$-simplices in $I$ s.t. $\varepsilon_{0}(e_{0})=0$ and $\varepsilon_{0}(e_{1})=1$. Then, 
> 	1. $\partial I=\varepsilon_{1}-\varepsilon_{0}$
> 	
> 	For a topological space $X$, we will now construct a [[chain homotopy]] $$D:S_{p}(X)\to S_{p+1}(I\times X),\quad c\mapsto I\times c$$Then, $$\begin{align}(\partial D+D\partial)c&=\partial(I\times c)+D(\partial c)=\partial I\times c-I\times \partial c+I\times \partial c=\varepsilon_{1}\times c-\varepsilon_{0}\times c\end{align}$$
> 	
> 	Now, if we define $\eta_{0},\eta_{1}:X\to I\times X$ with $\eta_{0}(x):=(0,x)$ and $\eta_{1}(x):=(1,x)$ for all $x\in X$, we have that $(\eta_{1})_{c}\left( \sum_{\sigma}n_{\sigma}\sigma  \right)(x)=\sum_{\sigma}^{}n_{\sigma}(\eta_{1}\circ\sigma)(x)=\sum_{\sigma}^{}n_{\sigma}(1,\sigma(x))=\sum_{\sigma}^{}n_{\sigma}(\varepsilon_{1}\times \sigma)(x)$
> 	$$(\partial D+D\partial)c=\varepsilon_{1}\times c-\varepsilon_{0}\times c=(\eta_{1})_{c}(c)-(\eta_{0})_{c}(c)$$Therefore, $(\eta_{1})_{c}\sim (\eta_{0})_{c}$. 
> 	
> 	Hence, for $f_{0},f_{1}:(X,A)\to(Y,B)$ be continuous with $f_{1}\sim f_{0}$, we have a homotopy $F:(I,\varnothing)\times(X,A)\to (Y,B)$ and we have that $F\circ \eta_{0}=f_{0}$ and $F \circ \eta_{1}=f_{1}$. We have that: $$F_{c}:S_{p}(I\times X,I\times A)\to S_{p}(Y,B)$$and: $$\begin{align}\partial \circ (F_{c}\circ D)+(F_{c} \circ  D) \circ  \partial&=F_{c}\circ (\partial D+D\partial)\\&=F_{c}\circ ((\eta_{1})_{c}-(\eta_{0})_{c})\\&=(f_{1})_{c}-(f_{0})_{c}\end{align}$$As $F_{c}\circ D:S_{p}(X,A)\to S_{p+1}(Y,B)$ is a chain homotopy, $(f_{1})_{c}\sim(f_{0})_{c}$. The statement follows from [[Chain Homotopy|Proposition 1]].
> 2. **Excision**: Let $X$ be a topological space and $B\subseteq A\subseteq X$ s.t. $\overline{B}\subseteq A^\circ$. Then, take $\mathcal{U}:=\{ A,X \backslash B \}$ whose interiors form a cover. Indeed, $$A^\circ \cup (X \backslash B)^\circ =A^\circ \cup X \backslash \overline{B} \supseteq A^\circ  \cup X \backslash A^\circ =X$$Then, we have by [[Group Homomorphism|Second isomorphism theorem]]: $$\begin{align}S_{p}(X \backslash B) / S_{p}(A \backslash B)&=S_{p}(X \backslash B) / S_{p}(A )\cap S_{p}(X \backslash B)\\&\cong (S_{p}(X \backslash B)+S_{p}(A)) / S_{p}(A)=S_{p}^{\mathcal{U}}(X) / S_{p}(A)\end{align}$$Let $\psi:S_{p}(X \backslash B) / S_{p}(A \backslash B)\to S_{p}^{\mathcal{U}}(X) / S_{p}(A)$ be such an isomorphism. Further, let $\varphi:S_{p}^{\mathcal{U}}(X) / S_{p}(A) \to S_{p}(X) / S_{p}(A)$ be the inclusion. Then, for $k:=\varphi \circ\psi$ given by the inclusion, we have that: $k_{*}:= \varphi_{*}\circ\psi_{*}$ where $\varphi_{*}$ is an isomorphism by the previous corollary and $\psi_{*}$ is an isomorphism. Hence, $k_{*}$ is an isomorphism. 
---
