#Definition #LieGroups 

> [!definition]
> Let $M$ be a [[smooth manifold]] and $X\in \Gamma(\text{T}M)$ that is [[Integral Curve|complete]]. The ***flow*** of $X$ on $M$ is a smooth function: $$\begin{array}{cccc} {\Phi_{X}:}&{\mathbb{R}\times M}&\to&{M}\\&{(t,p)} &\mapsto & {\gamma_{p}(t)} \end{array}{}$$where $\gamma_{p}$ is the maximal integral curve given by [[Integral Curve|Theorem 1]].
- **Remark**: For given $t\in \mathbb{R}$, $p\mapsto \Phi_{X}(t,p)$ defines a [[diffeomorphism]]. Therefore, with Proposition 1, $\Phi_{X}$ is also called a 1-parameter group of $\text{Diffeo}(M)$. 
---
##### Properties
> [!lemma] Proposition 1
> For any $t_{1},t_{2}\in \mathbb{R}$ and $p\in M$, $$\Phi_{X}(t_{1}+t_{2},p)=\Phi_{X}(t_{1},\Phi_{X}(t_{2},p))$$

> [!proof]-
> The map $\chi:t\mapsto \gamma_{p}(t_{2}+t)$ is an integral curve on $X$. To check we have that: $$\chi'(t)=\gamma'_{p}(t_{2}+t)=X_{\gamma_{p}(t_{2}+t)}=X_{\chi(t)}$$Then, $\chi(0)=\gamma_{p}(t_{2})$ and by the [[Integral Curve|uniqueness of solution of ODE]], $$\gamma_{p}(t_{2}+t)=\gamma_{\gamma_{p}(t_{2})}(t)$$Therefore, $$\Phi_{X}(t+t_{2},p)=\Phi_{X}(t,\Phi_{X}(t_{2},p))$$
---
> [!lemma] Proposition 2
> Let $M$ be a smooth manifold and $X,Y\in \Gamma(\text{T}M)$ be complete vector fields. Then, for any $t_{0}\in \mathbb{R}$ and $p\in M$: $$\left. \frac{d}{dt} \right| _{t_{0}}d\Phi^{-t}_{X}(Y_{\Phi^t_{X}(p)})=d\Phi^{-t_{0}}_{X}((L_{X}Y)_{\Phi^{t_{0}}_{X}(p)})$$where $L_{X}Y$ is the [[Lie derivative]].

> [!proof]+
> For $p\in M$, consider the function $H(t):=d\Phi^{-t}_{X}(Y_{\Phi^t_{X}(p)})$
---
> [!lemma] Proposition 3
> Let $X,Y\in \Gamma(\text{T}M)$ be two complete smooth vector fields. Then, the following are equivalent:
> 1. $[X,Y]=0$.
> 2. $X$ is invariant under the flow of $Y$.
> 3. $Y$ is invariant under the flow of $X$.

> [!proof]+
> We have: 
> - (2=>1): Assume $X$ is invariant under the flow of $Y$. Then, $Y_{\Phi^t_{X}(p)}=d_{p}\Phi^t_{X}(Y_{p})$ for any $t,p$. Therefore, by applying $d_{\Phi^t_{X}(p)}\Phi^{-t}_{X}$ on both sides, $$d_{\Phi^t_{X}(p)}\Phi^{-t}_{X}(Y_{\Phi^t_{X}(p)})=Y_{p}$$Hence, $[X,Y]=L_{X}Y=\left. \frac{d}{dt} \right| _{t=0}Y_{p}=0$.
> - 
