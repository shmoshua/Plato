> [!definition]
> For a group $\Gamma$ with discrete topology, a ***mean*** on $\Gamma$ is a function $\mu\in \ell^\infty(\Gamma,\mathbb{R})^{*}$ s.t.
> 1. $\mu(\chi_{\Gamma})=1$
> 2. $\mu(f)\geq 0$ for all $f\geq 0,f\in\ell^\infty(\Gamma,\mathbb{R})$.
> 
> The set of means is denoted as $\mathcal{M}(\Gamma)$.
- **Remark**: For each mean $\mu\in\mathcal{M}(\Gamma)$, we can define an additive set function $\lambda_{\mu}:\mathcal{P}(\Gamma)\to[0,+\infty]$ as $\lambda_{\mu}(E)=\mu(\chi_{E})$ s.t. $\lambda_{\mu}(\Gamma)=1$.
---
##### Properties
> [!lemma] Proposition 1
> $\mathcal{M}(\Gamma)$ is a [[Convex Set|convex]], [[Weak Topology|weak*-closed]] subset of $B_{\leq 1}(0)$ and hence [[Compact sets|compact]]. 

> [!proof]-
> We have:
> 1. **$\mathcal{M}(\Gamma)$ is convex**:
>    For $\mu_{1},\mu_{2}\in \mathcal{M}(\Gamma)$ and $t\in(0,1)$:
>    1. $t\mu_{1}(\chi_{\Gamma})+(1-t)\mu_{2}(\chi_{\Gamma})=t+(1-t)=1$
>    2. $t\mu_{1}(f)+(1-t)\mu_{2}(f)\geq 0$ for $f\geq 0$.
> 2. **$\mathcal{M}(\Gamma)$ is weak*-closed**:
---
> [!lemma] Proposition 2
> Let $\lambda:\Gamma\to \text{Aut}(\ell^\infty(\Gamma,\mathbb{R}))$ s.t. $$(\lambda(\gamma)g)(x)=g(\gamma ^{-1}x)$$Then, 
> 1. $\left\| \lambda(\gamma)g \right\|_{\infty}=\left\| g \right\|_{\infty}$ for all $\gamma\in \Gamma$ and $g\in \ell^\infty(\Gamma,\mathbb{R})$
> 2. $\lambda(\gamma_{1}\gamma_{2})=\lambda(\gamma_{1})\lambda(\gamma_{2})$
> 
> Therefore, $\lambda(\gamma)$ is a bijective isometry and $\lambda(\gamma)^{*}$ is weak\*-continuous. Further, $$\begin{array}{cccc} {\lambda ^{*}:}&{\Gamma}&\to&{\text{Aut}(\ell^\infty(\Gamma)^{*})}\\&{\gamma} &\mapsto & {\lambda(\gamma ^{-1})^{*}} \end{array}{}$$is a [[group homomorphism]].

> [!proof]-
> We have: 
> 1. For any $x\in \Gamma$,$$\left| (\lambda(\gamma)g)(x) \right| =\left| g(\gamma ^{-1}x) \right| \leq \left\| g \right\| _{\infty}$$Therefore, $\left\| \lambda(\gamma)g \right\|_{\infty}\leq \left\| g \right\|_{\infty}$. Further, $$\left| g(x) \right| =\left| g(\gamma ^{-1}y) \right| =\left| (\lambda(\gamma)g)(y) \right|\leq \left\| \lambda(\gamma)g \right\| _{\infty} $$
> 2. We have: $$(\lambda(\gamma_{1}\gamma_{2})g)(x)=g(\gamma_{2}^{-1}\gamma_{1}^{-1}x)=(\lambda(\gamma_{2})g)(\gamma ^{-1}x)=(\lambda(\gamma_{1})\lambda(\gamma_{2})g)(x)$$
> 3. $\lambda(\gamma ^{-1})$ is the inverse of $\lambda(\gamma)$. 
> 4. [[Weak Topology|Proposition 3]]
> 5. We have: $$\lambda ^{*}(\gamma_{1}\gamma_{2})f=\lambda(\gamma_{2}^{-1}\gamma_{1}^{-1})^{*}f=f\circ \lambda(\gamma_{2}^{-1}\gamma_{1}^{-1})=f\circ \lambda(\gamma_{2}^{-1})\circ \lambda(\gamma_{1}^{-1})=\lambda ^{*}(\gamma_{1})\lambda ^{*}(\gamma_{2})f$$
---
> [!lemma] Proposition 3
> $\mathcal{M}(\Gamma)$ is invariant under $\lambda ^{*}(\gamma)$ for all $\gamma\in \Gamma$.

> [!proof]-
> For $\mu\in \mathcal{M}(\Gamma)$ and $\gamma\in \Gamma$, $$(\lambda ^{*}(\gamma)\mu)(g)=(\lambda(\gamma ^{-1})^{*}\mu)(g)=\mu (\lambda(\gamma ^{-1})(g))$$Therefore,
> 1. $(\lambda ^{*}(\gamma)\mu)(\chi_{\Gamma})=\mu(\lambda(\gamma ^{-1})(\chi_{\Gamma}))=\mu(\chi_{\Gamma})=1$
> 2. $(\lambda ^{*}(\gamma)\mu)(g)=\mu(\lambda(\gamma ^{-1})(g))\geq 0$ as $\lambda(\gamma^{-1})g\geq 0$. 
> 
> This shows that $\lambda ^{*}(\gamma)(\mathcal{M}(\Gamma))\subseteq \mathcal{M}(\Gamma)$.
