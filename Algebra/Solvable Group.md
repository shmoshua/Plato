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
> [!lemma] Lemma 3
> For a group $G$, the following are equivalent:
> 1. $G$ is solvable.
> 2. there exists $r\geq 1$ s.t. the [[Commutator Subgroup|derived series]] $G^{(r)}=\{ e \}$.

> [!proof]+
> 
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