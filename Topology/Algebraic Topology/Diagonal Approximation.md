#Definition #AlgebraicTopology 

> [!definition]
> A ***diagonal approximation*** $\Delta$ is a collection is a collection of [[chain complex|chain maps]] of the form: $$\Delta:\mathcal{S}_{*}(X)\to \mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(X)$$for all [[topological space]] $X$ s.t.
> 1. $\Delta$ is natural w.r.t. continuous maps $f:X\to Y$, i.e. $\Delta_{Y}\circ f_{c}=(f_{c}\otimes f_{c})\circ\Delta_{X}$
> 2. on degree 0, $\Delta(x)=x\otimes x$ for all $x\in S_{0}(X)$.

---
##### Properties
> [!lemma] Theorem 1 (Uniqueness of Diagonal Approximation Up to Chain Homotopy)
> Let $\Delta,\Delta'$ be two diagonal approximations. Then, 
> 1. $\Delta \sim \Delta'$, i.e. they are [[Chain Homotopy|chain homotopic]] via a chain homotopy natural w.r.t $f:X\to Y$.

> [!proof]+
> We want to show that there exists a chain homotopy: $$D:\mathcal{S}_{*}(X)\to (\mathcal{S}_{*}(X)\otimes  \mathcal{S}_{*}(X))[1]$$that is natural w.r.t. $f:X\to Y$ s.t. $\partial_{\otimes}D+D\partial=\Delta-\Delta'$. 
> 
> We will show that using induction over $n$. 
> 1. If $n=0$, setting $D=0$ suffices as $\Delta(x)=\Delta'(x)$ for all $x\in S_{0}(X)$.
> 2. If $n\geq 1$, assume that $D$ is defined for all $0\leq p<n$ and topological spaces $X$ s.t. it is natural w.r.t. $f:X\to Y$ and $\partial_{\otimes}D+D\partial=\Delta-\Delta'$. 
>    
>    Let $d_{n}:\Delta^n\to \Delta^n,x\mapsto x$ be the identity
---
##### Examples
> [!h] Example 1 (Via Theta)
> Let $\Theta:\mathcal{S}_{*}(X\times X)\to \mathcal{S}_{*}(X)\otimes \mathcal{S}_{*}(X)$ be a chosen map from [[Singular Homology|Eilenberg-Zilberg]]. Then, $$\Delta:\mathcal{S}_{*}(X)\overset{ d_{c} }{ \to } \mathcal{S}_{*}(X\times X)\overset{ \Theta }{ \to } \mathcal{S}_{*}(X)\otimes  \mathcal{S}_{*}(X)$$for $d:X\to X\times X,x\mapsto (x,x)$ is a diagonal approximation.

> [!proof]-
> We have that:
> 1. $\Delta$ is a chain map as $\Theta$ is a chain map.
> 2. Naturality follows that of $\Theta$.
> 3. On degree $0$, $\Delta(x)=\Theta \circ d_{c}(x)=\Theta(x,x)=x\otimes x$.

---
