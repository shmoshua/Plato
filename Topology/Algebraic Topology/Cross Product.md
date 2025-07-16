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
> [!lemma] Proposition 1 (Commutativity and Associativity of Cohomological Cross Product)
> Let $X,Y$ be topological spaces. For $\alpha\in H^p(X;R),\beta\in H^q(Y;R)$ cocycles, 
> 1. **(Graded commutativity)**: for $T:X\times Y\to Y\times X,(x,y)\mapsto(y,x)$, it holds that: $$\alpha \times\beta=(-1)^{pq}T^{*}(\beta \times\alpha)$$ 

> [!proof]+
> We have that:
> 1. Fix $\Theta$ from [[Singular Homology|EZ Theorem]]. Consider the following map: $$\tau:\mathcal{S}_{*}(Y)\otimes  \mathcal{S}_{*}(X)\to \mathcal{S}_{*}(X)\otimes  \mathcal{S}_{*}(Y),\quad b\otimes  a\mapsto (-1)^{|a\mid b|}a\otimes  b$$
> 	1. **$\tau$ is a chain map**:
> 	   For $a\in S_{p}(X)$ and $b\in S_{q}(Y)$, we have: $$\begin{aligned}\tau(\partial (b\otimes  a))&=\tau(\partial b\otimes  a+(-1)^qb\otimes  \partial a)=(-1)^{q+(p-1)q}\partial a \otimes  b+(-1)^{p(q-1)}a\otimes  \partial b\\&=(-1)^{pq}(\partial a \otimes  b+(-1)^{p}a\otimes  \partial b)\\&=(-1)^{pq}\partial(a\otimes  b)\\&=\partial \tau(b\otimes  a)\end{aligned}$$
> 	
> 	Consider now the composition $J:=\tau \circ \Theta_{Y,X}\circ T_{c}:\mathcal{S}_{*}(X\times Y)\to \mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y)$ which is a chain map. This is natural w.r.t. $X\to X'$ and $Y\to Y'$. Further, at deg 0, we have: $$J(x,y)=\tau \circ \Theta_{Y,X}(y,x)=\tau(y\otimes  x)= x \otimes  y$$Therefore, by Eilenberg-Zilberg, $J\sim \Theta_{X,Y}$, i.e. there exists $$D:\mathcal{S}_{*}(X\times Y)\to (\mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(Y))[1]$$s.t. $\partial_{\otimes} D+D\partial_{X\times Y}=J-\Theta_{X,Y}$. Passing to cohomologies, 

- **Remark**: The graded commutativity holds on the cohomology level but may not on the cochain level.