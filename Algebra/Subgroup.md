#Definition #Algebra

> [!Definition]
> For a group $G$, a non-empty subset $H \subseteq G$ is a ***subgroup*** of $G$ if for all $x,y\in H$, $$x y^{-1}\in H$$denoted as $H \leq G$. If $H\neq G$, we call $H$ a ***proper subgroup*** of $G$, denoted as $H < G$. $\{  e \}$ and $G$ are called ***trivial subgroups*** of $G$. 
- **Related definition**: For a group $G$ and a set $X \subseteq G$, the ***subgroup generated by $X$*** is denoted as: $\braket{ X  }:=\bigcap_{H\leq G,X\subseteq H}^{} H$. If $X=\{ x \}$, then we just write $\braket{ x  }$.
---
##### Propositions

> [!lemma] Proposition 1
> If $H \leq G$, then $H$ is a group.

> [!Proof]-
> We will show the group axioms:
> 1. If $x\in H$, then $x x^{-1}=e\in H$.
> 2. If $x,e\in H$, then $ex^{-1}= x^{-1}\in H$.
> 3. If $x,y\in H$, then $y^{-1}\in H$ and $xy=x(y^{-1})^{-1}\in H$.
> 
---
> [!lemma] Proposition 2
> The intersection of arbitrarily many subgroups of $G$ is again a subgroup of $G$.

> [!Proof]-
> Let $\Lambda$ be any let and assume that for every $\lambda\in \Lambda$, $H_{\lambda}\leq G$. Then, for $$H:=\bigcap_{\lambda\in\Lambda}^{}H_{\lambda}$$
> and any $x,y\in H$, we have that $x,y\in H_{\lambda}$ for any $\lambda$. Therefore, $x y^{-1}\in H_{\lambda}$ for any $\lambda\in \Lambda$ and $x  y^{-1}\in H$. Therefore, $H \leq G$.
---
> [!lemma] Proposition 3
> If $G$ is a group and $x\in G$ with order $\text{ord}(x)=n$, then $\braket{ x  }\cong$ [[Cyclic Groups|$C_n$]]. In other words, $\text{ord}(x)=|\braket{ x }|$.

> [!Proof]-
> The group $\braket{  x }$ consists of the elements $x^1,\dots,x^n$ where $x^n=e$.
---
> [!lemma] Lemma 4
> Let $H\subseteq G$ be non-empty. Then, the following are equivalent:
> 1. $H\leq G$
> 2. $HH\subseteq H$ and $H^{-1}\subseteq H$.
> 3. $HH^{-1}\subseteq H$

> [!proof]-
> We show that:
> - (1=>2): For $h_{1}h_{2}\in HH$, as $H$ is a subgroup, $h_{1}h_{2}\in H$. Further, $h^{-1}\in H$. 
> - (2=>3): For $h_{1}h_{2}^{-1}\in H H^{-1}$, as $h_{2}^{-1}\in H$ and $h_{1}h_{2}^{-1}\in H$.
> - (3=>1): Let $h_{1},h_{2}\in H$. Then, $h_{1}h_{2}^{-1}\in H$ and $H\leq G$.
---
> [!lemma] Proposition 5
> For $U,V\leq G$, $UV\leq G$ if and only if $UV=VU$.

> [!proof]-
> Assume that $UV\leq G$. Then, for any $uv\in UV$, we have that $v^{-1}u^{-1}\in UV$, i.e. there exists $\hat{u}\in U$ and $\hat{v}\in V$ s.t. $v^{-1}u^{-1}=\hat{u}\hat{v}$. Then, $uv=(v^{-1}u^{-1})^{-1}=(\hat{u}\hat{v})^{-1}=\hat{v}^{-1}\hat{u}^{-1}\in VU$. On the other hand, for any $vu\in VU$, as $v\in UV$ and $u\in UV$, we have that $vu\in UV$. Therefore, $UV=VU$.
> 
> Conversely, now assume that $UV=VU$. Then, for any $uv,\hat{u}\hat{v}\in UV$, $(uv)(\hat{u}\hat{v})^{-1}=uv\hat{v}^{-1}\hat{u}^{-1}$. As $v\hat{v}^{-1}\hat{u}^{-1}\in VU=UV$, $v\hat{v}^{-1}\hat{u}^{-1}=u^*v^*$ for $u^*\in U$ and $v^*\in V$. Then, $$(uv)(\hat{u}\hat{v})^{-1}=uv\hat{v}^{-1}\hat{u}^{-1}=\underbrace{ uu^*}_{\in U  }v^*\in UV$$ This proves that $UV$ is a subgroup.
---
##### Related Definitions
- [[Coset]]
- [[Centralizer and Normalizer]]
- [[Normal Subgroup]]