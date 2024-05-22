#Definition #LieGroups 

> [!definition]
> Let $G,H$ be [[Topological Group|topological groups]]. A ***local homomorphism*** is a pair $(\varphi,U)$ where $e\in U\subseteq G$ and $\varphi:U\to H$ s.t. whenever $\{ x,y,xy \}\subseteq U$, $$\varphi(xy)=\varphi(x)\varphi(y)$$
> Additionally, if $\varphi:U\to\varphi(U)$ is a [[homeomorphism]], $(\varphi,U)$ is a ***local isomorphism***.
---
##### Properties
> [!lemma] Theorem 1 (Extension of Local Homomorphisms)
> If $G$ is a [[simply connected]] topological group, then any local homomorphism $\varphi:U\to H$ extends uniquely to a continuous homomorphism $G\to H$.

> [!proof]+
> We have:
> 1. **Defining the extension**:
>    As $G$ is simply connected, it is path-connected. For all $g\in G$, let $\gamma:[0,1]\to G$ be a path from $e$ to $g$. Choose a partition of $[0,1]$ into subintervals $I_{k}:=[t_{k-1},t_{k}]$, for $k=1,\dots,n$, with the property that if $s,t\in I_{k}$, $\gamma(s)^{-1}\gamma(t)\in U$.
>    
>    For $x_{k}:=\gamma(t_{k})$, we get: $g=(x_{0}^{-1}x_{1})(x_{1}^{-1}x_{2})\dots(x_{n-1}^{-1}x_{n})$. Then, $$\varphi_{\gamma}(g):=\varphi(x_{0}^{-1}x_{1})\varphi(x_{1}^{-1}x_{2})\dots\varphi(x_{n-1}^{-1}x_{n})$$which is independent of the choice of the partition: Assume we take $I_{k}$ and write $[t_{k-1},t_{k}]=[t_{k-1},t]\cup[t,t_{k}]$. Then, since $t\in I_{k}$, $\gamma (t_{k-1})^{-1}\gamma(t),\gamma(t)^{-1}\gamma(t_{k})\in U$ and: $$\varphi(\gamma(t_{k-1})^{-1}\gamma(t_{k}))=\varphi(\gamma(t_{k-1})^{-1}\gamma(t))\varphi(\gamma(t)^{-1}\gamma(t_{k}))$$
> 2. **Showing the extension $\varphi$ is well-defined**:
>    We show that $\varphi$ is independent of the path $\gamma$. Let $\gamma_{0},\gamma_{1}$ be two paths from $0$ to $g$ and since $G$ is simply connected, let $h$ be a homotopy from $\gamma_{0}$ to $\gamma_{1}$. We further define, $\gamma_{s}(t):=h(s,t)$. 
>    
>    Let $W\subseteq U$ be an open neighborhood of $e\in G$ s.t. $W=W^{-1}$, $W^2\subseteq U$ and let $\delta>0$ with: $H(s_{1},t_{1})^{-1}H(s_{2},t_{2})\in W$ for all $\left| s_{1}-s_{2} \right|+\left| t_{1}-t_{2} \right|<\delta$.By setting $t_{k}=k /n$ with $1 /n<\delta$, we have: $$\gamma_{s}(t_{k-1})^{-1}\gamma_{s}(t_{k})\in W$$Further, for fixed $k$, and $s,r$ s.r. $\left| s-r \right|<\delta$, we have: $$\gamma_{s}(t_{k})^{-1}\gamma_{r}(t_{k})\in W$$Now, we write: $$\underbrace{ \gamma_{s}(t_{k-1})^{-1}\gamma_{s}(t_{k}) }_{ \in W }=\underbrace{ \gamma_{s}(t_{k-1})^{-1}\gamma_{r}(t_{k-1}) }_{ \in W }\underbrace{ [\gamma_{r}(t_{k-1})^{-1}\gamma_{r}(t_{k})]\gamma_{r}(t_{k})^{-1}\gamma_{s}(t_{k}) }_{ \in U }$$Therefore, by the local homomorphism, $$\varphi( \gamma_{s}(t_{k-1})^{-1}\gamma_{s}(t_{k}) )= \varphi(\gamma_{s}(t_{k-1})^{-1}\gamma_{r}(t_{k-1}))\varphi(\gamma_{r}(t_{k-1})^{-1}\gamma_{r}(t_{k}))\varphi(\gamma_{r}(t_{k})^{-1}\gamma_{s}(t_{k}))$$Then, $$\varphi_{\gamma_{s}}(g)=\prod_{k=1}^{n}\varphi(\gamma_{s}(t_{k-1})^{-1}\gamma(t_{k}))=\varphi(\gamma_{s}(t_{0})^{-1}\gamma_{r}(t_{0}))\prod_{k=1}^{n}\varphi(\gamma_{r}(t_{k-1})^{-1}\gamma_{r}(t_{k}))\varphi(\gamma_{r}(t_{n})^{-1}\gamma_{s}(t_{n}))$$