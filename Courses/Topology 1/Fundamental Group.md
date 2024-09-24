#Definition #Topology 

> [!definition]
> Let $X$ be a [[Topological Space]] and $x\in X$. The ***fundamental group*** of $X$ at $x$ is a [[group]] $\pi_{1}(X,x)$ given by the set of [[Path|path homotopy]] classes of closed paths at $x$ on $X$.
- **Notation**: The fundamental group of $X$ at $x$ is also denoted as $\Lambda_{x,x}$ where $\Lambda_{x,y}$ denotes all path homotopy classes of paths from $x$ to $y$.
- **Related definition**: For $x\in X$, let $\varepsilon_{x}:[0,1]\to X, t\mapsto x$ be the constant path at $x$.
---
##### Properties
> [!lemma] Proposition 1
> We have for $\gamma\in \Lambda_{x,y}$
> 1. $\gamma_{0}(\gamma_{1}\gamma_{2})=(\gamma_{0}\gamma_{1})\gamma_{2}$ for $\gamma_{0}\in \Lambda_{x,y},\gamma_{1}\in \Lambda_{y,z},\gamma_{2}\in \Lambda_{z,w}$.
> 2. $\varepsilon_{x}\gamma=\gamma$, $\gamma \varepsilon_{y}=\gamma$
> 4. $\gamma\overline{\gamma}=\varepsilon_{x}$, $\overline{\gamma}\gamma=\varepsilon_{y}$

> [!proof]-
> We have: 
> 1. Assuming $\gamma_{0},\gamma_{1},\gamma_{2}$ are actual paths, $$\gamma_{0}(\gamma_{1}\gamma_{2})(t)=\begin{cases}\gamma_{0}(2t)&0\leq t\leq \frac{1}{2}\\\gamma_{1}(4t-2)& \frac{1}{2}\leq t\leq \frac{3}{4}\\\gamma_{2}(4t-3)& \frac{3}{4}\leq t\leq 1\end{cases}$$and $$(\gamma_{0}\gamma_{1})\gamma_{2}(t)=\begin{cases}\gamma_{0}(4t)&0 \leq t\leq \frac{1}{4}\\\gamma_{1}(4t-1)& \frac{1}{4}\leq t\leq \frac{1}{2}\\\gamma_{2}(2t-1)& \frac{1}{2}\leq t\leq 1\end{cases}$$Consider the homotopy: $$h(t,s):=\begin{cases}\gamma_{0}\left( \frac{4t}{s+1} \right)&0\leq t\leq \frac{s+1}{4}\\\gamma_{1}(4t-s-1)& \frac{s+1}{4}\leq t\leq \frac{s+2}{4}\\\gamma_{2}\left( \frac{4t-s-2}{2-s} \right)& \frac{s+2}{4}\leq t\leq 1\end{cases}$$Then, $h(0,s)=\gamma_{0}(0)=x$ and $h(1,s)=\gamma_{2}(1)=w$. As $h$ is continuous, it is a path-homotopy and $$h(t,0)=(\gamma_{0}\gamma_{1})\gamma_{2}(t), \quad h(t,1)=\gamma_{0}(\gamma_{1}\gamma_{2})(t)$$
> 2. We have that: $$\varepsilon_{x}\gamma(t)=\begin{cases}x&0\leq t\leq \frac{1}{2}\\\gamma(2t-1)& \frac{1}{2}\leq t\leq 1\end{cases}$$with homotopy: $$h(t,s)=\begin{cases}x&0\leq t\leq \frac{1 -s}{2}\\\gamma\left(  \frac{2}{1+s}t+1 -\frac{2}{1+s} \right)& \frac{1-s}{2}\leq t\leq 1\end{cases}$$Then, $h(0,s)=x, h(1,s)=\gamma(1)$ with $h(t,0)=\varepsilon_{x}\gamma(t)$ and $h(t,1)=\gamma(t)$.
>    
>    Similarly, it holds for $\gamma \varepsilon_{y}=\gamma$.
> 3. We have: $$\gamma\overline{\gamma}(t)=\begin{cases}\gamma(2t)&0\leq t \leq \frac{1}{2}\\\gamma(2-2t)& \frac{1}{2}\leq t\leq 1\end{cases}$$Then, for$$h(t,s):=\begin{cases}\gamma(2st)&0\leq t\leq 1 /2\\\gamma(2s(1-t))& 1/2\leq t\leq 1\end{cases}$$$h(0,s)=\gamma(0)=x$ and $h(1,s)=\gamma(0)=x$ and $h(t,0)=x=\varepsilon_{x}(t)$ and $h(t,1)=\gamma\overline{\gamma}(t)$. 

- **Corollary**: $\pi_{1}(X,x)$ is indeed a group with path composition and path inversion.
---
> [!lemma] Proposition 2 (Functoriality of $\pi_{1}$)
> Let $X,Y,Z$ be topological spaces and $x_{0}\in X$. For a continuous $f:X\to Y$ and $g:Y,Z$, 
> 1.  $f_{*}:\pi_{1}(X,x_{0})\to \pi_{1}(Y,f(x_{0})), \gamma\mapsto f\circ \gamma$ is a group homomorphism.
> 2. $(g\circ f)_{{*}}=g_{*}\circ f_{*}$
> 3. $(\text{id}_{X})_{*}=\text{id}_{\pi_{1}(X,x_{0})}$.

> [!proof]-
> We have:
> 1. We check that $f_{*}$ is well-defined. For $\gamma_{1},\gamma_{2}$ s.t. $\gamma_{1}\sim\gamma_{2}$, let $h$ be the path homotopy. Then, $f(h(t,0))=f(\gamma_{1}(t))$ and $f(h(t,1))=f(\gamma_{2}(t))$. Further, $f(h(0,s)),f(h(1,s))$ are constant. Therefore, $f\circ h$ is a path homotopy from $f\circ\gamma_{1}$ to $f\circ\gamma_{2}$. 
>    
>    Further, it is a group homomorphism as $f\circ(\gamma_{1}\gamma_{2})(t)=(f\circ\gamma_{1})(f\circ\gamma_{2})(t)$.
> 2. Obvious.
> 3. Obvious.
- **Corollary**: For a homeomorphism $f:X\to Y$, $f_{*}:\pi_{1}(X,x_{0})\cong \pi_{1}(Y,f(x_{0}))$ for all $x_{0}\in X$.
---
> [!lemma] Proposition 3 (Fundamental Group of Product Spaces)
> For topological spaces $X,Y$ and $p,q$ projections from $X\times Y$ to respective spaces. Then, for all $(x,y)\in X\times Y$,$$\alpha:\pi_{1}(X\times Y,(x,y))\to \pi_{1}(X,x)\times \pi_{1}(Y,y),\quad \gamma\mapsto (p_{*}(\gamma),q_{*}(\gamma))$$is a group isomorphism.

> [!proof]-
> We have:
> 1. $\alpha$ is a group homomorphism as $p_{*}$ and $q_{*}$ are respectively by Proposition 2.1.
> 2. $\alpha$ is injective: let $\gamma:[0,1]\to X\times Y$ be a path s.t. $p_{*}(\gamma)=\varepsilon_{x}$ and $q_{*}(\gamma)=\varepsilon_{y}$ with path homotopies $h_{1},h_{2}$ from $p\circ\gamma$ to $\varepsilon_{x}$ and from $q\circ\gamma$ to $\varepsilon_{y}$ respectively. Then, $$h(t,s):=(h_{1}(t,s),h_{2}(t,s))$$is a path homotopy from $\gamma$ to $\varepsilon_{(x,y)}$.
> 3. $\alpha$ is surjective: For $\gamma_{1},\gamma_{2}$ closed paths in $X$ and $Y$ at $x$ and $y$ respectively, we have that: $$\gamma:[0,1]\to X\times Y,\quad t\mapsto (\gamma_{1}(t),\gamma_{2}(t))$$is a closed path at $(x,y)$ s.t. $\alpha(\gamma)=(\gamma_{1},\gamma_{2})$.
---
> [!lemma] Proposition 4
> Let $X$ be a topological space and $x,y\in X$. If there exists a path $\alpha:[0,1]\to X$ from $x$ to $y$, $$i_{\alpha}:\pi_{1}(X,y)\to \pi_{1}(X,x),\quad \gamma\mapsto \alpha\gamma\overline{\alpha}$$is a group isomorphism.

> [!proof]-
> For $\gamma_{1},\gamma_{2}$ closed paths at $y$ with $\gamma_{1}\sim\gamma_{2}$, let $h$ be the path homotopy from $\gamma_{1}$ to $\gamma_{2}$. Then, $$\widehat{h}(t,s):=\begin{cases}\alpha(3t)& 0\leq t\leq \frac{1}{3}\\h(3t-1,s)& \frac{1}{3}\leq t\leq \frac{2}{3}\\\alpha(3-3t)& \frac{2}{3}\leq t\leq 1\end{cases}$$Then, $\widehat{h}(t,0)=i_{\alpha}(\gamma_{1})(t)$ and $\widehat{h}(t,1)=i_{\alpha}(\gamma_{2})(t)$. Further, $\widehat{h}(0,s)=x$ and $\widehat{h}(1,s)=x$. Hence, $\widehat{h}$ is a path homotopy from $i_{\alpha}(\gamma_{1})$ to $i_{\alpha}(\gamma_{2})$.
> 
> Further, $$i_{\alpha}(\gamma_{1}\gamma_{2})=\alpha\gamma_{1}\gamma_{2}\overline{\alpha}=\alpha\gamma_{1}\overline{\alpha}\alpha\gamma_{2}\overline{\alpha}=i_{\alpha}(\gamma_{1})i_{\alpha}(\gamma_{2})$$It is therefore an isomorphism as $i_{\overline{\alpha}}$ is its inverse.
- **Corollary**: if $X$ is [[Path-Connected Space|path-connected]], all of its fundamental groups are isomorphic.
- **Remark**: the concrete isomorphism in the proposition depends on the path $\alpha$.
---
![[Contractible Space#^f327ea]]
![[Contractible Space#^87c949|p]]

---
> [!lemma] Theorem (Topological Group)
> Let $G$ be a [[topological group]] that is path-connected, locally path-connected and semi-locally simply connected. Then,
> 1. $\pi_{1}(G,e)$ is abelian.

> [!proof]+
> We have by the [[Universal Cover|universal covering theorem]] that there exists a universal cover $p:H\to G$. Now we use the well-known fact that if $H$ and $G$ are path-connected and locally path-connected then for any $e^{*}\in p ^{-1}(e)$, we can endow $H$ with a topological group structure s.t. $e^{*}$ becomes the identity and $p$ becomes a group homomorphism.
> 
> Then, $\text{ker }p$ becomes a discrete normal subgroup of $H$. As $H$ is connected, by [[Topological Group|Connected group Proposition 1]], $\text{ker }p\subseteq Z(G)$. 
> 
> The statement then follows by the fact that $\text{ker }p\cong \pi_{1}(G,e)$.
---
##### Examples
> [!h] Example 1
> We have that:
> 1. $\pi_{1}(S^1,1)\cong \mathbb{Z}$.
> 2. $\pi_{1}(\mathbb{R}^n,x)=\{ \varepsilon_{x} \}$ for all $x\in \mathbb{R}^n$.
> 3. for any convex $A\subseteq \mathbb{R}^n$, $\pi_{1}(A,x)=\{ \varepsilon_{x} \}$ for all $x\in A$.
> 4. $\pi_{1}(\mathbb{R}^n / \mathbb{Z}^n,0)\cong \mathbb{Z}^n$ by Proposition 3.
---
