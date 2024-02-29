#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. For $p\in M$, the ***tangent space*** is defined as: $$\text{T}_{p}M=\{ [U,\varphi,v]:(U,\varphi) \text{ chart at }p, v\in \mathbb{R}^m \}_{/\sim}$$where $[U,\varphi ,v]\sim[W,\psi,v']\iff d_{\varphi(p)}(\psi \circ\varphi ^{-1})v=v'$. Denote the equivalence class with $[U,\varphi,v]_{p}$. 


- **Remark**: If $\gamma:(-1,1)\to M$ smooth with $\gamma(0)=p$. Then, $\gamma'(0):=\left[ x, \left. \frac{d}{dt}x(\gamma(t)) \right|_{t=0} \right]_{p}\in T_{p}M$.
- **Related definition**: For a [[smooth function]] $f:M\to \mathbb{R}$ and $[x,v]_{p}\in T_{p}M$, the ***directional derivative***  is given as:$$[x,v]_{p}f:= \left. \frac{d}{dt}(f\circ x ^{-1})(x(p)+tv) \right|_{t=0} $$This is analogous to defining $\gamma:(-1,1)\to \mathbb{R}^m,t\mapsto x(p)+tv$. 
- **Related definition**: Let $\left. \frac{ \partial  }{ \partial x^i } \right|_{p}:=[x,e_{i}]_{p}\in T_{p}M$. Then, for every $[x,v]_{p}\in T_{p}M$, $$[x,v]_{p}=\sum_{i=1}^{m}v^i[x,e_{i}]_{p}=\sum_{i=1}^{m}v^i\left. \frac{ \partial  }{ \partial \varphi^i } \right|_{p}$$ where $v^i\in \mathbb{R}$ are called the ***coefficients*** of $v$ in chart $x$.
- **Related definition**: $TM:=\bigsqcup_{p\in M}T_{p}M$
---
##### Properties
> [!lemma] Lemma 1
> The relation $\sim$ is an equivalence relation.

> [!proof]-
> We have:
> 1. **$\sim$ is reflexive**: For $[U,\varphi,v]$, $$d_{\varphi(p)}(\varphi \circ \varphi ^{-1})v=d_{\varphi(p)}(\text{id})v=v$$
> 2. **$\sim$ is symmetric**: Suppose $[U,\varphi,v]\sim[W,\psi,v']$. Then, $$d_{\varphi(p)}(\psi \circ \varphi ^{-1})v=v'\implies v=(d_{\varphi(p)}(\psi \circ \varphi ^{-1}))^{-1}v'$$However, by the chain rule, $I_{m}=d_{\varphi(p)}(\varphi \circ\psi ^{-1}\circ\psi \circ\varphi ^{-1})=d_{\psi(p)}(\varphi \circ\psi^{-1})d_{\varphi(p)}(\psi \circ\varphi ^{-1})$, therefore, $v=d_{\psi(p)}(\varphi \circ\psi^{-1})v'$ which shows the symmetry.
> 3. **$\sim$ is transitive**: Suppose $[U_{1},\varphi_{1},v_{1}]\sim[U_{2},\varphi_{2},v_{2}]$ and $[U_{2},\varphi_{2},v_{2}]\sim[U_{3},\varphi_{3},v_{3}]$. Then, $$\begin{align}d_{\varphi_{1}(p)}(\varphi_{3}\circ \varphi_{1}^{-1})v_{1}&=d_{\varphi_{1}(p)}(\varphi_{3}\circ\varphi_{2}^{-1}\circ \varphi_{2} \circ  \varphi_{1}^{-1})v_{1}\\&=d_{\varphi_{2}(p)}(\varphi_{3}\circ\varphi_{2}^{-1})d_{\varphi_{1}(p)}( \varphi_{2} \circ  \varphi_{1}^{-1})v_{1}\\&=v_{3}\end{align}$$
---
> [!lemma] Lemma 2
> Let $M$ be a [[smooth manifold]] and $(U,\varphi)$ a chart at $p\in M$. Then, $$\begin{array}{cccc} {}&{\mathbb{R}^m}&\to&{\text{T}_{p}M}\\&{v} &\mapsto & {[U,\varphi,v]_{p}} \end{array}{}$$is a bijection. The resulting vector space structure on $\text{T}_{p}M$ is independent of the choice of the chart $(U,\varphi)$.

> [!proof]-
> We have:
> 1. **The map is injective**: Let $v_{1},v_{2}\in \mathbb{R}^m$ and suppose $[U,\varphi,v_{1}]\sim[U,\varphi ,v_{2}]$. Then, $$v_{1}=d_{\varphi(p)}(\varphi \circ \varphi ^{-1})v_{1}=v_{2}$$
> 2. **The map is surjective**: Let $[V,\psi,w]_{p}\in \text{T}_{p}M$. Then, $$d_{\varphi(p)}(\psi \circ \varphi ^{-1})d_{\psi(p)}(\varphi \circ \psi ^{-1})w=d_{\psi(p)}(\psi \circ \psi ^{-1})w=w$$Therefore, $[U,\varphi,d_{\psi(p)}(\varphi \circ \psi ^{-1})w]_{p}=[V,\psi,w]_{p}$.
> 3. **The vector space structure is independent**: Let $v_{1},v_{2}\in \text{T}_{p}M$, where 
> 	- $v_{1}$ is represented by $(U,\varphi,u_{1}),(W,\psi,w_{1})$ 
> 	- $v_{2}$ is represented by $(U,\varphi,u_{2}),(W,\psi,w_{2})$ 
> 	
> 	We need to show that $(U,\varphi,u_{1}+u_{2})\sim(W,\psi,w_{1}+w_{2})$. Indeed, $$d_{\varphi(p)}(\psi \circ \varphi ^{-1})(u_{1}+u_{2})=w_{1}+w_{2}$$and for $\lambda\in \mathbb{R}$, $$d_{\varphi(p)}(\psi \circ \varphi ^{-1})(\lambda u_{1})=\lambda w_{1}$$
---
##### Examples
> [!h] Example 1
> Let $U\subseteq \mathbb{R}^m$ be an open subset. Then, with the atlas $\{ (U,\text{id}) \}$, $\text{T}_{p}U=\mathbb{R}^m$ for any $p\in U$.
---
