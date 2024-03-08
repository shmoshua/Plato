#Definition #DifferentialGeometry 

> [!definition]
> Let $U\subseteq \mathbb{R}^m$ be open and $\omega\in \Omega^k(U)$.  The ***exterior derivative*** is the following operator: $$\begin{array}{cccc} {d:}&{\Omega^k(U)}&\to&{\Omega^{k+1}(U)}\\&{\omega} &\mapsto & {d\omega:=\sum_{I}^{}da_{I}\land dx_{I}} \end{array}{}$$where $\omega=\sum_{I}a_{I}dx_{I}$.
---
##### Properties
---
##### Examples
> [!h] Example 1
> Consider $U\subseteq \mathbb{R}^{2}$ and a [[Differential 1-Form|1-form]] $\omega:=Pdx+Qdy$ where $P,Q:U\to \mathbb{R}$ are smooth functions. Then, $$\begin{align}d\omega&=dP\land dx+dQ\land dy\\&=\left( \frac{ \partial P }{ \partial x } dx+\frac{ \partial P }{ \partial y } dy \right)\land dx+\left( \frac{ \partial Q }{ \partial x } dx+\frac{ \partial Q }{ \partial y } dy \right)\land dy\\&= \frac{ \partial P }{ \partial x } dx\land dx+\frac{ \partial P }{ \partial y } dy \land dx+\left( \frac{ \partial Q }{ \partial x } dx+\frac{ \partial Q }{ \partial y } dy \right)\land dy\end{align}$$