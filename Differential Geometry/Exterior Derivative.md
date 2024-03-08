#Definition #DifferentialGeometry 

> [!definition]
> Let $U\subseteq \mathbb{R}^m$ be open and $\omega\in \Omega^k(U)$.  The ***exterior derivative*** is the following operator: $$\begin{array}{cccc} {d:}&{\Omega^k(U)}&\to&{\Omega^{k+1}(U)}\\&{\omega} &\mapsto & {d\omega:=\sum_{I}^{}da_{I}\land dx_{I}} \end{array}{}$$where $\omega=\sum_{I}a_{I}dx_{I}$.
---
##### Properties
> [!lemma] Proposition 1
> For the exterior derivative $d$, we have that: 
> 1. $d$ is $\mathbb{R}$-linear.
> 2. For $\omega_{1}\in \Omega^p(U),\omega_{2}\in \Omega^q(U)$, we have: $$d(\omega_{1}\land\omega_{2})=d\omega_{1}\land\omega_{2}+(-1)^{p}\omega_{1}\land d\omega_{2}$$
> 3. $d^{2}=0$
> 4. For $F:V\to U$ is smooth for another open $V\subseteq \mathbb{R}^m$, $d\circ F^{*}=F^{*}\circ d$.

> [!proof]+
> We have: 
> 1. for $\omega_{1},\omega_{2}\in \Omega^k(U)$ and $\lambda\in \mathbb{R}$, $\lambda\omega_{1}+\omega_{2}=\sum_{I}^{}(\lambda a_{I}+b_{I})dx_{I}$ where $\omega_{1}=\sum_{I}^{}a_{I}dx_{I}$ and $\omega_{2}=\sum_{I}^{}b_{I}dx_{I}$, we have: $$\begin{align}d(\lambda\omega_{1}+\omega_{2})&=\sum_{I}^{}d(\lambda a_{I}+b_{I})\land dx_{I}\\&=\sum_{I}^{}(\lambda da_{I}+db_{I})\land dx_{I}\\&=\lambda \sum_{I}da_{I}\land dx_{I}+\sum_{I}db_{I}\land dx_{I}\\&=\lambda d\omega_{1}+d\omega_{2}\end{align}$$
> 2. Let $\omega_{1}=\sum_{I}^{}a_{I}dx_{I}$ and $\omega_{2}=\sum_{J}^{}b_{J}dx_{J}$. Then, we have: $$\omega_{1}\land\omega_{2}=\sum_{I,J}^{}a_{I}b_{J}dx_{I}\land dx_{J}=\sum_{I\cap J=\varnothing}^{}a_{I}b_{J}(\pm 1)dx_{Q}$$where $Q$ is the multi-index of $I\cup J$. Then, $$\begin{align}d(\omega_{1}\land\omega_{2})=\end{align}$$
> 3. 
> 4. $$\begin{align}d(\omega_{1}\land\omega_{2})&=\sum_{n=1}^{}\end{align}$$
---
##### Examples
> [!h] Example 1
> Consider $U\subseteq \mathbb{R}^{2}$ and a [[Differential 1-Form|1-form]] $\omega:=Pdx+Qdy$ where $P,Q:U\to \mathbb{R}$ are smooth functions. Then, $$\begin{align}d\omega&=dP\land dx+dQ\land dy\\&=\left( \frac{ \partial P }{ \partial x } dx+\frac{ \partial P }{ \partial y } dy \right)\land dx+\left( \frac{ \partial Q }{ \partial x } dx+\frac{ \partial Q }{ \partial y } dy \right)\land dy\\&= \cancel{ \frac{ \partial P }{ \partial x } dx\land dx }+\frac{ \partial P }{ \partial y } dy \land dx+\frac{ \partial Q }{ \partial x } dx\land dy+\cancel{ \frac{ \partial Q }{ \partial y } dy \land dy }\\&=\left( \frac{ \partial Q }{ \partial x } -\frac{ \partial P }{ \partial y }  \right) dx\land dy\end{align}$$where we recover the Green's theorem.
---
> [!h] Example 2
> Consider $U\subseteq \mathbb{R}^{3}$ and a [[Differential k-Form|2-form]] $$\omega:=F_{1} dy\land dz-F_{2}dx\land dz+F_{3}dx\land dy$$ where $F_{i}:U\to \mathbb{R}$ are smooth functions. Then, $$\begin{align}d\omega&=dF_{1}\land dy\land dz-dF_{2}\land dx\land dz+dF_{3}\land dx\land dy\\&=\frac{ \partial F_{1} }{ \partial x } dx\land dy\land dz+\frac{ \partial F_{2} }{ \partial y } dx\land dy\land dz+\frac{ \partial F_{3} }{ \partial z } dx\land dy\land dz\\&=\left( \frac{ \partial F_{1} }{ \partial x } +\frac{ \partial F_{2} }{ \partial y } +\frac{ \partial F_{3} }{ \partial z }  \right) dx\land dy\land dz\end{align}$$If we have the vector field $F(x):=(F_{1}(x),F_{2}(x),F_{3}(x))$, then $d\omega=\text{div }F\ dx\land dy\land dz$.
---
