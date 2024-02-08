#Definition #FunctionalAnalysis 

> [!definition]
> A ***signed measure*** on a measure space $(X,\Sigma)$ is a function $\nu:\Sigma\to \overline{\mathbb{R}}$ that:
> 1. $\nu(\varnothing)=0$.
> 2. $\nu$ is [[Additive Functions|additive]].
> 3. either $\nu[\Sigma]\subseteq(-\infty,+\infty]$ or $\nu[\Sigma]\subseteq[-\infty,+\infty)$.
- **Related definition**: a signed measure $\nu$ is called:
	- **finite**, if $\left| \nu(X) \right|<+\infty$.
	- **$\sigma$-finite**, if there exists $(X_{n})\subseteq\Sigma$ s.t. $X=\bigcup_{n=1}^{\infty}X_{n}$ and $\left| \nu(X_{n}) \right|<+\infty$.
- **Remark**: For two non-negative measures $\mu^+$ and $\mu^-$ s.t. at least one of them is finite, then $\mu:=\mu^+ -\mu^-$ is a signed measure. $\mu$ is finite if both are finite.
---