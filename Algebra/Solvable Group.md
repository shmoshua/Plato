#Definition #Algebra 

>[!definition]
>A group $G$ is ***solvable*** if there exists a sequence of subgroups $\{ e \}=G_{0} \unlhd G_{1}\unlhd \cdots \unlhd G_{n}=G$ s.t. for all $1 \leq i \leq n$, it holds that $G_{i}/G_{i-1}$ is abelian.

- **Remark**: Solvable groups play an important role in Galois theory.
- **Remark**: If a group does not have a solvable non-trivial normal divisor, it cannot be solvable.
---
##### Properties
> [!lemma] Theorem 1
> A group $G$ is solvable if and only if for all $H \unlhd G$, $H$ and $G / H$ are solvable.
---
> [!lemma] Theorem 2
> Any group $G$ with $\left| G \right|=p^n$ with $p$ prime is solvable.

> [!proof]-
> We prove using induction over $n$. If $n=1$, we know that it's true. Now assume that it holds for all $n'<n$. 
> 
> We have that by [[Conjugation (Group Theory)]]: $$\left| G \right| =\left| Z(G) \right| +\sum_{i=1}^{n}[G:Z_{G}(x_{j})] $$By taking modulo $p$, $\left| Z(G) \right|\equiv _p 0$. Therefore, $\left| Z(G) \right|=p^m$ for some $1\leq m\leq n$. 
> 
> If $m=n$, then $G=Z(G)$ and $G$ is abelian. Hence, $G$ is solvable. 
> 
> If $m<n$, then $Z(G)\unlhd G$ and $\left| G / Z(G) \right|=p^{n-m}$ and by induction hypothesis, we have that $G / Z(G)$ is solvable. By theorem 1, $G$ is solvable.
---
> [!lemma] Lemma 3 (Solvability and Derived Series)
> For a group $G$, the following are equivalent:
> 1. $G$ is solvable.
> 2. there exists $r\geq 1$ s.t. the [[Commutator Subgroup|derived series]] $G^{(r)}=\{ e \}$.

> [!proof]-
> We have:
> - (2=>1): Then, from [[Commutator Subgroup|Lemma 1]], $G^{(i+1)}\unlhd G^{(i)}$ and $G^{(i)} / G^{(i+1)}$ is abelian. Therefore, $G^{(r)}\unlhd \dots\unlhd G^{(0)}$ is the desired sequence and $G$ is solvable.
> - (1=>2): Assume $G$ is solvable and we have a sequence $\{ e \}=G_{r}\unlhd \dots\unlhd G_{0}=G$. We claim that $G^{(i)}\leq G_{i}$. We will show this by induction. $G\leq G$ holds automatically. For $i\geq 1$, by [[Commutator Subgroup|Lemma 1]], $$G_{i}\geq G_{i-1}^{(1)}\geq (G^{(i-1)})^{(1)}=G^{(i)}$$Therefore, $G^{(r)}\leq G_{r}=\{ e \}$.
- **Related definition**: The ***solvability length*** of a solvable group is $\text{sol}(G):=\min\{ r\geq 1:G^{(r)}=\{ e \} \}$.
---
> [!lemma] Lemma 4 
> Let $N\unlhd G$ and assume that $G^{(r)}\leq N$. Then, $\text{sol}(G / N)\leq r$.

> [!proof]-
> Let $\pi:G\to G / N$ be the canonical projection. Then, $$(G / N)^{(r)}=(\pi(G))^{(r)}=\pi(G^{(r)})=\{ N \}$$
---
###### Solvable Topological Groups
> [!lemma] Theorem 1
> Let $G$ be a solvable Hausdorff group. Then,
> 1. there exists closed groups $\{ e \}=G_{0}\unlhd G_{1}\unlhd\dots\unlhd G_{n}=G$ with $G_{i} / G_{i-1}$ abelian.
> 2. if $G$ is additionally connected, then $G_{i}$ are additionally connected.

> [!proof]-
> We have:
> 1. The proof is by induction on $r:=\text{sol}(G)$. If $r=1$, then $G^{(1)}=\{ e \}$. Therefore $G$ is abelian and $\{ e \}$ is closed.
>    
>    Let $r\geq 2$. Then, by [[Commutator Subgroup|Lemma 1]], $G^{(r-1)}\unlhd G$ and is abelian. Hence, $\overline{G^{(r-1)}}\unlhd G$ by [[Topological Group|Lemma 2.1]] and is abelian by the continuity of multiplication. Moreover, by Lemma 4, $\text{sol}(G / \overline{G^{(r-1)}})\leq r-1$ and by [[Quotient Topology|Lemma 2.3]], $G / \overline{G^{(r-1)}}$ is Hausdorff. Therefore, there exists by inductive hypothesis $$\{ e \}=H_{0}\unlhd\dots\unlhd H_{m}=G / \overline{G^{(r-1)}}$$where $H_{i}$ are closed and $H_{i} / H_{i-1}$ are abelian. Then, consider: $$\{ e \}\unlhd\overline{G^{(r-1)}}=\pi ^{-1}(H_{0})\unlhd \pi ^{-1}(H_{1})\unlhd\dots\unlhd \pi ^{-1}(H_{m})=G$$where $\pi:G\to G / \overline{G^{(r-1)}}$ is the canonical projection. Then, for $h\in \pi ^{-1}(H_{i})$ and $x\in \pi ^{-1}(H_{i+1})$, $$\pi(xhx ^{-1})=\pi(x)\pi(h)\pi(x ^{-1})\in H_{i}$$Therefore, $\pi ^{-1}(H_{i})\unlhd \pi ^{-1}(H_{i+1})$ and $\pi ^{-1}(H_{i})$ is closed by the continuity. Further, for $g,h\in \pi ^{-1}(H_{i})$: $$gh\pi ^{-1}(H_{i-1})=\pi(xH_{i-1})\pi(yH_{i-1})=\pi(yH_{i-1})\pi(xH_{i-1})=hg\pi ^{-1}(H_{i-1})$$Hence, $\pi ^{-1}(H_{i}) / \pi ^{-1}(H_{i-1})$ is abelian. This proves the statement.
> 2. Let $G$ be additionally connected. Then, by [[Commutator Subgroup|Lemma 2]], $G^{(r-1)}$ is connected and by [[Connected Space|Lemma 2]], $\overline{G^{(r-1)}}$ is connected. Then, $G / \overline{G^{(r-1)}}$ is also a connected as a continuous image of $G$ through the canonical projection and for each $H_{i}$, $\pi ^{-1}(H_{i}) / \overline{G^{(r-1)}}=H_{i}$, which is connected. Therefore, by [[Topological Group|Connected Lemma 1]], $\pi ^{-1}(H_{i})$ are connected. This proves the statement.
---
> [!lemma] Corollary 2
> Let $G$ be a connected Lie group that is a solvable group. Then, there exists a sequence: $$\{ e \}=G_{r}\unlhd\dots\unlhd G_{0}=G$$where $G_{i}$ are closed and connected and $G_{i-1} / G_{i}$ is isomorphic to either $\mathbb{R}$ or $\mathbb{T}$.

> [!proof]-
> From Theorem 1, we have: $$\{ e \}=H_{\ell}\unlhd\dots\unlhd H_{0}=G$$with $H_{i}$ is closed connected and $H_{i-1} / H_{i}$ is abelian and connected. By [[Lie Group|Connected Lie group theorem 1]], $H_{i-1} / H_{i}\cong \mathbb{T}^{a_{i}}\times \mathbb{R}^{b_{i}}$. Then, we can replace $H_{i}$ with the pre-image of: $$\{ 0 \}\unlhd \mathbb{T}\unlhd\dots \unlhd \mathbb{T}^{a_{i}}\unlhd \mathbb{T}^{a_{i}}\times \mathbb{R}\unlhd \dots\unlhd \mathbb{T}^{a_{i}}\times \mathbb{R}^{b_{i}}$$
---
##### Examples
- [[Abelian Group]] are solvable by definition with $G_{1}=G$.
- If a group is [[Simple Group|simple]] and non-abelian, it cannot be solvable.
- [[Dihedral Group|$D_n$]] is solvable for all $n\ge 2$, as $\{ e \} \unlhd C_{n}\unlhd D_{n}.$
- [[Symmetry Group|$S_2$]] $\cong C_{2}$ is solvable. (There exists a solution formula for a quadratic equation).
- [[Symmetry Group|$S_3$]] $\cong C_{3}$ is solvable. (There exists a solution formula for a cubic equation).
- The tetrahedron group $T$ is solvable. $\{ e \} \unlhd C_{2}\times C_{2}\unlhd T$ as $T / C_{2} \times C_{2}\cong C_{3}$.
- [[Symmetry Group|$S_4$]] $\cong C$ is solvable as $\{ e \}\unlhd C_{2}\times C_{2}\unlhd T \unlhd C$. (There exists a solution formula for an equation of 4th degree).
- [[Symmetry Group|$S_5$]] is not solvable. (There exists *no* solution formula for an equation of 5th degree). As $S_{5}$ has a subgroup $A_{5}$ s.t. $S_{5} / A_{5} \cong C_{2}$.But $A_{5}$ is the only normal divisor of $S_{5}$. But $A_{5}$ is isomorphic to the dodecahedral group $D$, which is not solvable.
---