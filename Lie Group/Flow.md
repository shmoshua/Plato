#Definition #LieGroups 

> [!definition]
> Let $M$ be a [[smooth manifold]] and $X\in \Gamma(\text{T}M)$. The ***flow*** of $X$ on $M$ is a smooth function: $$\begin{array}{cccc} {\Phi_{X}:}&{U\times M}&\to&{M}\\&{(t,p)} &\mapsto & {\gamma_{p}(t)} \end{array}{}$$where $U\subseteq \mathbb{R}$ open and  $\gamma_{p}$ is the maximal integral curve given by [[Integral Curve|Theorem 1]].
- **Related notation**: We denote $\Phi_{X}^t:M\to M,p\mapsto \Phi_{X}(t,p)=\gamma_{p}(t)$. 
- **Remark**: By Theorem 1, $\Phi_{X}$ is also called a [[One-Parameter Subgroup|one-parameter subgroup]] of $\text{Diff}(M)$. 
---
##### Properties
> [!lemma] Theorem 1
> For any $t_{1},t_{2}\in \mathbb{R}$ and $p\in M$, if $X$ is complete, then:
> 1. $\Phi_{X}^{t_{1}}\circ\Phi_{X}^{t_{2}}=\Phi_{X}^{t_{1}+t_{2}}$, i.e. $\Phi_{X}(t_{1}+t_{2},p)=\Phi_{X}(t_{1},\Phi_{X}(t_{2},p))$
> 2. $\Phi_{X}^t$ is bijective with $(\Phi_{X}^t)^{-1}=\Phi_{X}^{-t}$.
> 3. $\Phi_{X}^t$ is a [[diffeomorphism]] for all $t\in \mathbb{R}$.
> 4. $\left. \frac{d}{dt} \right|_{t=s}\Phi^t_{X}(p)=X_{\Phi^s_{X}(p)}$

> [!proof]-
> We have:
> 1. The map $\chi:t\mapsto \gamma_{p}(t_{2}+t)$ is an integral curve on $X$. To check we have that: $$\dot{\chi}(t)=\dot{\gamma}_{p}(t+t_{2})=X_{\gamma_{p}(t_{2}+t)}=X_{\chi(t)}$$
> 
> 	Then, $\chi(0)=\gamma_{p}(t_{2})$ and by the [[Integral Curve|uniqueness of solution of ODE]], $$\gamma_{p}(t_{2}+t)=\gamma_{\gamma_{p}(t_{2})}(t)$$Therefore, $$\Phi_{X}(t+t_{2},p)=\gamma_{p}(t+t_{2})=\gamma_{\gamma_{p}(t_{2})}(t)=\Phi_{X}(t,\Phi_{X}(t_{2},p))$$
> 2. $\Phi_{X}^t\circ\Phi_{X}^{-t}=\Phi_{X}^0=\text{id}_{M}$ as $\gamma_{p}(0)=p$ for all $p\in M$. 
> 3. Both $\Phi^t_{X}$ and $\Phi^{-t}_{X}$ are smooth by definition.
> 4. We have:$$\left. \frac{d}{dt} \right| _{t=s}\Phi^t_{X}(p)=\left. \frac{d}{dt} \right| _{t=s}\gamma_{p}(t)=\dot{\gamma}_{p}(s)=X_{\gamma_{p}(s)}=X_{\Phi^s_{X}(p)}$$
- **Remark**: If $X$ is incomplete, then:
	1. 1 holds if $\Phi_{X}^{t_{1}}\Phi_{X}^{t_{2}}$ is defined.
	2. if $\Phi^t_{X}:U\to M$ is defined for some open $U\subseteq M$, then $\Phi_{X}^t:U\to \Phi_{X}^t$ is a diffeomorphism to an open set. 
---
> [!lemma] Proposition 2 (Flow Pullbacks)
> Let $X,Y\in \Gamma(\text{T}M)$. Then, 
> 1. $(\Phi^t_{X})^{*}(X)=X$ for all $t$.
> 2. $\left. \frac{d}{dt} \right|_{s}(\Phi^t_{X})^{*}(Y)_{p}=(\Phi^{s}_{X})^{*}(L_{X}Y)$ for all $s$.

> [!proof]-
> We have:
> 1. Assume that $X$ is complete for simplicity and fix $t\in \mathbb{R}$. Then, $$\begin{align}(\Phi^t_{X})^{*}(X)_{p}&=(d_{p}\Phi^t_{X})^{-1}(X_{\Phi^t_{X}(p)})=d_{\Phi^t_{X}(p)}\Phi^{-t}_{X}(X_{\Phi^t_{X}(p)})\\&=d\Phi^{-t}_{X}\left( \left. \frac{d}{ds} \right|_{s=t}\Phi^s_{X}(p)  \right)\\&=\left. \frac{d}{ds} \right|_{s=t}\Phi^{-t}_{X}(\Phi^s_{X}(p))\\&=\left. \frac{d}{ds} \right| _{s=t}\Phi^{-t+s}_{X}(p)\\&=\left. \frac{d}{du} \right| _{u=0}\Phi^u_{X}(p)\\&=X_{\Phi^0_{X}(p)}\\&=X_{p} \end{align}$$
> 2. We have: $$\begin{align}\left. \frac{d}{dt} \right|_{t=s}(\Phi^t_{X})^{*}(Y)_{p}&=\left. \frac{d}{dt} \right|_{t=0}(\Phi^{t+s}_{X})^{*}(Y)_{p}\\&=\left. \frac{d}{dt} \right|_{t=0}(\Phi^{s}_{X})^{*}((\Phi^t_{X})^{*}(Y)_{p})\\&=(\Phi^s_{X})^{*}\left( \left. \frac{d}{dt} \right| _{t=0}(\Phi^t_{X})^{*}(Y)_{p} \right)\\&=(\Phi^s_{X})^{*}(L_{X}Y)\end{align} $$
---
> [!lemma] Theorem 3 (Commutation Theorem)
> Let $X,Y\in \Gamma(\text{T}M)$ be two smooth vector fields. Then, the following are equivalent:
> 1. $[X,Y]=0$.
> 3. $Y$ is invariant under the flow of $X$, i.e. $(\Phi^t_{X})^{*}(Y)=Y$ for any $t$.
> 4. $X$ is invariant under the flow of $Y$, i.e. $(\Phi^t_{Y})^{*}(X)=X$ for any $t$.
> 5. $\Phi_{X}^t$ and $\Phi_{Y}^s$ commute for all $t,s\in \mathbb{R}$.

^0d5b4f

> [!proof]-
> We have: 
> - (1=>2): Assume $[X,Y]=0$. Then, by Proposition 2, $\left. \frac{d}{dt} \right|_{s}(\Phi^t_{X})^{*}(Y)_{p}=(\Phi^s_{X})^{*}(0)=0$ for all $s$. Therefore, as $(\Phi^0_{X})^{*}(Y)=Y$, $(\Phi^t_{X})^{*}(Y)=Y$ for all $t$.
> - (2=>1): Assume $Y$ is invariant under the flow of $X$. Then, $$[X,Y]=L_{X}Y=\left. \frac{d}{dt} \right| _{t=0}(\Phi^t_{X})^{*}(Y)=\left. \frac{d}{dt} \right| _{t=0}Y=0$$
> - (3=>1) and (1=>3) hold by symmetry.
> - (3=>4): Assume that $[X,Y]=0$. From 3, $X_{\Phi^t_{Y}(p)}=d_{p}\Phi^t_{Y}(X_{p})$ for any $t,p$. Consider the curve $\gamma:\mathbb{R}\to M$ defined as $\gamma(t)=\Phi_{Y}^s(\Phi_{X}^t(p))$. Then, $\gamma(0)=\Phi_{Y}^s(p)$ and: $$\dot{\gamma}(t)= \frac{d}{dt} \Phi_{Y}^s(\Phi_{X}^t(p))=d\Phi^s_{Y}(X_{\Phi_{X}^t(p)})=X_{\Phi^s_{Y}(\Phi^t_{X}(p))}=X_{\gamma(t)}$$
>   Therefore, by the uniqueness of integral curves, $\gamma=\gamma_{\Phi^s_{Y}(p)}$. Hence,$$\Phi_{X}^t(\Phi_{Y}^s(p))=\gamma_{\Phi^s_{Y}(p)}(t)=\gamma(t)=\Phi^s_{Y}(\Phi^t_{X}(p))$$
> - (4=>2): Wlog assume that $X,Y$ are complete and assume that the flows commute. Therefore, $$d\Phi_{X}^t(Y_{p})=\left. \frac{d}{ds} \right| _{s=0}\Phi^t_{X}(\Phi^s_{Y}(p))=\left. \frac{d}{ds} \right| _{s=0}\Phi^s_{Y}(\Phi^t_{X}(p))=Y_{\Phi^t_{X}(p)}$$Hence, $(\Phi^t_{X})^{*}(Y)_{p}=(d_{p}\Phi^t_{X})^{-1}(Y_{\Phi^t_{X}(p)})=Y_{p}$. 

^35997d

---
> [!lemma] Theorem 4 (Commutation Error)
> Let $X,Y\in \Gamma(\text{T}M)$. Then, for any coordinate system, 
> 1. $(\Phi^t_{Y}\circ\Phi^s_{X})(x)=x+sX_{x}+tY_{x}+O(\left| s \right|^{2}+\left| t \right|^{2})$
> 2. $(\Phi^t_{Y}\circ\Phi^s_{X})(x)-(\Phi^s_{X}\circ\Phi^t_{Y})(x)=st[X,Y]_{x}+O(\left| s \right|^3+\left| t \right|^3)$
> 3. $(\Phi^{-t}_{Y}\circ\Phi^{-s}_{X}\circ\Phi^t_{Y}\circ\Phi^s_{X})(x)=x+st[X,Y]_{x}+O(\left| s \right|^3+\left| t \right|^3)$

> [!proof]+
> For $\Psi(s,t)=\Phi^t_{Y}(\Phi^s_{Y}(x))$, we have: $d_{0}\Psi=(X_{x},Y_{x})$. Therefore, by Taylor expansion, we have: $$(\Phi^t_{Y}\circ \Phi^s_{X})(x)=x+sX_{x}+tY_{x}+O(\left| s \right| ^{2}+\left| t \right| ^{2})$$
----
###### Flows of Incomplete Vector Fields

> [!lemma] Theorem 1
> Let $X\in \Gamma(\text{T}M)$ and $U\subseteq \mathbb{R}\times M$ be the set of maximal existence, i.e. $\Phi_{X}:U\to M$ is defined and cannot be extended to a larger set. Then, 
> 1. $U:=\{ (t,x)\in \mathbb{R}\times M: a(x)<t<b(x) \}$ where $a,b:M\to[-\infty,\infty]$ with $-\infty\leq a(x)< 0< b(x)\leq+\infty$.
> 2. $U$ is open.

> [!proof]-
> 1 follows from [[Integral Curve|Theorem 1]].
---
