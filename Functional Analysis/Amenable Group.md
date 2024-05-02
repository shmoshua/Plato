#Definition #FunctionalAnalysis 

> [!definition]
> Let $\Gamma$ be a locally compact Hausdorff group. Then, $\mu\in \ell^\infty(\Gamma,\mathbb{R})^{*}$ is called a ***mean*** on $\ell^\infty(\Gamma,\mathbb{R})$s.t.
> 1. $\mu(1_{\Gamma})=1$ and
> 2. $\mu(f)\geq 0$ if $f\geq 0$
>    
> We use $\mathcal{M}(\Gamma)=\{ \mu\in \ell^\infty(\Gamma,\mathbb{R})^{*}:\mu \text{ is a mean} \}$. Further, we define a representation $\lambda$ of $\Gamma$ on $\ell^\infty(\Gamma, \mathbb{R})$ as: $$(\lambda(\gamma)g)(\eta)=g(\gamma ^{-1}\eta)$$ Then, $\mu\in \mathcal{M}(\Gamma)$ is ***left-invariant*** if $\mu(\lambda(\gamma)g)=\mu(g)$ for all $\gamma\in \Gamma$ and $g\in \ell^\infty(\Gamma,\mathbb{R})$.
> 
> Ultimately, a group $\Gamma$ is called ***amenable***, if there exists a left-invariant $\mu\in \mathcal{M}(\Gamma)$.
---
##### Properties

> [!lemma] Lemma 1
> $\lambda$ is a representation. Further, it holds that $\lambda(\gamma)$ is a bijective isometry, i.e. $\left\| \lambda(\gamma)g \right\|_{\infty}=\|g\|_{\infty}$.

> [!proof]-
> Firstly, we show that $\lambda$ is a group homomorphism. For $\gamma_{1},\gamma_{2}\in \Gamma$, $$\begin{align}(\lambda(\gamma_{1}\gamma_{2})g)(\eta)&=g(\gamma_{2}^{-1}\gamma_{1}^{-1}\eta)\\&=(\lambda(\gamma_{2})g)(\gamma ^{-1}_{1}\eta)\\&=(\lambda(\gamma_{1})\lambda(\gamma_{2})g)(\eta)\end{align}$$
> Secondly, it is bijective as: $$\lambda(\gamma)\lambda(\gamma ^{-1})=\lambda(\gamma \gamma ^{-1})=\lambda(e)=\text{id}$$$$\lambda(\gamma ^{-1})\lambda(\gamma )=\lambda(\gamma ^{-1} \gamma )=\lambda(e)=\text{id}$$
> and $$\begin{align}\left\| \lambda(\gamma)g \right\| _{\infty}&=\inf\{ M>0:|(\lambda(\gamma)g)(\eta)|\leq M \}\\&=\inf\{ M>0:|g(\gamma ^{-1}\eta)|\leq M \}\\&=\inf\{ M>0:|g(\eta)|\leq M \}\\&=\|g\|_{\infty}\end{align}$$
---

> [!lemma] Lemma 2
> For a discrete group $\Gamma$, $\mathcal{M}(\Gamma)$ is weak\*-closed and weak\*-compact for $\sigma(\ell^\infty(\Gamma,\mathbb{R})^{*},\ell^\infty(\Gamma,\mathbb{R}))$-topology.

> [!proof]-
> $\mathcal{M}(\Gamma)$ is weak\*-closed as the conditions are closed. Further, it is a subset of the unit ball of $\ell^\infty(\Gamma,\mathbb{R})^{*}$, therefore, compact. 
---

> [!lemma] Lemma 3
> For a discrete group $\Gamma$, we can define an adjoint representation: $$\begin{array}{cccc} {\lambda ^{*}:}&{\Gamma}&\to&{\text{Aut}(\ell^\infty(\Gamma,\mathbb{R})^{*})}\\&{\gamma} &\mapsto & {\lambda(\gamma ^{-1})^{*}} \end{array}{}$$where the [[Automorphism on Vector Spaces|automorphism]] is w.r.t. the [[Weak Topology|weak*-topology]]. Further, $\lambda ^{*}(\gamma)$ preserves $\mathcal{M}(\Gamma)$ for all $\gamma\in \Gamma$.

> [!proof]-
> We have that: $$\lambda ^{*}(\gamma_{1}\gamma_{2})f=\lambda(\gamma_{2}^{-1}\gamma_{1}^{-1})^{*}(f)=f\circ\lambda(\gamma_{2}^{-1}\gamma_{1}^{-1})=f\circ \lambda(\gamma_{2}^{-1})\circ \lambda(\gamma_{1}^{-1})=\lambda ^{*}(\gamma_{1})\lambda ^{*}(\gamma_{2})f $$Further, for a [[Weak Topology|mean]] $\mu\in \mathcal{M}(\Gamma)$, $$\lambda ^{*}(\gamma)(\mu)(g)=(\lambda(\gamma^{-1})^{*}\mu)(g)=\mu(\lambda(\gamma ^{-1})g)$$
---
> [!lemma] Theorem 4
> Let $\Gamma$ be a abelian (discrete) group. Then, $\Gamma$ is amenable. Especially, there exists a set function, $m:\mathcal{P}(\Gamma)\to[0,1]$ s.t. 
> 1. $m(\Gamma)=1$.
> 2. $m$ is finitely additive.
> 3. $m(\gamma S)=m(S)$ for all $\gamma\in \Gamma, S\subseteq\Gamma$.

> [!proof]-
> We will use [[Topological Vector Space with Seminorms|Markov-Kakutani]]. Firstly, $\mathcal{M}(\Gamma)$ is convex as for $\mu_{1},\mu_{2}\in \mathcal{M}(\Gamma)$: 
> 1. $t\mu_{1}(1_{\Gamma})+(1-t)\mu_{2}(1_{\Gamma})=t+(1-t)=1$.
> 2. for $f\geq 0$, $t\mu_{1}(f)+(1-t)\mu_{2}(f)\geq 0$.
> 
> Therefore, $t\mu_{1}+(1-t)\mu_{2}\in \mathcal{M}(\Gamma)$. From Markov-Kakutani, there exists $\mu\in \mathcal{M}(\Gamma)$ s.t. $$\lambda ^{*}(\gamma)(\mu)=\mu$$for all $\gamma\in \Gamma$. It follows that: $$\mu(\lambda(\gamma)g)=(\mu \circ \lambda(\gamma))(g)=(\lambda(\gamma)^{*}(\mu))(g)=(\lambda ^{*}(\gamma ^{-1})(\mu))(g)=\mu(g)$$which proves that $\mu$ is left-invariant. 
> 
> Further, let $m(S):=\mu(\chi_{S})$. Then, 
> 1. $m(\Gamma)=\mu(1_{\Gamma})=1$.
> 2. $m\left( S \cup T\right)=\mu(\chi_{S}+\chi_{T})=\mu(\chi_{S})+\mu(\chi_{T})=m(S)+m(T)$ for disjoint $S,T$.
> 3. $m(\gamma S)=\mu(\chi_{\gamma S})=\mu(\lambda(\gamma )\chi_{S})=\mu(\chi_{S})=m(S)$
---
> [!lemma] Remark 5
> The countable group $\Gamma$ has a Følner sequence, if there exists a sequence $F_{n}\subseteq\Gamma$ of finite subsets  s.t. for all $\gamma\in \Gamma$: $$\frac{\left| \gamma  F_{n}\triangle F_{n} \right| }{\left| F_{n} \right| }\xrightarrow{n\to \infty} 0$$Then, any countable group $\Gamma$ with a Følner sequence is amenable.

> [!proof]+
> 
---
##### Examples
> [!lemma] Proposition 
> The [[free group]] $F_{\{ a,b \}}$ is not amenable.

> [!proof]-
> Denote for a reduced word $w$, $S(w)$ as the set of elements in $F_{(a,b)}$ whose expression begins with $w$. Assume that from Theorem 4 we have a set function $m:\mathcal{P}(F_{\{ a,b \}})\to[0,1]$ s.t. 
> 1. $m(F_{\{ a,b \}})=1$,
> 2. $m$ is finitely additive,
> 3. $m(w S)=m(S)$ for all $w\in F_{\{ a,b \}}$, $S\subseteq F_{\{ a,b \}}$.
>    
> Then, $$\begin{align}S(a)&=S(ab)\sqcup S(ab^{-1})\sqcup S(aa)\\&=aS(b)\sqcup aS(b^{-1})\sqcup aS(a)\end{align}$$Therefore, $$m(S(a))=m(S(b))+m(S(b^{-1}))+m(S(a))$$from which it holds that $m(S(b))=m(S(b^{-1}))=0$ and $m(S(a))=m(S(a^{-1}))=0$, which is a contradiction. 
---
