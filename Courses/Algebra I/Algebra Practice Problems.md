#Algebra-I 

> [!Q] Q1
> Prove or disprove: 
> 1. If $N_{1}\unlhd G_{1},N_{2}\unlhd G_{2}$ with $N_{1}\cong N_{2}$ and $G_{1} / N_{1}\cong G_{2} / N_{2}$ then, $G_{1}\cong G_{2}$.
> 2. If $N_{1}\unlhd G_{1},N_{2}\unlhd G_{2}$ with $G_{1}\cong G_{2}$ and $N_{1}\cong N_{2}$, then $G_{1} / N_{1}\cong G_{2} / N_{2}$.
> 3. If $N_{1}\unlhd G_{1},N_{2}\unlhd G_{2}$ with $G_{1}\cong G_{2}$ and $G_{1} / N_{1}\cong G_{2} / N_{2}$, then $N_{1}\cong N_{2}$.

> [!a]- A1
> We have: 
> 1. False: $C_{12}$ and $D_{6}$ both have a normal subgroup isomorphic to $C_{6}$. 
> 2. False: $D_{6}$ has two normal subgroups $\braket{ \sigma  }$ and $\braket{ \rho^3  }$ isomorphic to $C_{2}$. However, the quotient group are $C_{6}$ and $D_{3}$ respectively.
> 3. False: $D_{6}$ and consider the subgroups $C_{6}$ and $D_{3}$. Then, the quotient is the same but the subgroups are not isomorphic.
---
> [!Q] Q2
> Let $G$ be a group and let $N\unlhd G$ of index $n$. Show that $g^n\in N$ for all $g\in G$.

> [!a]- A2
> For every $g\in G$, $(gH)^n=g^nH=H$. Therefore, $g^n\in H$.
---
> [!Q] Q3
> Let $G$ be a finite group of odd order. Show that every element of $G$ has a unique square root; that is, for every $g\in G$, there exists a unique $a\in G$ such that $a^{2}=g$.

> [!a]- A3
> For $g\in G$, $\text{ord}(g)$ is odd as well. Therefore, there exists $k\geq0$ s.t. $g^{2k+1}=e$ and $g=(g^{2k})^{-1}$. Let $a=(g^k)^{-1}$. Then, $$a\cdot a=(g^k)^{-1}(g^k)^{-1}=(g^{2k})^{-1}=g$$For uniqueness, if $\left| G \right|=2p-1$, $$a=a^{2p}=b^{2p}=b$$
---
> [!Q] Q4
> Let $G$ be a group. A subgroup $H\leq G$ is called a characteristic subgroup of $G$ if $\varphi(H)=H$ for every $\varphi\in \text{Aut}(G)$. Show that if $H$ is a characteristic subgroup of $N$ and $N\unlhd G$, then $H\unlhd G$.

> [!a]- A4
> For all $g\in G$,  $\varphi(x)=gxg^{-1}$ is an automorphism. Therefore, $gHg^{-1}=H$. 
---
> [!Q] Q5
> Show that if $H$ is a characteristic subgroup of $N$ and $N$ is a characteristic subgroup of $G$, then $H$ is a characteristic subgroup of $G$.

> [!a]- A5
> For any $\varphi\in \text{Aut}(G)$, as $\varphi[N]=N$, we can restrict $\varphi|_{N}\in \text{Aut}(N)$. Therefore, $\varphi|_{N}(H)=H$ and $\varphi(H)=H$.
---
> [!Q] Q6
> Let $G$ be a finite group, $H\leq G$ and $N\unlhd G$. Show that if $\gcd(\left| H \right|,[G:N])=1$, $H\subseteq N$.

> [!a]- A6
> We have that $HN\leq G$. Therefore, $$\frac{\left| K \right|}{\left| K\cap N \right| }\mid [G:N]$$and $\left| K \cap N\right|=\left| K \right|$. This shows that $K\subseteq N$.
---
> [!Q] Q7
> Let $G$ be a group. Show that if $G / Z(G)$ is cyclic, then $G$ is abelian.

> [!proof]-
> We have that $G / Z(G)=\braket{ aZ(G) }$. For every $g\in G$, $gZ(G)=a^k Z(G)$. Then, $$ab=$$
---
> [!Q] Q8
> Prove or disprove: Let $G$ be a group. If $G / Z(G)$ is abelian, then $G$ is abelian.

> [!a]- A8
> Counterexample: $D_{4}$ has $\{ e,\rho^{2} \}$ as center.
---
> [!Q] Q9
> Show that if $G$ is a nonabelian finite group, then $\left| Z(G) \right|\leq \frac{1}{ 4}\left| G \right|$

> [!a]- A9
> We know that $[G:Z(G)]$ is then non-cyclic by Q8. Therefore, $$[G:Z(G)]\geq 4$$.
---
> [!Q] Q10
> Let $H\leq G$. Show that the following are equivalent: 
> 1. $x ^{-1}y^{-1}xy\in H$ for all $x,y\in G$ 
> 2. $H\unlhd G$ and $G / H$ is abelian

> [!a]- A10
> If $x ^{-1}y^{-1}xy\in H$ for all $x,y\in G$, then for $g\in G$ and $h\in H$: $$ghg^{-1}=h\underbrace{ h^{-1}ghg^{-1} }_{ \in H }\in H$$Hence, $H\unlhd G$. Further, for $xH,yH\in G / H$, $x ^{-1}y^{-1}xyH=H$ and $xyH=yxH$. On the other hand, we have for all $x,y\in G$ $$H=(xH)(x ^{-1}H)(yH)(y^{-1}H)=x ^{-1}y^{-1}xyH$$as $G / H$ is abelian. 
---
> [!Q] Q11
> Let $G$ be a group, $H\leq G$ of finite index $n$. Define $$\begin{array}{cccc} {f:}&{G}&\to&{S(G / H)}\\&{g} &\mapsto & {xH\mapsto(gx)H} \end{array}{}$$
> 1. Show that $f$ is a group homomorphism. 
> 2. Show that if $H\unlhd G$, then $H=\text{ker }f$.

> [!a]- A11
> We have: 
> 1. $$f(g_{1}g_{2})(xH)=g_{1}g_{2}xH=f(g_{1})(g_{2}xH)=f(g_{1})(f(g_{2})(xH))=(f(g_{1})\circ f(g_{2}))(xH)$$
> 2. We have: $$\text{ker }f:=\{ g\in G: gxH=xH\quad\forall x\in G \}=\{ g\in G:gxx^{-1}=g\in H \}=H$$
---
> [!Q] Q12
> Let $G$ be an abelian group. Let $K=\{ a\in G:a^{2}=e \}$ and let $H=\{ x^{2}: x\in G \}$. Show that $G / K\cong H$. 

> [!a]- A12
> We define the homomorphism: $$\begin{array}{cccc} {\varphi:}&{G}&\to&{H}\\&{x} &\mapsto & {x^{2}} \end{array}{}$$Then, $$\varphi(xy)=xyxy=x^{2}y^{2}=\varphi(x)\varphi(y)$$
> with $\text{ker }\varphi=K$. Therefore, $G / K\cong H$.
---
##### Cyclic Groups
