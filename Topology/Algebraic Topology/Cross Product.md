#Definition #AlgebraicTopology 

> [!definition]
> Let $X,Y$ be [[topological space|topological spaces]] and $R$ a [[ring]].
> 1. ***Homological cross product*** is a chain map: $$\times:\mathcal{S}_{*}(X)\otimes  \mathcal{S}_{*}(Y)\to \mathcal{S}_{*}(X\times Y)$$that is:
> 	1. natural under maps $X\to X'$ and $Y\to Y'$
> 	2. satisfies the Leibniz formula: $\partial(a\times b)=\partial a \times b+(-1)^p a\times \partial b$ for all $a\in S_{p}(X)$ and $b\in S_{q}(X)$.
> 2. ***Relative Homological cross product*** is a chain map: $$\times:\mathcal{S}_{*}(X,A)\otimes  \mathcal{S}_{*}(Y,B)\to \mathcal{S}_{*}(X\times Y,(X\times B)\cup (A\times Y))$$that is:
> 	1. natural under maps $X\to X'$ and $Y\to Y'$
> 	2. satisfies the Leibniz formula: $\partial(a\times b)=\partial a \times b+(-1)^p a\times \partial b$ for all $a\in S_{p}(X)$ and $b\in S_{q}(X)$.
> 3. ***Cohomological cross product*** is a cochain map:$$\times:\mathcal{S}^{*}(X;R)\otimes_{\mathbb{Z}}  \mathcal{S}^{*}(Y;R)\to \mathcal{S}^{*}(X\times Y;R),\quad \varphi \otimes  \psi\mapsto (\varphi \otimes  \psi)\circ  \Theta$$that is natural under maps $X\to X'$ and $Y\to Y'$ where $\Theta:\mathcal{S}_{*}(X\times Y)\to \mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y)$ is given by [[Singular Homology|Eilenberg-Zilberg]].

^9c0a44

- **Remark**: The cross products induce a map in co-/homology:
	1. $\times:H_{p}(X)\otimes H_{q}(Y)\to H_{p+q}(X\times Y),[a]\otimes[b]\mapsto[a\times b]$.
	2. $\times:H^p(X;R)\otimes_{R}H^q(Y;R)\to H^{p+q}(X\times Y;R)$

---
##### Properties
![[Singular Homology#^817af7]]
![[Singular Homology#^70ff12|p]]

---
![[Singular Cohomology#^e93291]]
![[Singular Cohomology#^bffd5e|p]]

---

![[Relative Homology#^14638d]]
![[Relative Homology#^8840d9|p]]
![[Relative Homology#^85bd50]]

---
> [!lemma] Proposition 1 (Associativity of Homological Cross Product)
> Let $X,Y,Z$ be topological spaces. For $a\in H_{*}(X),b\in H_{*}(Y),c\in H_{*}(Z)$, $$(a\times b)\times c=a\times(b\times c)\in H_{*}(X\times Y\times Z)$$

^a0f0a6

> [!proof]-
> We claim that two chain maps $\phi,\psi:\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y)\otimes \mathcal{S}_{*}(Z)\to \mathcal{S}_{*}(X\times Y\times Z)$ s.t.
> 1. in degree 0, $\phi(x\otimes y\otimes z)=\psi(x\otimes y\otimes z)=(x,y,z)$ for all $x\in X,y\in Y,z\in Z$.
> 2. both are natural w.r.t. $X\to X',Y\to Y',Z\to Z'$.
> 
> Then, $\phi \sim \psi$. We proceed by induction over $n$ to construct a chain homotopy $D$. 
> 
>  - If $n=0$, as $\phi=\psi$ we can set $D=0$.
>  - If $n\geq 1$, assume that we have $D$ for all $0\leq k< n$ for all spaces $X,Y,Z$ that is natural w.r.t. $X\to X',Y\to Y', Z\to Z'$ and $\partial_{X\times Y\times Z} D+D\partial_{\otimes}=\phi-\psi$.
>    
>    Let $I_{i}:\Delta^i\to \Delta^i\in S_{i}(\Delta^i)$ given by $x\mapsto x$. Then, we claim that for any $i+j+k=n$: $$(\phi-\psi-D\partial_{\otimes })(I_{i}\otimes  I_{j}\otimes  I_{k})\in S_{n}(\Delta^i\times \Delta^j\times \Delta^k)$$is a cycle. Indeed, $$\begin{aligned}\partial_{X\times Y\times Z}(\phi-\psi-D\partial_{\otimes })(I_{i}\otimes  I_{j}\otimes  I_{k})&=(\phi \partial_{\otimes }-\psi\partial_{\otimes }+D\partial_{\otimes }^{2}+\psi \partial_{\otimes }-\phi \partial_{\otimes })(I_{i}\otimes  I_{j}\otimes  I_{k})=0\end{aligned}$$As $\Delta^i\times\Delta^j\times\Delta^k$ is contractible, $H_{n}(\Delta^i\times\Delta^j\times\Delta^k)=0$ and there is $a\in S_{n+1}(\Delta^i\times\Delta^j\times\Delta^k)$ s.t. $\partial a=(\phi-\psi-D\partial_{\otimes})(I_{i}\otimes I_{j}\otimes I_{k})$. Let $D(I_{i}\otimes I_{j}\otimes I_{k}):= a$. Then, it holds that:$$\partial D(I_{i}\otimes  I_{j}\otimes  I_{k})=\partial a=(\phi-\psi-D\partial_{\otimes })(I_{i}\otimes  I_{j}\otimes  I_{k})$$Now, we set for $\sigma_{X}\in S_{i}(X)$, $\sigma_{Y}\in S_{j}(Y)$ and $\sigma_{Z}\in S_{k}(Z)$ we define: $$D(\sigma_{X}\otimes \sigma_{Y}\otimes  \sigma_{Z}):= (\sigma_{X}\times\sigma_{Y}\times\sigma_{Z})_{c}D(I_{i}\otimes  I_{j}\otimes  I_{k})$$
> 	 1. **$D$ is well-defined** as $I_{i}\times I_{j}\times I_{k}$ is the identity.
> 	 2. **$D$ is natural w.r.t. maps**:
> 	    For $f:X\to X',g:Y\to Y', h:Z\to Z'$, we have that: $$\begin{aligned}D((f_{c}\otimes  g_{c}\otimes  h_{c})(\sigma_{X}\otimes  \sigma_{Y}\otimes  \sigma_{Z}))&=D((f\circ  \sigma_{X})\otimes  (g \circ  \sigma_{Y} )\otimes   (h\circ  \sigma_{Z}))\\&=((f\circ  \sigma_{X})\times  (g \circ  \sigma_{Y} )\times   (h\circ  \sigma_{Z}))_{c}D(I_{i}\otimes  I_{j}\otimes  I_{k})\\&=(f\times g\times h)_{c}(\sigma_{X}\times\sigma_{Y}\times\sigma_{Z})_{c}D(I_{i}\otimes  I_{j}\otimes  I_{k})\\&=(f\times g\times h)_{c}D(\sigma_{X}\otimes  \sigma_{Y}\otimes  \sigma_{Z})\end{aligned}$$
> 	 3. $\partial D+D\partial=\phi-\psi$.
> 	    I have that: $$\begin{aligned}\partial D(\sigma_{X}\otimes  \sigma_{Y}\otimes  \sigma_{Z})&=\partial (\sigma_{X}\times\sigma_{Y}\times\sigma_{Z})_{c}D(I_{i}\otimes  I_{j}\otimes  I_{k})\\&= (\sigma_{X}\times\sigma_{Y}\times\sigma_{Z})_{c}\partial D(I_{i}\otimes  I_{j}\otimes  I_{k})\\&= (\sigma_{X}\times\sigma_{Y}\times\sigma_{Z})_{c}(\phi-\psi-D\partial_{\otimes })(I_{i}\otimes  I_{j}\otimes  I_{k})\\&=(\phi-\psi-D\partial_{\otimes }) ((\sigma_{X})_{c}\otimes (\sigma_{Y})_{c}\times(\sigma_{Z})_{c})(I_{i}\otimes  I_{j}\otimes  I_{k})\\&=(\phi-\psi-D\partial_{\otimes }) (\sigma_{X}\otimes  \sigma_{Y}\otimes  \sigma_{Z})\end{aligned}$$ 
> 	 
> 	This proves the induction.
> 
> Now, consider the two compositions given by: 
> 1. $\phi:\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y)\otimes \mathcal{S}_{*}(Z)\xrightarrow{\times \otimes \text{id}}\mathcal{S}_{*}(X\times Y)\otimes \mathcal{S}_{*}(Z)\xrightarrow{\times}\mathcal{S}_{*}(X\times Y\times Z)$ and
> 2. $\psi:\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y)\otimes \mathcal{S}_{*}(Z)\xrightarrow{\text{id}\otimes  \times}\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y\times Z)\xrightarrow{\times}\mathcal{S}_{*}(X\times Y\times Z)$.
> 
> Clearly, both are chain maps that satisfy the above two conditions. Hence, they are chain homotopic. Further, in homology, we get that: $$\phi_{*}([\sigma_{X}]\otimes [\sigma_{Y}]\otimes  [\sigma_{Z}])=\phi_{*}([\sigma_{X}\otimes  \sigma_{Y}\otimes  \sigma_{Z}])=[(\sigma_{X}\times\sigma_{Y})\otimes  \sigma_{Z}]=[(\sigma_{X}\times\sigma_{Y})\times\sigma_{Z}]$$Similarly, $$\psi_{*}([\sigma_{X}]\otimes [\sigma_{Y}]\otimes  [\sigma_{Z}])=[\sigma_{X}\times(\sigma_{Y}\times\sigma_{Z})]$$This proves the claim.
>    

^a98ef9

---
> [!lemma] Proposition 2 (Commutativity and Associativity of Cohomological Cross Product)
> Let $X,Y,Z$ be topological spaces. For $\alpha\in H^p(X;R),\beta\in H^q(Y;R),\gamma\in H^r(Z;R)$
> 1. **(Graded commutativity)**: for $T:X\times Y\to Y\times X,(x,y)\mapsto(y,x)$, it holds that: $$\alpha \times\beta=(-1)^{pq}T^{*}(\beta \times\alpha)$$ 
> 2. **Associativity**: it holds that in $H^{p+q+r}(X\times Y\times Z)$ $$(\alpha \times\beta)\times\gamma=\alpha \times(\beta \times\gamma)$$

^6340c5

> [!proof]-
> Fix $\Theta$ from [[Singular Homology|EZ Theorem]]. We have that:
> 1. Consider the following map: $$\tau:\mathcal{S}_{*}(Y)\otimes  \mathcal{S}_{*}(X)\to \mathcal{S}_{*}(X)\otimes  \mathcal{S}_{*}(Y),\quad b\otimes  a\mapsto (-1)^{|a\mid b|}a\otimes  b$$
> 	1. **$\tau$ is a chain map**:
> 	   For $a\in S_{p}(X)$ and $b\in S_{q}(Y)$, we have: $$\begin{aligned}\tau(\partial (b\otimes  a))&=\tau(\partial b\otimes  a+(-1)^qb\otimes  \partial a)=(-1)^{q+(p-1)q}\partial a \otimes  b+(-1)^{p(q-1)}a\otimes  \partial b\\&=(-1)^{pq}(\partial a \otimes  b+(-1)^{p}a\otimes  \partial b)\\&=(-1)^{pq}\partial(a\otimes  b)\\&=\partial \tau(b\otimes  a)\end{aligned}$$
> 	
> 	Consider now the composition $J:=\tau \circ \Theta_{Y,X}\circ T_{c}:\mathcal{S}_{*}(X\times Y)\to \mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y)$ which is a chain map. This is natural w.r.t. $X\to X'$ and $Y\to Y'$. Further, at deg 0, we have: $$J(x,y)=\tau \circ \Theta_{Y,X}(y,x)=\tau(y\otimes  x)= x \otimes  y$$Therefore, by Eilenberg-Zilberg, $J\sim \Theta_{X,Y}$, i.e. there exists $$D:\mathcal{S}_{*}(X\times Y)\to (\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y))[1]$$s.t. $\partial_{\otimes} D+D\partial_{X\times Y}=J-\Theta_{X,Y}$. For $f\in S^p(X;R)$ and $g\in S^q(Y;R)$ cocyles, $$\begin{aligned}T^{*}([g]  \times [f])&=T^{*}([g\times f])=T^{*}([(g\otimes  f)\circ  \Theta_{Y,X}])=[(g\otimes  f)\circ \Theta_{Y,X}\circ  T_{c}]\\&=(-1)^{pq}[(f\otimes  g)\circ  \tau\circ \Theta_{Y,X}\circ  T_{c}]\end{aligned}$$as $(-1)^{pq}(f\otimes g)\tau(b\otimes a)=(f\otimes g)(a\otimes b)=(-1)^{pq}f(a) g(b)=(g\otimes f)(b\otimes a)$. Therefore, $$\begin{aligned}T^{*}([g]  \times [f])&=(-1)^{pq}[(f\otimes  g)\circ  J]\\&=(-1)^{pq}[(f\otimes  g)\circ \Theta_{X,Y}+(f\otimes  g)\circ  \partial_{\otimes }D+(f\otimes  g)\circ  D\partial_{X\times Y}]\\&=(-1)^{pq}[(f\otimes  g)\circ \Theta_{X,Y}+\underbrace{ (f\otimes  g)\circ  \partial_{\otimes } }_{ =0 }D\pm \delta_{X\times Y}((f\otimes  g)\circ  D)]\\&=(-1)^{pq}[(f\otimes  g)\circ \Theta_{X,Y}]\\&=(-1)^{pq}[f\times g]\\&=(-1)^{pq}[f]\times[g]\end{aligned}$$
> 2. Consider the following two chain maps:
> 	1. $\phi:\mathcal{S}_{*}(X\times Y\times Z)\xrightarrow{\Theta_{X\times Y,Z}}\mathcal{S}_{*}(X\times Y)\otimes \mathcal{S}_{*}(Z)\xrightarrow{\Theta_{X,Y}\otimes \text{id}}\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y)\otimes \mathcal{S}_{*}(Z)$ and
> 	2. $\psi:\mathcal{S}_{*}(X\times Y\times Z)\xrightarrow{\Theta_{X,Y\times Z}}\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y\times Z)\xrightarrow{\text{id}\otimes \Theta_{Y,Z}}\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y)\otimes \mathcal{S}_{*}(Z)$.
>  
> 	 Let $f,g,h$ be cocycles representing $\alpha,\beta,\gamma$ respectively. Then, $$\begin{aligned}(f\times g)\times h&=((f\times g)\otimes  h)\circ  \Theta_{X\times Y,Z}\\&=(((f\otimes  g)\circ  \Theta_{X,Y})\otimes  h)\circ  \Theta_{X\times Y,Z}\\&=((f\otimes  g)\otimes  h)\circ  (\Theta_{X,Y}\otimes  \text{id})\circ  \Theta_{X\times Y,Z}\\&=\phi ^{*}(f\otimes  g\otimes  h)\end{aligned}$$Similarly, $\psi ^{*}(f\otimes g\otimes h)=f\times(g\times h)$. Hence, it suffices to show that $\phi \sim \psi$ which can be shown analogously to [[Singular Homology|Theorem 9]].

^52f367

- **Remark**: The graded commutativity holds on the cohomology level but may not on the cochain level. ^bbc4db

---
