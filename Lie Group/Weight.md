#Definition #RepresentationTheory #LieGroups 

> [!definition]
> Let $G$ be a [[Lie group]] and $\rho:G\to \text{GL}(V)$ be a [[Lie group representation]] to a $\mathbb{C}$-vector space $V$. A ***weight*** of $G$ in $V$ is a group homomorphism $\chi:G\to \mathbb{C}^\times$ s.t. 
> 1. $V_{\chi}:=\{ v\in V:\rho(g)v=\chi(g)v,\forall g\in G \}\neq \{ 0 \}$.

- **Related definition**: For weight $\chi$, $V_{\chi}$ is called the ***weight space*** of $\chi$ and any non-zero element in $V_{\chi}$ is called a ***weight vector.***
---
##### Properties
> [!lemma] Proposition 1
> Any weight $\chi$ is smooth.

> [!proof]-
> By [[Lie Group|Proposition 5.2]], it suffices to show that $\chi$ is continuous. Let $0\neq v\in V_{\chi}$ be a weight vector. Let $(g_{n})_{n}\subseteq G$ s.t. $g_{n}\to 0$. Then, $$\lim_{ n \to \infty } \left| \chi(g_{n}) \right| = \frac{1}{\left| v \right| }\lim_{ n \to \infty } \left| \rho(g_{n})v \right|=0 $$Hence, $\chi$ is continuous. 
---
> [!lemma] Lemma 2
> Let $G$ be a connected Lie group and $\rho:G\to \text{GL}(V)$ a complex representation. For $H\unlhd G$ and a weight $\chi:H\to \mathbb{C}^\times$ w.r.t. $\rho|_{H}$, 
> 1. $V_{\chi}$ is an $G$-invariant subspace.

> [!proof]-
> Let $g\in G$, $h\in H$ and $v\in V_{\chi}$. Then,$$\rho(h)\rho(g)v=\rho(g)\rho(\underbrace{ g^{-1}hg }_{ \in H })v=\chi(g ^{-1}hg)\rho(g)v$$And $\chi(g^{-1}hg)\in \text{Spec}(\rho(h))$ for all $g\in G$. Therefore, $G\to \text{Spec}(\rho(h)),g\mapsto \chi(g ^{-1}hg)$ is a continuous function and as $G$ is connected, the image is connected. However, as $\text{Spec}(\rho(h))$ is a discrete set, the function is constant and $\chi(g^{-1}hg)=\chi(h)$ for all $g\in G$. Therefore, $$\rho(h)\rho(g)v=\chi(h)\rho(g)v$$and $\rho(g)v\in V_{\chi}$.
---
> [!lemma] Theorem 3 (Existence of Weights for Connected Solvable Lie Groups)
> Let $G$ be a connected solvable Lie group. Then, for any complex representation $\rho:G\to \text{GL}(V)$, 
> 1. there exists a weight $\chi$ of $G$ in $V$.

> [!proof]-
> We proceed with induction over $n:=\text{dim}(G)$. 
> 
> If $n=1$, then $\text{dim }\mathfrak{g}=1$. Hence, there exists $x\in \mathfrak{g}$ s.t. $\mathfrak{g}=\mathbb{R}x$. Let $0\neq v_{0}$ be an eigenvector of $d_{e}\rho(x)$, which exists as any complex matrix has an eigenvector. Then, $$d_{e}\rho(\lambda x)\mathbb{C}v=\lambda d_{e}\rho(x)\mathbb{C}v\subseteq \mathbb{C}v,\quad \forall\lambda\in \mathbb{R}$$Then, $x\in \mathfrak{stab}(\mathbb{C}v)$ and as  $G$ is connected, $\exp:\mathfrak{g}\to G$ is surjective and by [[Lie Group Representation|Proposition 1]]:$$\rho(G)\mathbb{C}v\subseteq \mathbb{C}v$$ By defining $\chi:G\to \mathbb{C}$ s.t. $\rho(g)v=\chi(g)v$, we have that: $$\chi(g_{1}g_{2})v=\rho(g_{1}g_{2})v=\rho(g_{1})\rho(g_{2})v=\chi(g_{2})\rho(g_{1})v=\chi(g_{1})\chi(g_{2})v$$and $\chi(g_{1}g_{2})v=\chi(g_{1})\chi(g_{2})$. 
> 
> For $n\geq 2$, by [[Solvable Group|Corollary 2]], we can find $H\unlhd G$ s.t. $H$ is connected, closed and $G / H$ is isomorphic to $\mathbb{T}$ or $\mathbb{R}$. As $\text{dim }H<n$, we have a weight $\chi:H\to \mathbb{C}^\times$. By Lemma 2, $V_{\chi}$ is $G$-invariant. Hence, for $v\in V_{\chi}$,$$d_{e}\rho(x)v=\left. \frac{d}{dt} \right| _{t=0}\rho(\exp(tx))v\in V_{\chi},\quad \forall x\in \mathfrak{g}$$It follows that $d_{e}\rho(x)\in \mathfrak{\text{End}}(V_{\chi})$ for all $x\in \mathfrak{g}$. 
> 
> Then, as $H$ is closed, it is a Lie group and for $v\in V_{\chi}$ and $h\in H$, we have: $\rho(h)v=\chi(h)v$. Then, $$d_{e}\rho(x)v=\left. \frac{d}{dt} \right| _{t=0}\rho(\exp(tx))v=\left. \frac{d}{dt} \right| _{t=0}\chi(\exp(tx))v=d_{e}\chi(x)v,\quad \forall x\in \mathfrak{h}$$Therefore, we can write $\mathfrak{g}=\mathbb{R}y\oplus \mathfrak{h}$ for some $y\in \mathfrak{g}$ as $\mathfrak{h}$ is a subspace of $\mathfrak{g}$ of codimension 1. Now, as $d_{e}\rho(y)\in \text{End}(V_{\chi})$, let $v_{0}\in V_{\chi} \backslash\{ 0 \}$ be an eigenvector of $d_{e}\rho(y)$. It follows that: $$d_{e}\rho(z)\mathbb{C}v_{0}\subseteq \mathbb{C}v_{0},\quad z\in \mathfrak{g}$$As $G$ is connected again, $\exp:\mathfrak{g}\to G$ is surjective and and by [[Lie Group Representation|Proposition 1]] we get: $$\rho(g)\mathbb{C}v_{0}\subseteq \mathbb{C}v_{0},\quad \forall g\in G$$This shows that there exists a weight $\chi$.
---
##### Examples


> [!h] Example 1
> Consider: $$G:=\left\{ \begin{bmatrix}a&b\\0&c\end{bmatrix} :a,c\neq 0\right\}$$
> and inclusion: $\rho:G\to \text{GL}(2,\mathbb{R})$. 
> 1. The only weight is given as: $$\chi:G\to \mathbb{C}^\times,\quad \begin{bmatrix}a&b\\0&c \end{bmatrix}\mapsto a$$with $V_{\chi}=\left\langle\begin{bmatrix}1\\0\end{bmatrix} \right\rangle$.
---
> [!h] Example 3 (Heisenberg Lie Group)
> Consider: $$H:=\left\{ \begin{bmatrix}1&a&b\\0&1&c\\0&0&1\end{bmatrix} :a,b,c\in \mathbb{R}\right\}$$
> and inclusion: $\rho:H\to \text{GL}(3,\mathbb{R})$. 
> 1.  The only weight is $\chi \equiv 1$, with $V_{\chi}=\left\langle\begin{bmatrix}1\\0\\0\end{bmatrix}\right\rangle$
---
> [!h] Example 4 (Special Linear Group)
> For $\text{SL}(2,\mathbb{R})$ and inclusion $\rho:\text{SL}(2,\mathbb{R})\to \text{GL}(2,\mathbb{R})$, there exists no weights.
---
