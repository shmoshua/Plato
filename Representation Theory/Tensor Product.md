#Definition #RepresentationTheory 

> [!definition]
> For two $K$-[[Vector Space|vector spaces]] $V,W$, the ***tensor product*** $V\otimes W$ is defined as $(V\times W) /U$ where $U$ is the subspace spanned by: $$\begin{align}&(v_{1}+v_{2})\otimes w-v_{1}\otimes w-v_{2}\otimes w\\&v\otimes (w_{1}+w_{2})-v\otimes w_{1}-v\otimes w_{2}\\&av\otimes w-a(v\otimes w)\\&v\otimes aw-a(v\otimes w)\end{align}$$for $v\in V,w\in W,a\in K$.
- **Related definition**: $v\otimes w$ for $v\in V,w\in W$ are called ***pure tensors***.
- **Equivalent definition**: $V\otimes W$ is the [[Free Group|free abelian group]] $F_{\{ v\otimes w \}_{v\in V,w\in W}} / U$ where $U$ is a subgroup spanned by: $$\begin{align}&(v_{1}+v_{2})\otimes w-v_{1}\otimes w-v_{2}\otimes w\\&v\otimes (w_{1}+w_{2})-v\otimes w_{1}-v\otimes w_{2}\\&av\otimes w-v\otimes aw\end{align}$$
- **Remark**: Tensor product is associative: $(V_{1}\otimes V_{2})\otimes V_{3}=V_{1}\otimes(V_{2}\otimes V_{3})$.
- **Related definition**: For $A\in \mathcal{B}(V,V')$ and $B\in \mathcal{B}(W,W')$, the ***tensor product of $A$ and $B$*** is given as: $$\begin{array}{cccc} {A\otimes B:}&{V\otimes W}&\to&{V'\otimes W'}\\&{v\otimes w} &\mapsto & {Av\otimes Bw} \end{array}{}$$
---
##### Properties
> [!lemma] Proposition 1
> Let $M$ be any $K$-vector space and $\text{Bil}(V,W,M)$ be the space of bilinear maps $V\times W\to M$. Then, $$\begin{array}{cccc} {J:}&{\mathcal{B}(V\otimes W,M)}&\to&{\text{Bil}(V,W,M)}\\&{T} &\mapsto & {(v,w)\mapsto T(v\otimes w)} \end{array}{}$$defines a natural bijection.

> [!proof]-
> To check the bilinearity, for $v_{1},v_{2}\in V,w\in W$:$$\begin{align}&J_{T}(v_{1}+v_{2},w)=T((v_{1}+v_{2})\otimes w)=T(v_{1}\otimes w+v_{2}\otimes w)=J_{T}(v_{1},w)+J_{T}(v_{2},w)\\&J_{T}(v,w_{1}+w_{2})=T(v\otimes (w_{1}+w_{2}))=T(v\otimes w_{1}+v\otimes w_{2})=J_{T}(v,w_{1})+J_{T}(v,w_{2})\\&J_{T}(av,w)=T(av\otimes w)=T(a(v\otimes w))=aJ_{T}(v,w)\\&J_{T}(v,aw)=T(v\otimes aw)=T(a(v\otimes w))=aJ_{T}(v,w)\end{align}$$
> Assume that $J_{T}=0$. Then, for any $v\in V,w\in W$, $v\otimes w\in \text{ker }T$, i.e. $V\otimes W \subseteq \text{ker }T$ which means that $T=0$, i.e. $J$ is injective.
> 
> Conversely, let $S\in \text{Bil}(V,W,M)$. Then, let $$\begin{array}{cccc} {T:}&{V\otimes W}&\to&{M}\\&{v\otimes w} &\mapsto & {S(v,w)} \end{array}{}$$To show that $T$ is well-defined, $$\begin{align}&T(v_{1}\otimes w+v_{2}\otimes w)=T(v_{1}\otimes w)+T(v_{2}\otimes w)=S(v_{1}+v_{2},w)=T((v_{1}+v_{2})\otimes w)\\&T(v\otimes w_{1}+v\otimes w_{2})=T(v\otimes w_{1})+T(v\otimes w_{2})=S(v,w_{1}+w_{2})=T(v\otimes (w_{1}+w_{2}))\\&T(av\otimes w)=S(av,w)=aS(v,w)=aT(v\otimes w)=T(a(v\otimes w))\\&T(v\otimes aw)=S(v,aw)=aS(v,w)=aT(v\otimes w)=T(a(v\otimes w))\end{align}$$and by definition, $J_{T}(v,w)=T(v\otimes w)=S(v,w)$ and $J_{T}=S$.
---
> [!lemma] Proposition 2
> If $\{ v_{i} \}_{i}$ is a basis of $V$ and $\{ w_{j} \}_{j}$ is a basis of $W$, $\{ v_{i}\otimes w_{j} \}_{i,j}$ is a basis of $V\otimes W$. 

> [!proof]-
> Clearly $\{ v_{i}\otimes w_{j} \}$ spans $V\otimes W$ by definition. To see the linear independence, let $e_{ij}:V\otimes W\to K$ be s.t. $e_{ij}(v_{i}\otimes w_{j})=1$ and vanishes on any other basis tensor. 
> 
> Assume that $A:=\sum_{i,j}^{}a_{ij}(v_{i}\otimes w_{j})=0$. Then, $e_{ij}(A)=a_{ij}=0$ for all $i,j$.
---
##### Examples

> [!h] Example 1
> Let $V$ be a finite-dimensional vector space. Then, $$\begin{array}{cccc} {J:}&{V^{*}\otimes W}&\to&{\text{Hom}(V,W)}\\&{f\otimes w} &\mapsto & {v\mapsto f(v)w} \end{array}{}$$is an isomorphism.

> [!proof]-
> First we show that $J(f\otimes w)$ is well-defined. $$J(f\otimes w)(v_{1}+v_{2})=f(v_{1})w+f(v_{2})w=J(f\otimes w)v_{1}+J(f\otimes w)v_{2}$$$$J(f\otimes w)(av)=af(v)w=aJ(f\otimes w)v$$
> If $J(f\otimes w)=0$, then either $f=0$ or $w=0$. Therefore, $\text{ker }J=(0)$. Further, for $A\in \text{Hom}(V,W)$, let $f_{i}$ be the basis of $V^{*}$. Then, consider $\sum_{i}^{}f_{i}\otimes A(v_{i})$. $$J\left( \sum_{i}^{}f_{i}\otimes A(v_{i}) \right)(v)=\sum_{i}^{}f_{i}(v)A(v_{i})=A\left( \sum_{i}^{}f_{i}(v)v_{i} \right)=A(v) $$
---
> [!h] Example 2 (Symmetric and Exterior Power)
> Let $V$ be a $K$-vector space. We define: $$S^nV:=V^{\otimes n} / \braket{ T-s(T) :T\in V^{\otimes }n ,s\in \text{Trans}} $$i.e. where $s$ is a transposition. If $\{ v_{i} \}_{i}$ is a basis of $V$, then $\{ v_{i_{1}}\otimes\dots \otimes v_{i_{n}}:i_{1}\leq\dots\leq i_{n} \}$ is the basis of $S^nV$ with dimension ${m+n-1\choose n}$ for $\text{dim} V=m$.
> 
> Similarly, for: $$\land^nV:=V^{\otimes n} / \braket{ s(T)=T  } $$we have $\{ v_{i_{1}}\otimes\dots \otimes v_{i_{n}}:i_{1}<\dots<i_{n} \}$ as a basis with dimension $m \choose n$.
---
