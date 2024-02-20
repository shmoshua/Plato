#Definition #Algebra

> [!definition]
> Let $G$ be a group. Then, the group of ***inner automorphisms*** of $G$ $\text{Inn}(G)\subseteq \text{Aut}(G)$ is defined as: $$\text{Inn}(G):=\{ \varphi_{\sigma}\in \text{Aut}(G):\forall g \in G, \varphi_{\sigma}(g)=\sigma g\sigma^{-1} \}$$
---
##### Properties
> [!lemma] Proposition 1
> $\text{Inn}(G)\unlhd \text{Aut}(G)$

> [!proof]-
> For $\varphi_{\sigma}\in \text{Inn}(G)$ and $\phi\in \text{Aut}(G)$, $$(\phi\varphi_{\sigma}\phi ^{-1})(x)=\phi(\sigma \phi ^{-1}(x)\sigma ^{-1})=\phi(\sigma)x\phi(\sigma)^{-1}=\varphi_{\phi(\sigma)}(x)$$
---
> [!lemma] Lemma 2
> We have that: $$\text{Inn}(G)\cong G / Z(G)$$

>[!proof]-
>Using the [[Group Homomorphism|First Isomorphism Theorem]], we define $F:= G \to \text{Inn}(G), \sigma \to \varphi_{\sigma}$. This is a homomorphism as: $$F(\sigma_{1}\sigma_{2})(g)=\sigma_{1}\sigma_{2}g\sigma_{2}^{-1}\sigma_{1}^{-1}=\sigma_{1}F(\sigma_{2})(g)\sigma_{1}^{-1}=F(\sigma_{1})(F(\sigma_{2})(g))$$Then, $\text{ker}F=\{ \sigma\in G:\varphi_{\sigma}(g)=g, \forall g\in G \}=\{ \sigma\in G:\sigma g\sigma^{-1}=g, \forall g\in G \}=Z(G)$.
---
> [!lemma] Theorem 3
> If $\text{Inn}(G)$ is cyclic, then $G$ is abelian.

> [!proof]-
> If $\text{Inn}(G)$ is cyclic, from Lemma 2, $G / Z(G)$ is cyclic. Therefore, there exists $g Z(G)$. For arbitrary $a,b\in G$, we have that: $$aZ(G)=g^mZ(G),\quad bZ(G)=g^nZ(G)$$
> Then, $g^{-m}a\in Z(G)$ and $g^{-n}b\in Z(G)$. From which, $a=xg^m$ and $b=yg^n$ for $x,y\in Z(G)$. Therefore, $$ab=xg^m yg^n=yg^{m+n}x=yg^n xg^m=ba$$
