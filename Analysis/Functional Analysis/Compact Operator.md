#Definition #FunctionalAnalysis 
>[!definition]
>A [[Bounded Linear Map|bounded linear operator]] $T: V \to W$ between [[Banach Space|Banach spaces]] is  ***compact***, if $\overline{T(B_{\leq 1}(0))}$ is a compact subset of $W$. In other words, whenever $B \subseteq V$ is bounded, $\overline{T(B)}\subseteq W$ has to be compact.
>
>We denote the set of all compact operators from $V$ to $W$ as: $\mathcal{K}(V,W)\subseteq \mathcal{B}(V,W)$
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\mathcal{K}(V,W)$ is a subspace of $\mathcal{B}(V,W)$.
> 2. If $A\in \mathcal{B}(V,V)$, $T\in \mathcal{K}(V,W)$ and $B\in \mathcal{B}(W,W)$, then: $$B\circ T\circ A\in \mathcal{K}(V,W) $$
> 3. $\mathcal{K}(V,W)$ is closed in $\mathcal{B}(V,W)$ w.r.t. the operator norm.

> [!proof]+
> We have that: 
> 1. As $\{ 0 \}$ is compact, $0\in \mathcal{K}(V,W)$. 
>    
>    For $\lambda\in \mathbb{K}$ and $T\in \mathcal{K}(V,W)$, $$\overline{\lambda T(B_{\leq 1}(0))}=\overline{T(B_{\leq \lambda}(0))}$$which is compact.
>    
>    For $T_{1},T_{2}\in \mathcal{K}(V,W)$, 
> 1. For $T_{1},T_{2}\in \mathcal{K}(V,W)$, $\overline{T_{1}(B(0,1))}$ and $\overline{T_{2}(B(0,1))}$ are compact. Then, of course, $$\alpha\overline{T_{1}(B(0,1))}+\beta\overline{T_{2}(B(0,1))}$$is compact. Then, $$\overline{\alpha T_{1}(B(0,1))+\beta T_{2}(B(0,1))}$$is compact. 
> 2. Holds from the fact that the operators are bounded and $V,W$ are Banach.
> 3. Let $T\in \mathcal{B}(V,W)$ and $(T_{n})_{n}\subseteq \mathcal{K}(V,W)$ s.t. $$\lim_{ n \to \infty } \left\| T_{n}-T \right\| =0$$ We show that $T\in\mathcal{K}(V,W)$, i.e. ${T(B_{\leq 1}(0))}$ is [[Metric Space|totally bounded]]. Let $\varepsilon>0$ and $n$ s.t. $$\left\| T-T_{n} \right\| \leq \varepsilon$$Then, for every $x,y\in B_{\leq 1}(0)$, we have: $$\begin{align}\left\| T(x)-T(y) \right\| &\leq \left\| T(x)-T_{n}(x) \right\| +\left\| T_{n}(x)-T_{n}(y) \right\| +\left\| T(y)-T_{n}(y) \right\| \\&\leq 2\left\| T-T_{n} \right\| +\left\| T_{n}(x)-T_{n}(y) \right\| \end{align}$$As $T_{n}(B_{\leq 1}(0))$ is totally bounded, there exists finite $F \in B_{\leq 1}(0)$ s.t. $$\left\| T_{n}(x)-T_{n}(y) \right\| \leq \varepsilon$$for all $x\in F$ and $y\in B_{\leq 1}(0)$. Therefore, $$\left\| T(x)-T(y) \right\| \leq 3\varepsilon$$for all $x\in F$, $y\in B_{\leq 1}(0)$, which proves that $T(B_{\leq 1}(0))$ is totally bounded.
- **Corollary**: If $T\in \mathcal{B}(V,W)$ is a limit of the sequence $(T_{n})_{n\geq 1}$, where each $T_{n}$ is [[Finite-Rank Linear Operator|finite-rank]], then $T\in \mathcal{K}(V,W)$.
---
##### Examples
- Bounded [[Finite-Rank Linear Operator]]
- Let $\mathcal{H}$ be a [[Separable Space|separable]] [[Hilbert Space|Hilbert space]] with an orthonormal basis $\{e_{i}: i\geq 1 \}$. Then, define: $$\begin{array}{cccc} {T:}&{\underset{ i\geq 1 }{ \oplus}\ \mathbb{C}e_{i}}&\to&{\underset{ i\geq 1 }{ \oplus}\ \mathbb{C}e_{i}} \end{array}{}$$where $T(e_{i})=\lambda_{i}e_{i}$ for $\lambda_{i}\in \mathbb{C}$. Then, 
  1. $T$ extends to a bounded operator $\mathcal{H}\to \mathcal{H}$ if and only if $\sup_{i\geq 1}\left| \lambda_{i} \right|<+\infty$ in which case it coincides with $\left\| T \right\|$. 
  2. $T$ is compact if and only if $\lim_{ i \to \infty }\lambda_{i}=0$.
---
