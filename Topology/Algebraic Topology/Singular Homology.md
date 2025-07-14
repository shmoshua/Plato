#Definition #AlgebraicTopology 

> [!definition]
> Let $G$ be an [[abelian group]]. A ***singular homology*** $H(\cdot;G)$ with [[Homology Theory|coefficients group]] $G$ is defined as follows. For $X$ a [[topological space]]:
> 1. $\mathcal{S}(X;G)$ is the graded abelian group with $S_{p}(X;G):=S_{p}(X)\otimes G=\bigoplus_{\sigma:\Delta_{p}\to X}G\sigma$.
> 2. $\partial:S_{p}(X;G)\to S_{p-1}(X;G)$ extending $\partial(g\sigma):=\sum_{i=0}^{p}(-1)^ig \sigma \circ F_{i}^p$ where for all [[p-Simplex|singular $p$-simplex]] $\sigma:\Delta_{p}\to X$:$$(-1)^ig:=\begin{cases}g&i\text{ is even}\\-g&i\text{ is odd}\end{cases}$$and $F_{i}^p:\Delta_{i-1}\to\Delta_{i}$ is the [[p-Simplex|$i$-th face map]].
> 3. $H_{p}(X,G):=H_{p}(\mathcal{S}(X;G))$ and for $A\subseteq X$, $H_{p}(X,A;G):=H_{p}(\mathcal{S}(X,A;G))$ where $\mathcal{S}(X,A;G):=\mathcal{S}(X;G) / \mathcal{S}(A;G)$.

^d74b64

---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\partial^{2}=0$, i.e. $\mathcal{S}(X;G)$ is a [[chain complex]].
> 2. For a point space $X$, $$H_{i}(X;G)\cong\begin{cases}G&i=0\\0&i\neq 0\end{cases}$$

^1724cc

> [!proof]-
> We have:
> 1. Follows from [[p-Simplex|boundary lemma]].
> 2. We have that the only singular $p$-simplex $\sigma_{p}:\Delta_{p}\to X$ is the constant map. Therefore, $S_{p}(X;G)\cong G$. 
>    
>    Now, for $p> 0$, we have that for $p$-simplex $\sigma:\Delta_{p}\to X$: $$\partial (g\sigma)=\begin{cases}0&p\text{ is odd}\\g\sigma_{p-1}&p\text{ is even}\end{cases}$$Hence, $$\text{ker }\partial \cong\begin{cases}G&p>0\text{ odd or }p=0\\0&\text{otherwise}\end{cases}$$
>    $$B_{p}(X;G) \cong\begin{cases}G&p>0\text{ odd}\\0&\text{otherwise}\end{cases}$$It follows that $H_{p}(X;G)\cong G$ if and only if $p=0$ and $0$ otherwise. 

^249113

---
> [!lemma] Theorem 2
> Let $X$ be a [[contractible space]]. Then, $H_{n}(X)=0$ for all $n\neq 0$.

^68ac5e

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

^d700de

---
> [!lemma] Theorem 3 (Cross Product)
> Let $X,Y$ be topological spaces. There exists a family of bilinear map $$\times:S_{p}(X)\times S_{q}(Y)\to S_{p+q}(X\times Y),\quad \forall p,q\geq 0,X,Y$$with the following properties:
> 1. For all $x\in X$ and $y\in Y$, $\sigma:\Delta_{p}\to X$ and $\tau:\Delta_{q}\to Y$ simplices, we have that: $$\sigma \times y:\Delta_{p}\to X\times Y, \quad w\mapsto (\sigma(w),y),\quad x \times \tau:\Delta_{q}\to X\times Y, \quad w\mapsto (x,\tau(w))$$
> 2. For continuous maps $f:X\to X'$ and $g:Y\to Y'$,  $f\times g:X\times Y\to X'\times Y'$ satisfies: $$(f\times g)_{c}(a\times b)=f_{c}(a)\times g_{c}(b),\quad \forall a\in S_{p}(X),b\in S_{q}(Y)$$
> 3. Leibniz Formula: $$\partial(a\times b)=\partial a\times b+(-1)^pa\times \partial b,\quad \forall a\in S_{p}(X),b\in S_{q}(Y) $$

^03772e

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

^97a53f

---
> [!lemma] Theorem 4 (Relative Cross Product)
> For $X,Y$ topological spaces and $A\subseteq X,B\subseteq Y$ subspaces,
> $$\times:S_{p}(X,A)\times S_{q}(Y,B)\to S_{p+q}(X\times Y,(X\times B)\cup (A\times Y)),\quad([a],[b])=[a\times b]$$is a cross product, i.e. extends the three properties. 

^6ff457

> [!proof]-
> We first show that this is well-defined.
> 1. Let $a-a'\in S_{p}(A)$ and $b-b'\in S_{q}(B)$, $$\begin{align}a\times b-a'\times b'&=(a-a'+a')\times (b-b'+b')-a'\times b'\\&=\underbrace{ (a-a') \times(b-b') }_{ \in S_{p+q}(A\times B) }+\underbrace{ (a-a')\times b' }_{ \in S_{p+q}(A\times Y) }+\underbrace{ a'\times(b-b') }_{ \in S_{p+q}(X\times B) }\in S_{p+q}((X\times B)\cup (A\times Y))\end{align}$$
> 2. For continuous maps $f:(X,A)\to(X,A')$ and $g:(Y,B)\to(Y',B')$, we have that for all $[a]\in S_{p}(X,A)$ and $[b]\in S_{p}(Y,B)$, $$\begin{align}(f\times g)_{c}([a]\times [b])=(f\times g)_{c}[a\times b]=[f_{c}(a)\times g_{c}(b)]\end{align}$$

^cbd460

---
> [!lemma] Theorem 4
> Let $X$ be a topological space and $\mathcal{U}:=\{ U_{\alpha} \}_{\alpha\in \mathcal{A}}$ be a collection of subsets of $X$ s.t. $\{ U_{\alpha}^\circ \}_{\alpha\in \mathcal{A}}$ is a covering of $X$. We say that $Q\subseteq X$ is $\mathcal{U}$-small, if there exists $\alpha\in \mathcal{A}$ with $Q\subseteq U_{\alpha}$. Let: $$S^\mathcal{U}_{p}(X):=\left\{  \sum_{\sigma}^{}n_{\sigma}\sigma: \sigma(\Delta_{p})\text{ is }\mathcal{U}\text{-small}  \right\}\subseteq S_{p}(X)$$Then, $\partial(S_{p}^\mathcal{U}(X))\subseteq S_{p-1}^{\mathcal{U}}(X)$ as if $\sigma$ is $\mathcal{U}$-small then so is $\sigma^{(i)}$ for all $i\in[p]$. Therefore, $\mathcal{S}^{\mathcal{U}}(X)$ is a subcomplex of $\mathcal{S}(X)$. Let  be 
> 1. the inclusion $i^{\mathcal{U}}:\mathcal{S}^\mathcal{U}(X)\to \mathcal{S}(X)$ induces an isomorphism $i^\mathcal{U}_{*}:H_{p}(\mathcal{S}^\mathcal{U}(X))\to H_{p}(X)$

^89608f

> [!proof]-
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
> 	   - If $p\geq 1$ and $T$ is defined for $\leq p-1$, then for $\sigma:\Delta_{p}\to\Delta_{q}$ affine singular simplex, $$T(\sigma):=\sigma_{B}(\gamma(\sigma)-\sigma-T(\partial\sigma))$$
> 
> 	Then, we show that $\partial T+T\partial=\gamma-\text{id}$.
> 	- If $p=0$, $\partial T(\sigma)+T(\partial\sigma)=0$ and $\gamma(\sigma)-\text{id}(\sigma)=\sigma-\sigma=0$.
> 	- If $p\geq1$, then: $$\begin{align}\partial(T\sigma)&=\partial(\sigma_{B}(\gamma(\sigma)-\sigma-T(\partial\sigma)))=\gamma(\sigma)-\sigma-T(\partial\sigma)-\sigma_{B}(\partial(\gamma(\sigma)-\sigma-T(\partial\sigma)))\\&=\gamma(\sigma)-\sigma-T(\partial\sigma)-\sigma_{B}(\partial\gamma(\sigma)-\partial\sigma-\gamma(\partial\sigma)+\partial\sigma +T(\partial \partial\sigma))\\&=\gamma(\sigma)-\sigma-T(\partial\sigma)-\sigma_{B}(0)\\&=\gamma(\sigma)-\sigma -T(\partial\sigma)\end{align}$$ 
> 
> Now, we can linearly extend $\gamma$ and $T$ to $S_{p}(X)$. Let $\sigma:\Delta_{p}\to X$ be a singular $p$-simplex and $i_{p}:\Delta_{p}\to\Delta_{p}$ be the identity viewed as a $p$-simplex. Then, we define:
> 1. $\gamma(\sigma):=\sigma_{c}(\gamma(i_{p}))$ and 
> 2. $T(\sigma):=\sigma_{c}(T(i_{p}))$
> 
> and extend the functions linearly. We have that:
> 1. **Claim 4**: For $X:=\Delta_{q}$, $\gamma$ and $T$ coincides with the old definition on $L^p(\Delta_{q})$. 
>    Let $\sigma=[v_{0},\dots,v_{p}]$. Then, fix $q\geq 0$. We will show that $\sigma_{c}$ commutes with $\gamma_{\text{old}}$ and with $T_{\text{old}}$.
>    1. If $p=0$, then: $\sigma_{c}(\gamma(\tau))=\sigma_{c}(\tau)=\gamma(\sigma_{c}(\tau))$ and $\sigma_{c}(T(\tau))=0=T(\sigma_{c}(\tau))$.
>    2. If $p\geq 1$, then: $$\begin{align}\sigma_{c}(\gamma_{\text{old}}(\tau))&=\sigma_{c}(\tau_{B}\gamma_{\text{old}}(\partial \tau))=(\sigma_{c}(\tau))_{B}\sigma_{c}\gamma_{\text{old}}(\partial \tau)=(\sigma_{c}(\tau))_{B}\gamma_{\text{old}}(\sigma_{c}(\partial \tau))\\&=(\sigma_{c}(\tau))_{B}\gamma_{\text{old}}(\partial (\sigma_{c}(\tau)))=\gamma_{\text{old}}(\sigma_{c}(\tau))\end{align}$$$$\begin{align}\sigma_{c}(T_{\text{old}}(\tau))&=\sigma_{c}(\tau_{B}(\gamma(\tau)-\tau-T(\partial \tau)))=(\sigma_{c}(\tau))_{B}\sigma_{c}(\gamma(\tau)-\tau-T(\partial \tau))\\&=(\sigma_{c}(\tau))_{B}(\gamma(\sigma_{c}\tau)-\sigma_{c}\tau-T(\partial\sigma_{c} \tau) )=T(\sigma_{c}\tau)\end{align}$$
>   
> 	  Therefore, $\sigma_{c}(\gamma(i_{p}))=\gamma(\sigma_{c}i_{p})=\gamma(\sigma)$ and $\sigma_{c}(T(i_{p}))=T(\sigma_{c}(i_{p}))=T(\sigma)$.
> 2. **Claim 5**: (Naturality) for $f:X\to Y$, $\gamma(f_{c}(c))=f_{c}(\gamma(c))$ and $T(f_{c}(c))=f_{c}(T(c))$ for all $c\in S_{p}(X)$. 
>    For $\sigma:\Delta_{p}\to X$ a singular $p$-simplex, $$f_{c}(\gamma(\sigma))=f_{c}(\sigma_{c}(\gamma(i_{p})))=(f\circ \sigma)_{c}(\gamma(i_{p}))=\gamma(f \circ  \sigma)=\gamma(f_{c}(\sigma))$$$$f_{c}(T(\sigma))=f_{c}(\sigma_{c}(T(i_{p})))=T(f\circ \sigma)=T(f_{c}(\sigma))$$
> 3. **Claim 6**: $\gamma$ is a chain map and is chain homotopic to $\text{id}$ via $T$. 
>    We have that for $\sigma:\Delta_{p}\to\Delta_{q}$ a singular $p$-simplex, $$\begin{align}\gamma(\partial\sigma)&=\gamma(\sigma_{c}\partial i_{p})=\sigma_{c}(\gamma(\partial i_{p}))=\sigma_{c}(\partial\gamma(i_{p}))=\partial(\sigma_{c}(\gamma(i_{p})))=\partial\gamma(\sigma)\end{align}$$Further, $$\begin{align}(T\partial+\partial T)(\sigma)&=T(\sigma_{c}\partial i_{p})+\partial(\sigma_{c}(T(i_{p})))=\sigma_{c}(T(\partial i_{p})+\partial(T(i_{p})))=\sigma_{c}(\gamma(i_{p})-i_{p})\\&=\gamma(\sigma)-\sigma\end{align}$$
> 
> Further $\gamma(\sigma)$ and $T(\sigma)$ have their images in $\text{im}(\sigma)$ by $\sigma_{c}$ in the definition. 
> 1. **Claim 7**: For $k\geq 1$, $\gamma^k:\mathcal{S}(X)\to \mathcal{S}(X)$ is chain homotopic to $\text{id}$ via $T_{k}$ which is natural w.r.t. maps.  
>    We have: $$\begin{align}\gamma^k-\text{id}&=\underbrace{ (\gamma^{k-1}+\dots+\gamma+\text{id}) }_{ =:G }(\gamma-\text{id})=G\circ (\gamma-\text{id})=G\circ (T\partial+\partial T)\\&=(G\circ T)\circ \partial+\partial \circ  (G\circ T)\end{align}$$Hence, by defining $T_{k}:=G\circ T$, we have the statement where the naturality follows from $\gamma$ and $T$. 
> 2. **Claim 8**: Let $\sigma:\Delta_{p}\to\Delta_{q}$ be an affine simplex. Then, any simplex in $\gamma(\sigma)$ has diameter $\leq \frac{p}{p+1}\text{diag}(\sigma)$.
>    Let $\sigma$ be an affine simplex. Then, $\gamma(\sigma)=\sigma_{B}(\gamma(\partial\sigma))$ and any simplex in $\gamma(\sigma)$ is given by $\sigma_{B}(\tau)$ where $\tau$ is in $\gamma(\partial\sigma)$. By recursively continuing we get that any simplex $\lambda$ that is in $\gamma(\sigma)$ has the form: $$\lambda:=[(\sigma_{0})_{B},(\sigma_{1})_{B},\dots,(\sigma_{p})_{B}]$$where $\sigma_{0}=\sigma$ and $\sigma_{i}$ is a proper face of $\sigma_{i-1}$, i.e. $\sigma_{i-1}^{(j)}=\sigma_{i}$ for some $j$. Then, for $i\leq j$, the vertices of $\sigma_{j}$ is a subset of $\sigma_{i}$ and we have that by [[Technical Lemmas|Lemma 4]]: $$\left| (\sigma_{i})_{B}-(\sigma_{j})_{B} \right| \leq \frac{p}{p+1}\text{diam}(\sigma_{i}) \leq \frac{p}{p+1}\text{diam}(\sigma) $$and $\text{diam}(\lambda)=\max_{i,j}\left| (\sigma_{i})_{B}-(\sigma_{j})_{B} \right|\leq \frac{p}{p+1}\text{diam}(\sigma)$.
> 
> Therefore, every affine simplex $\lambda$ in $\gamma^k(\sigma)\in L_{p}(\Delta_{q})$ has diameter $\text{diam}(\lambda)\leq (\frac{p}{p+1})^k\text{diam}(\Delta_{q})$ and the diameter of every simplex in $\gamma^k(\sigma)$ converges to 0.
> 
> Now, let $\sigma:\Delta_{p}\to X$ be a singular $p$-simplex. Then, $$\gamma^k(\sigma)=\gamma^{k-1}\circ \sigma_{c} \circ \gamma(i_{p})=\sigma_{c}(\gamma^k(i_{p}))$$Let $V_{\alpha}:=\sigma ^{-1}(U_{\alpha}^\circ)$ for all $\alpha\in \mathcal{A}$, which is then an open covering of $\Delta_{p}$. As $\Delta_{p}$ is compact metric, by [[Compact Space|Lebesgue Covering Lemma]] there exists $\delta>0$ s.t. for every $S\subseteq \Delta_{p}$ with $\text{diam}(S)<\delta$ there exists $\alpha\in \mathcal{A}$ with $S\subseteq V_{\alpha}$. 
> 
> By choosing $k$ s.t. every affine simplex $\lambda$ in $\gamma^k(\sigma)$ has diameter $\text{diam}(\lambda)< \delta$, we have that every such $\lambda$ is $\mathcal{U}$-small, i.e. $\gamma^k(\sigma)\in S^\mathcal{U}_{p}(X)$. 
> 
> Now, it's only left to show that $i^\mathcal{U}$ induces an isomorphism in homology. 
> 1. We first show that $i^\mathcal{U}_{*}$ is injective: Let $c\in S^\mathcal{U}_{p}(X)$ is a cycle, i.e. $\partial c=0$. Now, assume that $c=\partial e$ for some $e\in S_{p+1}(X)$. We need to show that $c=\partial e'$ for $e'\in S^\mathcal{U}_{p+1}(X)$.
>    
>    We first choose $k$ s.t. $\gamma^k(e)\in S^\mathcal{U}_{p+1}(X)$. Let $e':=\gamma^k(e)-T_{k}(c)\in S^\mathcal{U}_{p+1}(X)$. Then, $$\partial e'=\partial\gamma^k(e)-\partial T_{k}(c)=\partial\gamma^k(e)+T_{k}\underbrace{ \partial \partial e }_{ =0 }+c-\gamma^k(\partial e)=c$$This proves the injectivity.
> 2. For surjectivity, let $c\in S_{p}(X)$ be a cycle. We need to show that there exists $c'\in S^\mathcal{U}_{p}(X)$ s.t. $c$ and $c'$ are homologous in $S_{p}(X)$. 
>    
>    Let $k$ s.t. $\gamma^k(c)\in S^\mathcal{U}_{p}(X)$. Then, $$\gamma^k(c)-c=\partial T_{k}(c)+T_{k}\underbrace{ \partial(c) }_{ 0 }=\partial T_{k}(c)$$By taking $c':=\gamma^k(c)$, we have the surjectivity.
>    
>    

^7f1d9b

- **Corollary**: For $\mathcal{S}^\mathcal{U}(X,A):=\mathcal{S}^\mathcal{U}(X) / \mathcal{S}^{\mathcal{U}\cap A}(A)$, $i:\mathcal{S}^\mathcal{U}(X,A)\to \mathcal{S}(X,A)$ induces an isomorphism in homology as: $0\to \mathcal{S}^{\mathcal{U}\cap A}(A)\to \mathcal{S}^\mathcal{U}(X)\to \mathcal{S}^\mathcal{U}(X,A)\to 0$ is a SES and by [[Chain Complex|Theorem 3]] and [[Exact Sequence|5-lemma]], we have that the middle map is an isomorphism. ^165d4d
 ```tikz
\usepackage{tikz-cd}\begin{document}\begin{tikzcd} [column sep=tiny]{...} & {H_{p}(\mathcal{S}^{\mathcal{U}\cap A}(A))} & {H_{p}(\mathcal{S}^\mathcal{U}(X))} & {H_{p}(\mathcal{S}^{\mathcal{U}}(X,A))} & {H_{p-1}(\mathcal{S}^{\mathcal{U}\cap A}(A))} & {H_{p-1}(\mathcal{S}^\mathcal{U}(X))} & {...} \\ {...} & {H_p(A)} & {H_p(X)} & {H_p(X,A)} & {H_{p-1}(A)} & {H_{p-1}(X)} & {...} \arrow[from=1-1, to=1-2] \arrow[from=1-2, to=1-3] \arrow["{i_*}"', from=1-2, to=2-2] \arrow[from=1-3, to=1-4] \arrow["{i_*}"', from=1-3, to=2-3] \arrow[from=1-4, to=1-5] \arrow[from=1-4, to=2-4] \arrow[from=1-5, to=1-6] \arrow["{i_*}"', from=1-5, to=2-5] \arrow[from=1-6, to=1-7] \arrow["{i_*}"', from=1-6, to=2-6] \arrow[from=2-1, to=2-2] \arrow[from=2-2, to=2-3] \arrow[from=2-3, to=2-4] \arrow[from=2-4, to=2-5] \arrow[from=2-5, to=2-6] \arrow[from=2-6, to=2-7]\end{tikzcd}
\end{document} 
```

^5d7b19

	
> 

---
> [!lemma] Theorem 3
> The singular homology $H(\cdot;G)$ is a [[homology theory]] with coefficient group $G$.

^1bc43d

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

^c1b606

---
> [!lemma] Theorem 4 (Mayer-Vietoris)
> Let $X$ be a topological space and $A,B\subseteq X$ s.t. $A^\circ\cup B^\circ=X$. Let $\mathcal{U}:=\{ A,B \}$. Further, $$i^A_:A\cap B\to A,\quad i^B:A\cap B\to B,\quad j^A:A\to X,\quad j^B:B\to X$$ be inclusions. Then, 
> 1. $0 \to \mathcal{S}(A\cap B)\xrightarrow{i^A_{c}\oplus i^B_{c}} \mathcal{S}(A)\oplus \mathcal{S}(B)\xrightarrow{j^A_{c}-j^B_{c}}\mathcal{S}^{\mathcal{U}}(X)\to 0$ is a SES of chain complexes.
> 2. There exists a LES given by: $$\dots\to H_{p}(A\cap B)\to H_{p}(A)\oplus H_{p}(B)\to H_{p}(X)\xrightarrow{\delta}H_{p-1}(A\cap B)\to\dots$$
> 3. if $A\cap B\neq \varnothing$, then $\delta(H_{1}(X))\subseteq \tilde{H}_{0}(A\cap B)$ and: $$\dots\to \tilde{H}_{p}(A\cap B)\to \tilde{H}_{p}(A)\oplus \tilde{H}_{p}(B)\to \tilde{H}_{p}(X)\xrightarrow{\delta}\tilde{H}_{p-1}(A\cap B)\to\dots$$

^39ff02

> [!proof]-
> We have that 
> 1. $i^A_{c}\oplus i^B_{c}$ is injective and $j^A_{c}-j^B_{c}$ is surjective. Now, let $a\in S_{p}(A)$ and $b\in S_{p}(B)$ s.t. $j^A_{c}(a)=j^B_{c}(b)$. Then, $a,b\in S_{p}(A\cap B)$ and $a=b$. Hence, $i^A_{c}\oplus i^B_{c}(a)=(a,b)$. This shows that $\text{ker }j^A_{c}-j^B_{c}\subseteq \text{im }i^A_{c}\oplus i^B_{c}$. The other inclusion is trivial.
> 2. Holds by 1, [[Chain Complex|Theorem 3]] and $H_{p}(\mathcal{S}^\mathcal{U}(X))\cong H_{p}(X)$ by Theorem 4.
> 3. Let $c\in S^\mathcal{U}_{1}(X)$ be a cycle. Then, $c=c^A-c^B$ with $c^A$ a chain with image in $A$ and $c^B$ in $B$. Consider $(\partial c^A,\partial c^B)$. Since $\partial c=0$, we have that $\partial c^A=\partial c^B\in S_{0}(A\cap B)$. 
>    
>    Then, $\varepsilon^A(\partial c^A)=0$ and $\varepsilon^{A\cap B}(\partial c^A)=0$. Therefore, $\delta(c)=[\partial c^A]$ is in the kernel of $\varepsilon^{A\cap B}$. Hence, $\delta(H_{1}(X))\subseteq \tilde{H}_{0}(A\cap B)$.
>    
>    To show that the exact sequence also holds in reduced homology, it suffices to show it for: $$\to H_{1}(X)\xrightarrow{\delta}\tilde{H}_{0}(A\cap B)\to \tilde{H}_{0}(A)\oplus \tilde{H}_{0}(B)\to \tilde{H}_{0}(X)\to 0$$
>    - **Exactness at $\tilde{H}_{0}(A\cap B)$**:
>     From 2, we have that $\text{im }\delta \subseteq \text{ker }i^A_{*}\oplus i^B_{*}$. Let $a\in \tilde{H}_{0}(A\cap B)$ s.t. $i^A_{*}\oplus i^B_{*}(a)=0$. Then, $a\in \text{im }\delta$ and we have the statement.
>    - **Exactness at $\tilde{H}_{0}(A)\oplus \tilde{H}_{0}(B)$**:
>      We have that $\text{im } i^A_{*}\oplus i^B_{*} \subseteq \text{ker }j^A_{*}-j^B_{*}$. Conversely, let $(a,b)\in \tilde{H}_{0}(A)\oplus \tilde{H}_{0}(B)$ s.t. $j^A_{*}(a)-j^B_{*}(b)=0$. Then, there exists $x\in H_{0}(A\cap B)$ with $i^A_{*}(x)=a$ and $i^B_{*}(x)=b$. However, $$\varepsilon_{*}(x)=\varepsilon_{*}(i^A_{*}\oplus  i^B_{*}(x))=(\varepsilon^A_{*}(a),\varepsilon^B_{*}(b))=0$$
>    - **Exactness at $\tilde{H}_{0}(X)$**:
>      To show that $j^A_{*}-j^B_{*}$ is surjective, let $x\in \tilde{H}_{0}(X)\subseteq H_{0}(X)$. Then, there exists $(a,b)\in H_{0}(A)\oplus H_{0}(B)$ with $j^A_{*}(a)-j^B_{*}(b)=x$. We now only have that: $$\varepsilon_{*}(a,b)=\varepsilon_{*}(j^A_{*}(a)-j^B_{*}(b))=\varepsilon_{*}(x)=0$$Hence, $(a,b)\in \tilde{H}_{0}(A)\oplus \tilde{H}_{0}(B)$.

^a3eb8e

---

> [!lemma] Proposition 5
> Let $\sigma_{n}:\Delta_n \to \Delta_{n} / \partial\Delta_{n}$ be the quotient map. Then,
> 1. $\sigma_{n}$ is a cycle in $\mathcal{S}(\Delta_{n} / \partial \Delta_{n}, *)$. 
> 2. $[\sigma_{n}]$ is a generator in $H_{n}(\Delta_{n} / \partial \Delta _{n}, *)\cong H_{n}(S^n, *)\cong \tilde{H}_{n}(S^n)\cong \mathbb{Z}$.
> 3. for any abelian group $G$, $$G\to H_{n}(\Delta_{n} / \partial \Delta_{n},*;G),\quad g\mapsto [g\sigma_{n}]$$is an isomorphism.

^22d01e

> [!proof]-
> We have: 
> 1. Notice that: $$\partial\sigma_{n}=\sum_{i=0}^{n}(-1)^i (\sigma_{n} \circ  F^n_{i})=\sum_{i=0}^{n}(-1)^i *\in S_{n-1}(*)$$Hence, $\partial[\sigma_{0}]=[\partial\sigma_{0}]=0$. 
> 2. Consider the following maps: $$H_{n}(\Delta _{n} / \partial  \Delta_{n},*)\xleftarrow{q_{*},\cong}H_{n}(\Delta_{n}, \partial\Delta_{n})\xrightarrow{\cong} \tilde{H}_{n-1}( \partial\Delta_{n})$$where the first isomorphism is from the fact that $(\Delta_{n}, \partial\Delta_{n})$ is a [[good pair]] and the second isomorphism from the reduced LES and the fact that $\Delta_{n}$ is contractible. 
>    
>    Now, consider $i_{n}:\Delta_{n}\to \Delta_{n}$. Then, we notice that $q_{*}[i_{n}]=[\sigma_{n}]$. Further, $\partial_{*}[i_{n}]=[\beta_{n-1}]$ where: $$\beta_{n-1}=\partial i_{n}=\sum_{i=0}^{n}(-1)^i F^n_{i}\in S_{n-1}(\partial \Delta_{n})$$Hence, it suffices to show that $[\beta_{n-1}]$ generates $\tilde{H}_{n-1}(\partial\Delta_{n})$. 
>    
>    We show this by induction over $n$.
> 	1. For $n=0$, $[\beta_{0}]$ obviously generates $\tilde{H}_{0}(\partial\Delta_{1})$. 
> 	2. For $n\geq 1$, consider a map $\phi:\partial\Delta^n\to\Delta^{n-1} / \partial \Delta^{n-1}$ which collapses all but zeroth face to a point. Then, for the induced map $\phi_{*}:\tilde{H}_{n-1}(\partial\Delta_{n})\to \tilde{H}_{n-1}(\Delta_{n-1} / \partial\Delta_{n-1})$ it holds that $\phi_{*}([\beta_{n-1}])=[\sigma_{n-1}]$ which is a generator by the induction hypothesis. 
>  1. Analogously, we have the following isomorphisms: $$H_{n}(\Delta _{n} / \partial  \Delta_{n},*;G)\xleftarrow{q_{*},\cong}H_{n}(\Delta_{n}, \partial\Delta_{n};G)\xrightarrow{\cong} \tilde{H}_{n-1}( \partial\Delta_{n};G)\to {H}_{n-1}(\Delta_{n-1} / \partial \Delta_{n-1}, *;G)$$and $G \to \tilde{H}_{0}(\partial\Delta_{0} ; G),g\mapsto [g\beta_{0}]$ is an isomorphism.

^e3fe27

---
> [!lemma] Proposition 6 (Change of Coefficients)
> Let $G_{1},G_{2},G_{3}$ be abelian groups and $\varphi:G_{1}\to G_{2}$ and $\psi:G_{2}\to G_{3}$ homomorphisms. 
> 1. for any $(X,A)$, there exists a [[Chain Complex|chain map]] $\varphi^c:S_{*}(X,A;G_{1})\to S_{*}(X,A;G_{2})$ s.t. for any $f:(X,A)\to(Y,B)$, $\varphi^c$ commutes with $f_{c}$. 
> 2. if $0\to G_{1}\to G_{2}\to G_{3}\to 0$ is a SES, then 
> 	1. we have that $$0 \to \mathcal{S}(X,A;G_{1})\to \mathcal{S}(X,A;G_{2})\to \mathcal{S}(X,A;G_{3})\to 0$$is a SES as well.
> 	2. there exists a LES: $$\dots\to H_{n}(X,A;G_{1})\to H_{n}(X,A;G_{2})\to H_{n}(X,A;G_{3})\to H_{n-1}(X,A;G_{1})\to \cdots $$

^ff019f

> [!proof]-
> We have that: 
> 1. It follows from:$$\varphi^c\left( \sum_{i}^{}g_{i}\sigma_{i} \right)=\sum_{i}\varphi(g_{i})\sigma_{i}$$Then, this obviously commutes with $f_{c}$. 
> 2. As $S_{*}(X,A)$ is a free abelian group, the statement follows from the right exactness of [[Tensor Product]]. (Proposition 3).
> 3. Follows from 2 and [[Exact Sequence|Theorem 3]].

^347ad0

- **Remark**: Most interesting examples of the SES of abelian groups are of the form: ^fb77d6
	1. $0\to \mathbb{Z} \xrightarrow{\times p} \mathbb{Z} \to \mathbb{Z} / p\mathbb{Z} \to 0$
	2. $0 \to \mathbb{Z} / p\mathbb{Z} \xrightarrow{\times p}  \mathbb{Z} / p^{2} \mathbb{Z} \to \mathbb{Z} / p\mathbb{Z} \to 0$

---
> [!lemma] Proposition 7 (Cross Product on Tensor Simplices)
> Let $X,Y$ be topological spaces. Then, the cross product induces a chain map: $$\times:\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y)\to \mathcal{S}_{*}(X\times Y)$$where $\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y)$ is the [[Chain Complex|tensor product of chain complexes]] $\mathcal{S}_{*}(X)$ and $\mathcal{S}_{*}(Y)$.

^1d79d3

> [!proof]-
> As the cross product is bilinear, it induces a bilinear map on: $$\times:S_{p}(X)\otimes S_{q}(Y)\to S_{p+q}(X\times Y)$$Now, to show that it is a chain map, for $a\in S_{p}(X)$ and $b\in S_{q}(Y)$, $$\times(\partial(a\otimes  b))=\times(\partial_{X} a\otimes  b+(-1)^{\left| a \right| }a\otimes  \partial_{Y}b)=\partial_{X}a\times b+(-1)^{p }a\times\partial_{Y}b=\partial(a\times b)$$

^92ad74

- **Corollary**: the cross product induces a map $H_{*}(\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y))\to H_{*}(X\times Y)$. Together with $h:H_{*}(X)\otimes H_{*}(Y)\to H_{*}(\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y))$ from [[Chain Complex|Tensor Product Chain Complex]] we have a map: $$\times:H_{p}(X)\otimes  H_{q}(Y)\to H_{p+q}(X\times Y)$$ ^7574ee
- **Remark**: Using the relative cross product, we also have $$\times:H_{p}(X,A)\otimes H_{q}(Y,B)\to H_{p+q}(X\times Y, X\times B \cup A\times Y)$$ ^33d779

---
> [!lemma] Theorem 8 (Eilenberg-Zilberg)
> Consider the following. 
> 1. there exist a chain map $\Theta:\mathcal{S}_{*}(X\times Y)\to \mathcal{S}_{*}(X)\otimes  \mathcal{S}_{*}(Y)$ for any topological spaces $X,Y$ s.t.
> 	1. $\Theta:S_{0}(X\times Y)\to S_{0}(X)\otimes S_{0}(Y), (x,y)\mapsto x\otimes y$.
> 	2. $\Theta$ is natural w.r.t. continuous maps between spaces, i.e. for all $f:X\to X'$ and $g:Y\to Y'$, the following diagram commutes: $$\begin{CD}\mathcal{S}_{*}(X\times Y)@>\Theta>>\mathcal{S}_{*}(X)\otimes  \mathcal{S}_{*}(Y)\\@V(f\times g)_{c}VV @VVf_{c}\otimes  g_{c}V\\ \mathcal{S}_{*}(X'\times Y') @>>\Theta>\mathcal{S}_{*}(X')\otimes  \mathcal{S}_{*}(Y')\end{CD}$$
> 2. $\Theta$ is a [[Chain Homotopy|chain homotopy equivalence]].
> 3. $H_{*}(\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y))\cong H_{*}(X\times Y)$.

^254457

> [!proof]+
> We have that:
> 1. Recall that from the proof of Theorem 2, for any contractible space $X$ and $x_{0}\in X$, there exists a chain map: $\varepsilon_{x_{0}}:\mathcal{S}_{*}(X)\to \mathcal{S}_{*}(X)$ with $\varepsilon_{x_{0}}\equiv 0$ in degree $i>0$ and:$$\varepsilon_{x_{0}}:\mathcal{S}_{0}(X)\to \mathcal{S}_{0}(X),\quad \sum_{x\in X}n_{x}x\mapsto \left( \sum_{x\in X}^{}n_{x} \right)x_{0}$$    and a chain homotopy $D:=D_{X,x_{0}}:\mathcal{S}_{*}(X)\to \mathcal{S}_{*}(X)[1]$ s.t. $D\partial+\partial D=\text{id}-\varepsilon_{x_{0}}$.
>    
>    Now, we first show the following lemma: 
> 	1. **Lemma 1**: For contractible $X,Y$ and $x_{0}\in X$, $y_{0}\in Y$, there exists a chain homotopy $$E:\mathcal{S}_{*}(X)\otimes  \mathcal{S}_{*}(Y)\to (\mathcal{S}_{*}(X)\otimes  \mathcal{S}_{*}(Y))[1]$$between $\varepsilon_{x_{0}}\otimes \varepsilon_{y_{0}}$ and $\text{id}\otimes \text{id}=\text{id}_{\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y)}$.
> 	   
> 	   Let $D_{X}:=D_{X,x_{0}}$ and $D_{Y}:= D_{Y,y_{0}}$ from above. Then, for $E:=D_{X}\otimes \text{id}+\varepsilon_{x_{0}}\otimes D_{Y}$ we have that: $$\begin{aligned}E \circ  \partial+\partial \circ  E&=(D_{X}\otimes  \text{id}+\varepsilon_{x_{0}}\otimes  D_{Y})\circ  (\partial \otimes  \text{id}+\text{id}\otimes  \partial)\\&\quad\quad\quad\quad+ (\partial \otimes  \text{id}+\text{id}\otimes  \partial) \circ (D_{X}\otimes  \text{id}+\varepsilon_{x_{0}}\otimes  D_{Y})\\&= (D_{X}\circ  \partial)\otimes  \text{id}+D_{X}\otimes \partial-(\varepsilon_{x_{0}}\circ  \partial)\otimes  D_{Y}+ \varepsilon_{x_{0}}\otimes  (D_{Y}\circ  \partial)\\&\quad\quad\quad\quad+(\partial \circ  D_{X})\otimes  \text{id}+(\partial \circ  \varepsilon_{x_{0}})\otimes  D_{Y}-D_{X}\otimes \partial+\varepsilon_{x_{0}}\otimes(\partial \circ  D_{Y})\\&=\text{id}\otimes  \text{id}-\varepsilon_{x_{0}}\otimes  \text{id}+\underbrace{ (\partial \circ  \varepsilon_{x_{0}}-\varepsilon_{x_{0}}\circ  \partial) }_{ =0 }\otimes  D_{Y}+ \varepsilon_{x_{0}}\otimes  \text{id}-\varepsilon_{x_{0}}\otimes  \varepsilon_{y_{0}}\\&=\text{id}\otimes \text{id}-\varepsilon_{x_{0}}\otimes  \varepsilon_{y_{0}}\end{aligned}$$
> 	2. **Lemma 2**: For contractible $X,Y$ and $x_{0}\in X$, $y_{0}\in Y$, $$H_{n}(\mathcal{S}_{*}(X)\otimes  \mathcal{S}_{*}(Y))=0,\quad \forall n\geq 1$$
> 		   From Lemma 1, $(\varepsilon_{x_{0}}\otimes \varepsilon_{y_{0}})_{*}=\text{id}_{H_{n}(\mathcal{S}_{*}(X)\otimes  \mathcal{S}_{*}(Y))}$. However, as $(\varepsilon_{x_{0}}\otimes \varepsilon_{y_{0}})_{*}=0$ for $n\geq 1$, we have the statement.
> 	
>    We then prove the theorem with induction. 
>    
>    First, if $n=0$, we define $\Theta(x,y)=x\otimes y$. For $n\geq 1$, assume $\Theta$ has been defined for all $0\leq k< n$ and $X,Y$. Consider the diagonal map $d_{n}:\Delta^n \to \Delta^n\times\Delta^n,x\mapsto (x,x)$. Then, $d_{n}\in S_{n}(\Delta^n \times\Delta^n)$. Therefore, by induction $\Theta$ is already defined on $\partial d_{n}\in S_{n-1}(\Delta^n\times\Delta^n)$.
>    
>    We now claim that there exists $a_{n}\in (\mathcal{S}_{*}(\Delta^n)\otimes \mathcal{S}_{*}(\Delta^n))_{n}$ s.t. $\partial a_{n}=\Theta(\partial d_{n})$. Indeed, $$\partial\Theta(\partial d_{n})=\Theta \partial^{2}d_{n}=0$$as $\Theta$ is a chain map up to degree $n-1$. Hence, $\Theta(\partial d_{n})$ is a cycle of deg $n-1$. 
>    
>    If $n\geq 2$, then $n-1\geq 1$ and since $\Delta^n$ is contractible, by Lemma 2, $H_{n-1}(\mathcal{S}_{*}(\Delta^n)\otimes \mathcal{S}_{*}(\Delta^n))=0$. Therefore, there exists $a_{n}\in (\mathcal{S}_{*}(\Delta^n)\otimes \mathcal{S}_{*}(\Delta^n))_{n}$ with $\partial a_{n}=\Theta(\partial d_{n})$.
>    
>    If $n=1$, then $\Theta (\partial d_{1})=\Theta((1,1)-(0,0))=1\otimes 1-0 \otimes 0$. Therefore, by Lemma 1, $$[\Theta(\partial d_{1})]=[1\otimes  1-0\otimes  0]$$