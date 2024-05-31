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
> Let $X,Y\in \Gamma(\text{T}M)$ be two complete smooth vector fields. Then, the following are equivalent:
> 1. $\Phi^t_{X}$ and $\Phi^s_{Y}$ commute for all $t,s\in \mathbb{R}$.
> 2. $[X,Y]=0$.