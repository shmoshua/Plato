#Definition #MeasureTheory 

> [!definition]
> Let $X$ and $Y$ be compact [[Hausdorff Space|Hausdorff spaces]]. Then, for a continuous function $$\psi:X\to Y$$and a measure $\mu\in M(X)$, the ***pushforward measure*** is defined as: $$\psi_{*}(\mu)(E)=\mu(\psi ^{-1}(E))$$for any Borel $E\subseteq Y$. 
---
##### Properties
> [!lemma] Lemma 1
> If $Y=X$ and $\psi\in \text{Homeo}(X)$ is a [[homeomorphism|homeomorphism]], then for $$\begin{array}{cccc} {\lambda(\psi):}&{C(X)}&\to&{C(X)}\\&{f} &\mapsto & {f\circ \psi ^{-1}} \end{array}{}$$it holds that: 
> 1. $\lambda(\psi)$ is a bijective isometry on $(C(X),\|\cdot\|_{b})$.
> 2. $\lambda(\psi)^{*}$ is a bijective isometry on $C(X)^{*}$.
> 3. $\lambda(\psi)^{*}$ is weak\*-continuous in $C(X)^{*}$ 

> [!proof]-
> We have: 
> 1. Firstly, $$\left\| \lambda(\psi)f \right\|_{b}=\sup_{x\in X}\left| (\lambda(\psi)f)(x) \right|=\sup_{x\in X}\left| (f\circ\psi ^{-1})(x) \right|=\sup_{x\in X}\left| f(x) \right|=\left\| f \right\|_{b}$$
> 	Further, $$\lambda(\psi_{1}\circ \psi_{2})(f)=f\circ (\psi_{2}^{-1}\circ \psi_{1}^{-1})=\lambda(\psi_{1})(f\circ \psi_{2}^{-1})=(\lambda(\psi_{1})\circ \lambda(\psi_{2}))(f)$$Therefore, $\lambda(\psi_{1}\circ\psi_{2})=\lambda(\psi_{1})\circ\lambda(\psi_{2})$ and in particular, $\lambda(\psi)$ is a bijection with: $$\lambda(\psi)\circ \lambda(\psi ^{-1})=\lambda(\psi \circ \psi ^{-1})=\lambda(\text{id}_{X})=\text{id}_{C(X)}$$$$\lambda(\psi ^{-1})\circ \lambda(\psi)=\lambda(\psi ^{-1}\circ \psi)=\lambda(\text{id}_{X})=\text{id}_{C(X)}$$ 
> 2. Let $\lambda(\psi)^{*}:C(X)^{*}\to C(X)^{*}$ be the adjoint. Then, $$\|\lambda(\psi)^{*}g\|=\sup_{f\in C(X),\|f\|_{b}\leq 1}\left| (\lambda(\psi)^{*}g)(f) \right| =\sup_{f\in C(X),\|f\|_{b}\leq 1}\left| (g\circ \lambda(\psi))(f) \right|=\sup_{f\in C(X),\|f\|_{b}\leq 1}\left| g(f) \right| =\left\| g \right\| $$as $\lambda(\psi)$ is a bijective isometry. Therefore, $\lambda(\psi)^{*}$ is a bijection with: $$\lambda(\psi_{1} \circ \psi_{2})^{*}(g)=g\circ \lambda(\psi_{1}\circ \psi_{2})=g\circ \lambda(\psi_{1})\circ \lambda(\psi_{2})=\lambda(\psi_{2})^{*}(g\circ \lambda(\psi_{1}))=\lambda(\psi_{2})^{*}(\lambda(\psi_{1})^{*}(g))$$and: $$\lambda(\psi)^{*}\circ \lambda(\psi ^{-1})^{*}=\lambda(\psi^{-1}\circ \psi)^{*}=\text{id}_{C(X)}^{*}=\text{id}_{C(X)^{*}}$$$$\lambda(\psi ^{-1})^{*}\circ \lambda(\psi )^{*}=\lambda(\psi\circ \psi ^{-1})^{*}=\text{id}_{C(X)}^{*}=\text{id}_{C(X)^{*}}$$
> 3. From [[Weak Topology|Proposition 3.2]], $\lambda(\psi)^{*}:C(X)^{*}\to C(X)^{*}$ is weak\*-continuous.
---
> [!lemma] Proposition 2
> If $Y=X$, $\psi\in \text{Homeo}(X)$ and $$\begin{array}{cccc} {R:}&{M(X)}&\to&{C(X)^{*}}\\&{\mu} &\mapsto & {\Phi_{\mu}} \end{array}{}$$the [[Analysis/Complex Measure|Riesz representation]]. Let further $\lambda(\psi)$ defined as above. Then, for $\mu\in M(X)$, 
> $$\lambda ^{*}(\psi)(\Phi_{\mu}):=\lambda(\psi ^{-1})^{*}(\Phi_{\mu})=\Phi_{\psi_{*}(\mu)}$$ and$$\lambda ^{*}(\psi )[R[M^1(X)]]=R[M^1(X)]$$where $M^1(X)$ is the [[space of probability measures]].
> 
> This defines a group homomorphism: $$\begin{array}{cccc} {\lambda ^{*}:}&{\text{Homeo}(X)}&\to&{\text{Aut}(M(X))}\\&{\psi} &\mapsto & {\lambda(\psi ^{-1})^{*}} \end{array}{}$$with $\lambda ^{*}(\psi)(\mu)=\psi_{*}(\mu)$

> [!proof]-
> We define: $\lambda ^{*}(\psi)=[\lambda(\psi)^{*}]^{-1}=\lambda(\psi ^{-1})^{*}$. Then, $$\lambda ^{*}(\psi_{1}\circ \psi_{2})=[\lambda(\psi_{1}\circ \psi_{2})^{*}]^{-1}=[\lambda(\psi_{2})^{*}\circ \lambda(\psi_{1})^{*}]^{-1}=\lambda ^{*}(\psi_{1})\circ \lambda ^{*}(\psi_{2})$$
> 
> Let's compute $\nu\in M(X)$ for which: $$\lambda ^{*}(\psi)(\Phi_{\mu})=\Phi_{\nu}$$We have for $f\in C(X)$: $$\lambda ^{*}(\psi)(\Phi_{\mu})(f)=[\Phi_{\mu}\circ \lambda(\psi ^{-1})](f)=\Phi_{\mu}(\lambda(\psi ^{-1})(f))=\Phi_{\mu}(f\circ \psi)=\int_{X}^{} f\circ \psi \, d\mu $$
> 
> Therefore, for every Borel set $E\subseteq X$, by letting $f=\chi_{E}$, $$\mu(\psi ^{-1}[E])=\int_{X}^{} \chi_{\psi ^{-1}[E]}\, d\mu=\int_{X}^{} (\chi_{E}\circ \psi) \, d\mu=\int_{X}^{} \chi_{E}\, d\nu=\nu(E)  $$By setting $\psi_{*}(\mu)(E):=\nu(E)=\mu(\psi ^{-1}[E])$, we have: $$\lambda ^{*}(\psi)(\Phi_{\mu})=\Phi_{\psi_{*}(\mu)}$$Finally, we observe that: $$\lambda^{*}(\psi)[R[M^1(X)]]=R[M^1(X)]$$
---
