#Definition #LieGroups 

> [!definition]
> Let $G,H$ be [[Topological Group|topological groups]]. A ***local homomorphism*** is a pair $(\varphi,U)$ where $e\in U\subseteq G$ and $\varphi:U\to H$ s.t. whenever $\{ x,y,xy \}\subseteq U$, $$\varphi(xy)=\varphi(x)\varphi(y)$$
> Additionally, if $\varphi:U\to\varphi(U)$ is a [[Homeomorphism]], $(\varphi,U)$ is a ***local isomorphism***.
---
##### Properties
> [!lemma] Theorem 1 (Extension of Local Homomorphisms)
> If $G$ is a [[Simply Connected Space|simply connected]] topological group, 
> 1. any local homomorphism $\varphi:U\to H$ extends uniquely to a continuous group homomorphism $G\to H$.

> [!proof]-
> We have:
> 1. **Defining the extension**:
>    As $G$ is simply connected, it is path-connected. For all $g\in G$, let $\gamma:[0,1]\to G$ be a path from $e$ to $g$. Choose a partition of $[0,1]$ into subintervals $I_{k}:=[t_{k-1},t_{k}]$, for $k=1,\dots,n$, with the property that if $s,t\in I_{k}$, $\gamma(s)^{-1}\gamma(t)\in U$.
>    
>    For $x_{k}:=\gamma(t_{k})$, we get: $g=(x_{0}^{-1}x_{1})(x_{1}^{-1}x_{2})\dots(x_{n-1}^{-1}x_{n})$. Then, $$\varphi_{\gamma}(g):=\varphi(x_{0}^{-1}x_{1})\varphi(x_{1}^{-1}x_{2})\dots\varphi(x_{n-1}^{-1}x_{n})$$which is independent of the choice of the partition: Assume we take $I_{k}$ and write $[t_{k-1},t_{k}]=[t_{k-1},t]\cup[t,t_{k}]$. Then, since $t\in I_{k}$, $\gamma (t_{k-1})^{-1}\gamma(t),\gamma(t)^{-1}\gamma(t_{k})\in U$ and: $$\varphi(\gamma(t_{k-1})^{-1}\gamma(t_{k}))=\varphi(\gamma(t_{k-1})^{-1}\gamma(t))\varphi(\gamma(t)^{-1}\gamma(t_{k}))$$
>    The continuity then follows from the fact that it is continuous at $e$. 
> 2. **Showing the extension $\varphi$ is well-defined**:
>    We show that $\varphi$ is independent of the path $\gamma$. Let $\gamma_{0},\gamma_{1}$ be two paths from $0$ to $g$ and since $G$ is simply connected, let $h$ be a [[Topology/Path|path homotopy]] from $\gamma_{0}$ to $\gamma_{1}$. We further define, $\gamma_{s}(t):=h(t,s)$. 
>    
>    Let $W\subseteq U$ be an open symmetric neighborhood of $e\in G$ s.t. $W^2\subseteq U$ (given by [[Topological Group|Lemma 3]]).  By continuity we can find $\delta>0$ with: $\gamma_{s_{1}}(t_{1})^{-1}\gamma_{s_{2}}(t_{2})\in W$ for all $\left| s_{1}-s_{2} \right|+\left| t_{1}-t_{2} \right|<\delta$. By setting $t_{k}=k /n$ with $1 /n<\delta$, we have: $$\gamma_{s}(t_{k-1})^{-1}\gamma_{s}(t_{k})\in W$$By defining $\varphi_{s}:=\varphi_{\gamma_{s}}$, we want to show that: $$A:=\{ s\in [0,1]:\varphi_{s}(g)=\varphi_{0}(g) \}$$is both open and closed in $[0,1]$. Then, as $0\in A$, the statement is proven by connectedness.
>    
>    To show that $A$ is closed, let's show that if $s_{j}\to s$ then $s\in A$. Let $\{ t_{k} \}_{k}$ be a good partition as above. Because of the continuity of $h$, we have that: $$\lim_{ j \to \infty } \gamma_{s_{j}}(t_{k})=\gamma_{s}(t_{k})$$As $\varphi_{s_{j}}$ are continuous, we have that: $$\lim_{ j \to \infty } \varphi(\gamma_{s_{j}}(t_{k})^{-1}\gamma_{s_{j}}(t_{k+1}))=\varphi_{s}(\gamma_{s}(t_{k})^{-1}\gamma_{s}(t_{k+1}))$$Therefore, $$\varphi_{0}(g)=\lim_{ j \to \infty } \varphi_{s_{j}}(g)=\lim_{ j \to \infty } \prod_{k=0}^{n-1}\varphi(\gamma_{s_{j}}(t_{k})^{-1}\gamma_{s_{j}}(t_{k+1}))=\prod_{k=0}^{n-1}\varphi_{s}(\gamma_{s}(t_{k})^{-1}\gamma_{s}(t_{k+1}))=\varphi_{s}(g)$$This shows that $A$ is closed. 
>    
>    To show that $A$ is open, we can write: $$\underbrace{ \gamma_{s}(t_{k-1})^{-1}\gamma_{s}(t_{k}) }_{ \in W }=\underbrace{ \gamma_{s}(t_{k-1})^{-1}\gamma_{r}(t_{k-1}) }_{ \in W }\underbrace{ [\gamma_{r}(t_{k-1})^{-1}\gamma_{r}(t_{k})]\gamma_{r}(t_{k})^{-1}\gamma_{s}(t_{k}) }_{ \in U }$$Therefore, by the local homomorphism, $$\varphi( \gamma_{s}(t_{k-1})^{-1}\gamma_{s}(t_{k}) )= \varphi(\gamma_{s}(t_{k-1})^{-1}\gamma_{r}(t_{k-1}))\varphi(\gamma_{r}(t_{k-1})^{-1}\gamma_{r}(t_{k}))\varphi(\gamma_{r}(t_{k})^{-1}\gamma_{s}(t_{k}))$$Then, $$\begin{align}\varphi_{s}(g)&=\prod_{k=1}^{n}\varphi(\gamma_{s}(t_{k-1})^{-1}\gamma(t_{k}))\\&=\underbrace{ \varphi(\gamma_{s}(t_{0})^{-1}\gamma_{r}(t_{0})) }_{ =e }\prod_{k=1}^{n}\varphi(\gamma_{r}(t_{k-1})^{-1}\gamma_{r}(t_{k}))\underbrace{ \varphi(\gamma_{r}(t_{n})^{-1}\gamma_{s}(t_{n})) }_{ =e }=\varphi_{r}(g)\end{align}$$It follows that $\varphi$ is well-defined.
>  3. **Showing $\varphi$ is a continuous homomorphism**:
>     To see that it is a homomorphism, let $\gamma$ be a path from $e$ to $g$ and $\alpha$ a path from $e$ to $h$. Then $\gamma*g\alpha$ is a path from $e$ to $gh$ and by definition $\varphi(gh)=\varphi(g)\varphi(h)$.
- **Corollary**: For a path-connected, locally path-connected and [[Semi-Locally Simply Connected Space|semi-locally simply connected]] topological group $G$ with its [[Universal Cover|universal covering]] $p:\tilde{G} \to G$, then for any local homomorphism $(\varphi,U)$, $\varphi \circ p$ is a local homomorphism from $V$ to $H$ s.t. $p(V)\subseteq U$ and $\varphi \circ p$ extends to a continuous homomorphism $\tilde{G}\to H$.
---
##### Examples
> [!h] Example 1
> $\mathbb{R}$ and $\mathbb{T}$ are locally isomorphic.
---
