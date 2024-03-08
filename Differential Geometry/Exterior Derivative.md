#Definition #DifferentialGeometry 

> [!definition]
> Let $U\subseteq \mathbb{R}^m$ be open and $\omega\in \Omega^k(U)$.  The ***exterior derivative*** is the following operator: $$\begin{array}{cccc} {d:}&{\Omega^k(U)}&\to&{\Omega^{k+1}(U)}\\&{\omega} &\mapsto & {d\omega:=\sum_{I}^{}da_{I}\land dx_{I}} \end{array}{}$$where $\omega=\sum_{I}a_{I}dx_{I}$. For [[Smooth Manifold|smooth manifolds]] $M$ and $\omega\in \Omega^k(M)$, $$\begin{array}{cccc} {d:}&{\Omega^k(M)}&\to&{\Omega^{k+1}(M)}\\&{\omega} &\mapsto & {d\omega} \end{array}{}$$s.t. for any chart $(U,\varphi)$, if $\omega|_{U}=\sum_{I}^{}a_{I}dx_{I}$, then $d\omega|_{U}=\sum_{I}^{}da_{I}\land dx_{I}$.
---
##### Properties
> [!lemma] Proposition 1
> For the exterior derivative $d$, we have that: 
> 1. $d$ is $\mathbb{R}$-linear.
> 2. For $\omega_{1}\in \Omega^p(U),\omega_{2}\in \Omega^q(U)$, we have: $$d(\omega_{1}\land\omega_{2})=d\omega_{1}\land\omega_{2}+(-1)^{p}\omega_{1}\land d\omega_{2}$$
> 3. $d^{2}=0$
> 4. For $F:V\to U$ is smooth for another open $V\subseteq \mathbb{R}^n$, $d\circ F^{*}=F^{*}\circ d$.

> [!proof]-
> We have: 
> 1. for $\omega_{1},\omega_{2}\in \Omega^k(U)$ and $\lambda\in \mathbb{R}$, $\lambda\omega_{1}+\omega_{2}=\sum_{I}^{}(\lambda a_{I}+b_{I})dx_{I}$ where $\omega_{1}=\sum_{I}^{}a_{I}dx_{I}$ and $\omega_{2}=\sum_{I}^{}b_{I}dx_{I}$, we have: $$\begin{align}d(\lambda\omega_{1}+\omega_{2})&=\sum_{I}^{}d(\lambda a_{I}+b_{I})\land dx_{I}\\&=\sum_{I}^{}(\lambda da_{I}+db_{I})\land dx_{I}\\&=\lambda \sum_{I}da_{I}\land dx_{I}+\sum_{I}db_{I}\land dx_{I}\\&=\lambda d\omega_{1}+d\omega_{2}\end{align}$$
> 2. Let $\omega_{1}=\sum_{I}^{}a_{I}dx_{I}$ and $\omega_{2}=\sum_{J}^{}b_{J}dx_{J}$. Then, we have: $$\omega_{1}\land\omega_{2}=\sum_{I,J}^{}a_{I}b_{J}dx_{I}\land dx_{J}=\sum_{I\cap J=\varnothing}^{}a_{I}b_{J}(\pm 1)dx_{Q}$$where $Q$ is the multi-index of $I\cup J$. Then, $$\begin{align}d(\omega_{1}\land\omega_{2})&=\sum_{I,J}^{}\sum_{i=1}^{m}\frac{ \partial a_{I}b_{J} }{ \partial x_{i} }dx_{i}\land dx_{I}\land dx_{J}\\&=\sum_{I,J}^{}\sum_{i=1}^{m}\left(\frac{ \partial a_{I} }{ \partial x_{i} }b_{J}+a_{I}\frac{ \partial b_{J} }{ \partial x_{i} } \right)dx_{i}\land dx_{I}\land dx_{J} \\&=\sum_{I,J}^{}\sum_{i=1}^{m}\frac{ \partial a_{I} }{ \partial x_{i} }b_{J} dx_{i}\land dx_{I}\land dx_{J} +\sum_{I,J}^{}\sum_{i=1}^{m}a_{I}\frac{ \partial b_{J} }{ \partial x_{i} } dx_{i}\land dx_{I}\land dx_{J} \\&=\sum_{I,J}^{}\left( \sum_{i=1}^{m}\frac{ \partial a_{I} }{ \partial x_{i} } \right)b_{J} dx_{i}\land dx_{I}\land dx_{J} +(-1)^p\sum_{I,J}^{}a_{I}\left( \sum_{i=1}^{m}\frac{ \partial b_{J} }{ \partial x_{i} }  \right)dx_{I}\land dx_{i}\land dx_{J} \\&=d\omega_{1}\land\omega_{2} +(-1)^p\omega_{1}\land d\omega_{2}\end{align}$$
> 3. Firstly assume that $f\in \Omega^0(U)=C^\infty(U)$. Then, $$\begin{align}d(df)&=\sum_{i=1}^{m}d\left( \frac{ \partial f }{ \partial x_{i} }  \right) \land dx_{i}\\&=\sum_{i=1}^{m}\sum_{j=1}^{m}\frac{ \partial^{2}f }{ \partial x_{j}\partial x_{i} } dx_{j}\land dx_{i}\\&=\sum_{i\neq j}^{} \frac{ \partial^{2}f }{ \partial x_{j}\partial x_{i} } dx_{j}\land dx_{i}\\&=\sum_{i<j}^{}\frac{ \partial^{2}f }{ \partial x_{j}\partial x_{i} } dx_{j}\land dx_{i}+\sum_{i>j}^{}\frac{ \partial^{2}f }{ \partial x_{j}\partial x_{i} } dx_{j}\land dx_{i}\\&=\sum_{i<j}^{}\frac{ \partial^{2}f }{ \partial x_{j}\partial x_{i} } dx_{j}\land dx_{i}-\sum_{i>j}^{}\frac{ \partial^{2}f }{ \partial x_{i}\partial x_{j} } dx_{i}\land dx_{j}\\&=\sum_{i<j}^{}\frac{ \partial^{2}f }{ \partial x_{j}\partial x_{i} } dx_{j}\land dx_{i}-\sum_{i<j}^{}\frac{ \partial^{2}f }{ \partial x_{j}\partial x_{i} } dx_{j}\land dx_{i}\\&=0\end{align}$$Now for $\omega\in \Omega^k(U)$ s.t. $\omega=\sum_{I}^{}a_{I}dx_{I}$, $$d(d\omega)=d\left( \sum_{I}da_{I}\land dx_{I} \right)=\sum_{I}^{}d(da_{I}\land dx_{I})=\sum_{I}^{}(\underbrace{ d(da_{I}) }_{ =0 }\land dx_{I}-da_{I}\land \underbrace{ d(dx_{I})) }_{ =0 }=0 $$by recurrence.
> 4. First consider $g\in \Omega^0(U)$. Then, $$F^{*}(dg)=F^{*}\left( \sum_{i=1}^{m}\frac{ \partial g }{ \partial x_{i} }dx_{i}  \right)=\sum_{i=1}^{m}F^{*}\left( \frac{ \partial g }{ \partial x_{i} }dx_{i}  \right) =\sum_{i=1}^{m}\left( \frac{ \partial g }{ \partial x_{i} }\circ F  \right)  F^{*}(dx_{i})$$If $F=(F_{1},\dots,F_{m})$, then $F^{*}(dx_{i})=\sum_{j=1}^{n}\frac{ \partial F_{i} }{ \partial y_{j} }dy_{j}$. Therefore, $$F^{*}(dg)=\sum_{i=1}^{m}\left( \frac{ \partial g }{ \partial x _{i}} \circ F \right) \sum_{j=1}^{n}\frac{ \partial F_{i} }{ \partial y_{j} } dy_{j}=\sum_{j=1}^{m}\left( \sum_{i=1}^{m}\left( \frac{ \partial g }{ \partial x_{i} }\circ F  \right) \frac{ \partial F_{i} }{ \partial y_{j} }  \right)dy_{j}=\sum_{j=1}^{m}\frac{ \partial (g\circ F) }{ \partial y_{j} } dy_{j} $$From which it holds that $F^{*}(dg)=d(g\circ F)=d(F^{*}g)$.
>    
>    Now, if $\omega\in \Omega^k(U)$ with $\omega=\sum_{I}^{}a_{I}dx_{I}$, $$\begin{align}d(F^{*}\omega)&=\sum_{I}^{}d(F^{*}a_{I}\land F^{*}(dx_{I}))\\&=\sum_{I}^{}d(F^{*}a_{I})\land F^{*}(dx_{I})+\sum_{I}^{}F^{*}a_{I}\land d(F^{*}(dx_{I}))\\&=\sum_{I}^{}F^{*}(da_{I})\land F^{*}(dx_{I})+\sum_{I}^{}F^{*}a_{I}\land \underbrace{ d(F^{*}(dx_{I})) }_{ =0 }\\&=F^{*}(d\omega)\end{align}$$where $d(F^{*}(dx_{I})) =0$ by recurrence and 3. 
---
> [!lemma] Proposition 2
> For a [[smooth manifold]] $M$, the exterior derivative $d:\Omega^k(M)\to\Omega^{k+1}(M)$ is well-defined.

> [!proof]-
> Let $\omega\in \Omega^k(M)$. Then, for chart $(U,\varphi)$, we have: 
> $$d_{p}a_{I}=d_{\varphi(p)}(a_{I}\circ \varphi ^{-1})d_{p}\varphi=\varphi ^{*}(d(a_{I}\circ \varphi ^{-1}))_{p}$$Therefore,
> 
> $$\begin{align}d\omega|_{U}&=\sum_{I}^{}da_{I}\land dx_{I}\\&=\sum_{I}^{}\varphi ^{*}(d(a_{I}\circ \varphi ^{-1}))\land\varphi ^{*}(d\pi_{I})\\&=\varphi ^{*}\left( \sum_{I}^{}d(a_{I}\circ \varphi ^{-1})\land d\pi_{I} \right)\\&=\varphi ^{*}\left( d\left( \sum_{I}^{}(a_{I}\circ \varphi ^{-1})d\pi_{I} \right)  \right) \\&= \varphi ^{*}(d((\varphi ^{-1})^{*}\omega))\end{align}$$
> Now, let $(U_{\alpha},\varphi_{\alpha}),(U_{\beta},\varphi_{\beta})$ be two charts on $M$. Then, for $\omega_{\alpha}:=(\varphi_{\alpha}^{-1})^{*}\omega$, $$\begin{align}\varphi_{\alpha} ^{*}(d\omega_{\alpha})&=(\theta_{\alpha\beta}\varphi_{\beta})^{*}(d\omega_{\alpha})\\&=\varphi_{\beta}^{*}\theta_{\alpha\beta}^{*}(d\omega_{\alpha})\\&=\varphi_{\beta}^{*}d(\theta ^{*}_{\alpha\beta}(\varphi_{\alpha}^{-1})^{*}\omega)\\&=\varphi_{\beta}^{*}d((\varphi_{\beta}^{-1})^{*}\omega)\\&\end{align}$$
---
> [!lemma] Theorem 3
> Let $M,N$ be [[smooth manifold|smooth manifolds]]. Then: 
> 1. $d:\Omega^0(M)\to\Omega^1(M)$ coincides with [[Differential|differentials]].
> 2. For $\omega_{1}\in \Omega^p(M),\omega_{2}\in \Omega^q(M)$, we have: $$d(\omega_{1}\land\omega_{2})=d\omega_{1}\land\omega_{2}+(-1)^{p}\omega_{1}\land d\omega_{2}$$
> 3. $d^{2}=0$
> 4. For a [[Smooth Function|smooth map]] $F:N\to M$, $d( F^{*}\omega)=F^{*}(d\omega)$ for all $\omega\in \Omega^k(M)$.
---
##### Examples
> [!h] Example 1
> Consider $U\subseteq \mathbb{R}^{2}$ and a [[Differential 1-Form|1-form]] $\omega:=Pdx+Qdy$ where $P,Q:U\to \mathbb{R}$ are smooth functions. Then, $$\begin{align}d\omega&=dP\land dx+dQ\land dy\\&=\left( \frac{ \partial P }{ \partial x } dx+\frac{ \partial P }{ \partial y } dy \right)\land dx+\left( \frac{ \partial Q }{ \partial x } dx+\frac{ \partial Q }{ \partial y } dy \right)\land dy\\&= \cancel{ \frac{ \partial P }{ \partial x } dx\land dx }+\frac{ \partial P }{ \partial y } dy \land dx+\frac{ \partial Q }{ \partial x } dx\land dy+\cancel{ \frac{ \partial Q }{ \partial y } dy \land dy }\\&=\left( \frac{ \partial Q }{ \partial x } -\frac{ \partial P }{ \partial y }  \right) dx\land dy\end{align}$$where we recover the Green's theorem.
---
> [!h] Example 2
> Consider $U\subseteq \mathbb{R}^{3}$ and a [[Differential k-Form|2-form]] $$\omega:=F_{1} dy\land dz-F_{2}dx\land dz+F_{3}dx\land dy$$ where $F_{i}:U\to \mathbb{R}$ are smooth functions. Then, $$\begin{align}d\omega&=dF_{1}\land dy\land dz-dF_{2}\land dx\land dz+dF_{3}\land dx\land dy\\&=\frac{ \partial F_{1} }{ \partial x } dx\land dy\land dz+\frac{ \partial F_{2} }{ \partial y } dx\land dy\land dz+\frac{ \partial F_{3} }{ \partial z } dx\land dy\land dz\\&=\left( \frac{ \partial F_{1} }{ \partial x } +\frac{ \partial F_{2} }{ \partial y } +\frac{ \partial F_{3} }{ \partial z }  \right) dx\land dy\land dz\end{align}$$If we have the vector field $F(x):=(F_{1}(x),F_{2}(x),F_{3}(x))$, then $d\omega=\text{div }F\ dx\land dy\land dz$.
---
