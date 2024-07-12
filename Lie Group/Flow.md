#Definition #LieGroups 

> [!definition]
> Let $M$ be a [[smooth manifold]] and $X\in \Gamma(\text{T}M)$. The ***flow*** of $X$ on $M$ is a smooth function: $$\begin{array}{cccc} {\Phi_{X}:}&{U\times M}&\to&{M}\\&{(t,p)} &\mapsto & {\gamma_{p}(t)} \end{array}{}$$where $U\subseteq \mathbb{R}$ open and  $\gamma_{p}$ is the maximal integral curve given by [[Integral Curve|Theorem 1]].
- **Remark**: For given $t\in \mathbb{R}$, $p\mapsto \Phi_{X}(t,p)$ defines a [[diffeomorphism]]. Therefore, with Proposition 1, $\Phi_{X}$ is also called a [[One-Parameter Subgroup|one-parameter subgroup]] of $\text{Diffeo}(M)$. 
---
##### Properties
> [!lemma] Proposition 1
> For any $t_{1},t_{2}\in \mathbb{R}$ and $p\in M$, $$\Phi_{X}(t_{1}+t_{2},p)=\Phi_{X}(t_{1},\Phi_{X}(t_{2},p))$$

> [!proof]-
> The map $\chi:t\mapsto \gamma_{p}(t_{2}+t)$ is an integral curve on $X$. To check we have that: $$\chi'(t)=\gamma'_{p}(t_{2}+t)=X_{\gamma_{p}(t_{2}+t)}=X_{\chi(t)}$$Then, $\chi(0)=\gamma_{p}(t_{2})$ and by the [[Integral Curve|uniqueness of solution of ODE]], $$\gamma_{p}(t_{2}+t)=\gamma_{\gamma_{p}(t_{2})}(t)$$Therefore, $$\Phi_{X}(t+t_{2},p)=\Phi_{X}(t,\Phi_{X}(t_{2},p))$$
---
> [!lemma] Proposition 2
> Let $M$ be a smooth manifold and $X,Y\in \Gamma(\text{T}M)$ be complete vector fields. Then, for any $t_{0}\in \mathbb{R}$ and $p\in M$: $$\left. \frac{d}{dt} \right| _{t_{0}}d\Phi^{-t}_{X}(Y_{\Phi^t_{X}(p)})=d\Phi^{-t_{0}}_{X}((L_{X}Y)_{\Phi^{t_{0}}_{X}(p)})$$where $L_{X}Y$ is the [[Lie derivative]].

> [!proof]-
> For $p\in M$, consider the function $H(t):=d\Phi^{-t}_{X}(Y_{\Phi^t_{X}(p)})$. Then, $H$ is a smooth curve in $\text{T}_{p}M$. Therefore, by writing $t=t_{0}+s$, $$H'(t_{0})=\left. \frac{d}{ds} \right| _{s=0}H(t_{0}+s)=\left. \frac{d}{ds} \right| _{s=0}d\Phi^{-t_{0}-s}_{X}(Y_{\Phi^{t_{0}+s}_{X}(p)})=d\Phi_{X}^{-t_{0}}\left( \left. \frac{d}{ds} \right| _{s=0}d\Phi_{X}^{-s}(Y_{\Phi^{t_{0}+s}_{X}(p)}) \right) $$This proves the statement.
---
> [!lemma] Proposition 3
> Let $X,Y\in \Gamma(\text{T}M)$ be two complete smooth vector fields. Then, the following are equivalent:
> 1. $[X,Y]=0$.
> 3. $Y$ is invariant under the flow of $X$.
> 4. $X$ is invariant under the flow of $Y$.
> 5. $\Phi_{X}^t$ and $\Phi_{Y}^s$ commute for all $t,s\in \mathbb{R}$.

> [!proof]-
> We have: 
> - (2=>1): Assume $X$ is invariant under the flow of $Y$. Then, $Y_{\Phi^t_{X}(p)}=d_{p}\Phi^t_{X}(Y_{p})$ for any $t,p$. Therefore, by applying $d_{\Phi^t_{X}(p)}\Phi^{-t}_{X}$ on both sides, $$d_{\Phi^t_{X}(p)}\Phi^{-t}_{X}(Y_{\Phi^t_{X}(p)})=Y_{p}$$Hence, $[X,Y]=L_{X}Y=\left. \frac{d}{dt} \right| _{t=0}Y_{p}=0$.
> - (1=>2): Assume $[X,Y]=0$. Then, consider $H(t):=d\Phi^{-t}_{X}(Y_{\Phi^t_{X}(p)})$. Then, by Proposition 2, $$H'(t_{0})=0,\quad \forall t_{0}\in \mathbb{R}$$However, as $H(0)=Y_{p}$, $X(t)=Y_{p}$ for all $t\in \mathbb{R}$. By applying $d\Phi^{t}_{X}$ on both sides, we get our statement.
> - (3=>1) and (1=>3) hold by symmetry.
> - (1=>4): Assume that $[X,Y]=0$. From 3, $X_{\Phi^t_{Y}(p)}=d_{p}\Phi^t_{Y}(X_{p})$ for any $t,p$. Consider the curve $\gamma:\mathbb{R}\to M$ defined as $\gamma(t)=\Phi_{Y}^s(\Phi_{X}^t(p))$. Then, $\gamma(0)=\Phi_{Y}^s(p)$ and: $$\gamma'(t)= \frac{d}{dt} \Phi_{Y}^s(\Phi_{X}^t(p))=d\Phi^s_{Y}(X_{\Phi_{X}^t(p)})=X_{\Phi^s_{Y}(\Phi^t_{X}(p))}=X_{\gamma(t)}$$
>   Therefore, by the uniqueness of integral curves, $\gamma=\gamma_{\Phi^s_{Y}(p)}$. Hence,$$\Phi_{X}^t(\Phi_{Y}^s(p))=\gamma_{\Phi^s_{Y}(p)}(t)=\gamma(t)=\Phi^s_{Y}(\Phi^t_{X}(p))$$
> - (4=>1): Conversely assume that the flows commute. Therefore, $$d\Phi_{X}^t(Y_{p})=\left. \frac{d}{ds} \right| _{s=0}\Phi^t_{X}(\Phi^s_{Y}(p))=\left. \frac{d}{ds} \right| _{s=0}\Phi^s_{Y}(\Phi^t_{X}(p))=Y_{\Phi^t_{X}(p)}$$Therefore, $Y$ is invariant under the flow of $X$ and 1 holds.
- **Corollary**: Any smooth vector field $X$ is invariant under its own flow. 