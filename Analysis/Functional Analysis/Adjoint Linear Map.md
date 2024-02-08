#Definition #Analysis #FunctionalAnalysis 

> [!definition]
> Let $T\in \mathcal{B}(V,W)$ be a [[bounded linear map]] of [[Analysis/Normed Space|normed $\mathbb{K}$-vector spaces]]. The ***adjoint***  of $T$ is the linear map: $$\begin{array}{cccc} {T^{*}:}&{W^{*}}&\to&{V^{*}}\\&{\lambda} &\mapsto & {\lambda \circ T} \end{array}{}$$
> where $V^{*},W^{*}$ are the [[Dual Space|dual spaces]] of $V,W$. 

- **Related definition**: For a Hilbert space $\mathcal{H}$ and $T\in \mathcal{B}(\mathcal{H})$, if $T^{*}=T$, then $T$ is called ***self-adjoint/Hermitian***.
---
##### Properties
> [!lemma] Proposition 1
> For a bounded linear map $T\in \mathcal{B}(V,W)$, 
> 1. $T^{*}\in \mathcal{B}(W^{*},V^{*})$.
> 2. $\left\| T^{*} \right\|=\left\| T \right\|$

> [!proof]-
> We have that:
> 1. for $T\in \mathcal{B}(V,W)$$$\left| T^{*}(\lambda)(x) \right|=\left| \lambda(T(x)) \right| \leq \left\| \lambda \right\| \left\| T \right\| \|x\| $$
> which implies: $$\left\| T^{*} (\lambda)\right\|\leq \left\| T \right\| \cdot \left\| \lambda \right\|  $$Therefore, $$\left\| T^* \right\| \leq \left\| T \right\| $$
> 2. We have: $$\begin{align}\left\| T^{*} \right\| &=\sup_{\|\lambda\|\leq 1}\left\| T^{*} \lambda \right\| =\sup_{\left\| \lambda \right\| \leq 1}\sup_{\|v\|\leq 1}\left| \lambda(Tv) \right| =\sup_{\|v\|\leq 1}\sup_{\left\| \lambda \right\| \leq 1}\left| \lambda(Tv) \right| =\sup_{\|v\|\leq 1}\|Tv\|=\|T\|\end{align}$$from [[Dual Space|Corollary 2]].
---
##### Examples
- Let $\mathcal{H}_{1},\mathcal{H}_{2}$ be [[Hilbert Space]]. Then, the [[Riesz map]]:$$\begin{array}{cccc} {i:}&{\mathcal{H}}&\to&{\mathcal{H}^{*}}\\&{v} &\mapsto & {i(v)} \end{array}{}$$where $i(v)(w):=\braket{ w,v  }$ is bijective. Let $T\in \mathcal{B}(\mathcal{H}_{1},\mathcal{H}_{2})$ and $T^*:\mathcal{H}_{2}^{*}\to \mathcal{H}_{1}^{*}$. Then,$$\begin{CD}\mathcal{H}_{2}@>i_{2}>> \mathcal{H}_{2}^{*}\\@VT'VV @VVT^*V\\\mathcal{H}_{1}@>>i_{1}> \mathcal{H}_{1}^*\end{CD}$$and $T':=i_{1}^{-1}\circ T^{*}\circ i_{2}\in \mathcal{B}(\mathcal{H}_{2},\mathcal{H}_{1})$. It follows that $$\braket{ T(v) , w } =\braket{ v , T'(w) } $$for all $v\in \mathcal{H}_{1},w\in \mathcal{H}_{2}$. Therefore, we will use $T'$ to denote $T^{*}$ (with abuse of notations).
---
