#Definition #Algebra

> [!Definition]
> For a [[group]] $G$ and $N \leq G$, if for all $x\in G$, $$xNx^{-1}=N$$
> i.e. $xN=Nx$, then $N$ is a ***normal divisor/subgroup*** of $G$, denoted by $N \unlhd G$. If $N<G$, then $N$ is a ***proper normal divisor***, denoted by $N \lhd G$.
- **Remark**: A normal subgroup always conjugates to itself.
- **Remark**: Any [[subgroup]] of an [[Abelian Group|abelian group]] is normal.
- **Remark**: If $H\leq G$ and $[G:H]=2$, then $H\unlhd G$. ([[Coset|Lemma 3]])
- **Remark**: If $H\unlhd K\unlhd G$, then $H$ is not necessarily a normal divisor of $G$. **Example**: Let $G=D_{4}$ ([[Dihedral Group]]). Let $H=\{ e,\sigma_{1} \}\cong C_{2}$   and $K=\{ e,\sigma_{1},\sigma_{2},\sigma_{1}\circ\sigma_{2} \}\cong C_{2}\times C_{2}$. Then, we have $H\unlhd K$ as $K$ is abelian and $K\unlhd G$ (as $[G:K]=2$). But $\rho \sigma_{1}\rho^{-1}=\sigma_{2}\notin H$. Therefore, $H$ is not a normal divisor of $G$.

---
##### Properties

> [!lemma] Proposition 1
> For $N \leq G$, it holds that 
> $$N \unlhd G\quad \Longleftrightarrow \quad \forall x\in G:\forall n\in N:(xn x^{-1}\in N)$$

> [!proof]-
> We know that => direction is from the definition. For the other direction, from the assumption it follows that $xNx^{-1}\subseteq N$. If we replace $x$ with $x^{-1}$, then:
> $$N=x(x^{-1}Nx)x^{-1}\subseteq xNx^{-1}$$
> Therefore, $N=xNx^{-1}$ and $N\unlhd G$.
---
> [!lemma] Fact 2
> If $N,K\unlhd G$, then $(N\cap K)\unlhd G$.

> [!proof]-
> With [[Subgroup|Proposition 2]] $(K\cap N)\leq G$. Therefore, from Proposition 1, for all $x\in G$ and $h\in K\cap N$:
> $$xhx^{-1}\in K\land xhx^{-1}\in N$$ 
> and therefore, $xhx^{-1}\in K\cap N$, which implies $(K\cap N)\unlhd G$ using the same proposition again.

---
> [!lemma] Fact 3
> If $N\unlhd G$, then for all $x,y\in G$: $$(xN)(yN)=(xy)N$$
> So, we can define a binary operation on $G / N$.

> [!proof]-
> As $N \unlhd G$, it holds that:
> $$(xN)(yN)=(x(yNy^{-1}))(yN)=xyNN =(xy)N$$
---
> [!lemma] Proposition 4
> Let $H,K\unlhd G$ and $\left| H\cap K \right|=1$. Then, for all $h\in H, k\in K$: $$hk=kh$$

> [!proof]-
> Consider $hkh^{-1}k^{-1}$. We have that: 
> 1. $h\underbrace{ kh^{-1}k^{-1}}_{ \in H }\in H$ and
> 2. $\underbrace{ hkh^{-1} }_{ \in K }k^{-1}\in K$
> 
> Therefore, $hkh^{-1}k^{-1}\in H\cap K$, i.e. $hkh^{-1}k^{-1}=e$. This proves the statement.
---
> [!lemma] Proposition 5
> Let $p$ be the smallest prime dividing $\left| G \right|$. If $H\leq G$ s.t. $[G : H]=p$, then $H \unlhd G$. 

> [!proof]-
> We define a group action $G \curvearrowright G/H$: $x\circ gH=xgH$. This induces a homomorphism: $$\begin{array}{cccc} {\varphi:}&{G}&\to&{S_{p}}\\&{x} &\mapsto & {\varphi(x)} \end{array}{}$$where $\varphi(x)(gH)=xgH$. Then, $\text{ker}\varphi=\{ x\in G: xgH=gH\quad  \forall g \}$. If $x\in \text{ker} \varphi$, then $xH=H$ and therefore, $x\in H$. This shows that $\text{ker}\varphi\leq H$.
> 
> Then, using the [[Group Homomorphism|first isomorphism theorem]], $G / \text{ker}(\varphi)=\text{Im}(\varphi)\leq S_{p}$. Therefore, $$[G: \text{ker}\varphi] | \left| S_{p} \right| =p!$$
> 
> It follows that:
> 1. $p=[G:H]|[G:\text{ker}\varphi]$
> 2. $[G:\text{ker}\varphi]|p!$
>    
> From these facts, we can conclude that $[G:\text{ker}\varphi]=p$.  Then, $$p=\frac{\left| G \right| }{|\text{ker}\varphi|}=\frac{\left| G \right| }{|H|} \frac{|H|}{|\text{ker}\varphi|}$$Therefore, $[H:\text{ker}\varphi]=1$, i.e. $H=\text{ker}\varphi$. As the kernel is normal, we have that $H\unlhd G$.
---
##### Examples
1. $\mathbb{U}\unlhd \mathbb{C}^{*}$: for $z\in \mathbb{C}^{*}$ and $u\in \mathbb{U}$, $\left| zuz^{-1} \right|=\left| zz^{-1}u \right|=1$. We have: $\mathbb{C}^{*} / \mathbb{U}=\mathbb{R}^{*}$
---
