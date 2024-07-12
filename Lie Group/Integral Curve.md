#Definition #LieGroups 

> [!definition]
> Let $M$ be a [[smooth manifold]]. For a [[vector field]] $X$ an ***integral curve*** on $X$ is a smooth map $\gamma:(a,b)\to M$ with: $$\dot{\gamma}(t)=X_{\gamma(t)},\quad \forall t\in I$$
---
##### Properties
> [!lemma] Theorem 1 (Existence and Uniqueness of solutions of ODEs)
> Let $X\in \Gamma(\text{T}M)$. For every $p\in M$, there exists an open interval $I_{p}\subseteq \mathbb{R}$ ($(-\infty,b),(a,\infty)$ possible) and a smooth curve $\gamma_{p}:I_{p}\to M$ s.t. 
> 1. $0\in I_{p}$ with $\gamma_{p}(0)=p$.
> 2. $\gamma_{p}$ is an integral curve on $X$.
> 3. if $\mu:J\to M$ satisfies 1 and 2, $J\subseteq I_{p}$ and $\mu|_{J}=\gamma_{p}|_{J}$.
- **Related definition**: $X$ is called ***complete*** if $I_{p}=\mathbb{R}$ for all $p\in M$.
---
##### Examples
> [!h] Example 1 (Left-Invariant Vector Fields)
> Let $G$ be a [[Lie group]]. Then, 
> 1. if $X\in \Gamma(\text{T}M)$ is [[Vector Field|$G$-invariant]], $X$ is complete.
> 2. For every $v\in \mathfrak{g}=\text{T}_{e}G$, let $v^L\in \Gamma(\text{T}G)$ be the corresponding $G$-invariant vector field given as: $$v^L_{g}=d_{e}L_{g}(v)$$ (cf. [[Lie Algebra|Proposition 1]]) Let $\gamma_{v}:\mathbb{R}\to G$ be the integral curve with $\gamma_{v}(0)=e$. Then, the [[flow]] of $v^L$ on $G$ is given by: $$\Phi_{v^L}:\mathbb{R}\times G\to G;\quad (t,g)\mapsto g\cdot \gamma_{v}(t)$$
> 3.  $\gamma_{v}$ is a smooth group homomorphism, i.e. $\gamma_{v}$ is a [[one-parameter subgroup]] of $G$.
> 4. For any [[one-parameter subgroup]] $\varphi:\mathbb{R}\to G$, we have that $\varphi=\gamma_{\varphi'(0)}$.

> [!proof]-
> We have:
> 1. Let $\gamma_{e}:I_{e}\to G$ be the maximal integral curve of $X$ given by Theorem 1. Notice that $\gamma_{v}:=\gamma_{e}$. Then, define $\gamma_{g}$ with: $$\gamma_{g}(t):=g\cdot \gamma_{e}(t)$$We claim that $\gamma_{g}$ is an integral curve of $X$ through $g$. We have that: $$\gamma'_{g}(t)=dL_{g}(\gamma'_{e}(t))=dL_{g}(X_{\gamma_{e}(t)})=X_{g\cdot \gamma_{e}(t)}=X_{\gamma_{g}(t)}$$Let $\delta>0$ s.t. $(-\delta,\delta)\subseteq I_{e}$. Let: $$\gamma(t):=\begin{cases}\gamma_{e}(t)&t\in I_{e}=:(a_{e},b_{e})\\\gamma_{e}(\delta)\cdot \gamma_{e}(t-\delta)=\gamma_{\gamma_{e}(\delta)}(t-\delta)&t\in(a_{e}+\delta,b_{e}+\delta) \end{cases}$$ which is well-defined as both curves are integral curves of $X$ through $e$. Therefore, we have a contradiction unless $b_{e}=+\infty$. By symmetry, we have that $I_{e}=\mathbb{R}$. As $\gamma_{g}(t)=g\cdot\gamma_{e}(t)$ is an integral curve, $I_{g}=\mathbb{R}$ for any $g\in G$ and $X$ is complete.
> 2. We have that: $$\Phi_{v^L}(t,g)=\gamma_{g}(t)=g\cdot \gamma_{e}(t)=g\cdot \gamma_{v}(t)$$
> 3. We have: $$\gamma_{v}(t_{1}+t_{2})=\gamma_{v}(t_{2}+t_{1})=\Phi_{v^L}(t_{2}+t_{1},e)=\Phi_{v^L}(t_{2},\Phi_{v^L}(t_{1},e))=\Phi_{v^L}(t_{2},\gamma_{v}(t_{1}))=\gamma_{v}(t_{1})\cdot \gamma_{v}(t_{2})$$
> 4. Let $v:=\varphi'(0)\in \text{T}_{e}G$ and $v^L$ the corresponding vector field. Then, we have: $$\varphi'(t)=\left. \frac{d}{ds} \right| _{s=0}\varphi(t+s)=\left. \frac{d}{ds} \right| _{s=0}\varphi(t)\varphi(s)=\left. \frac{d}{ds} \right| _{s=0}(L_{\varphi(t)}\circ \varphi)(s)=dL_{\varphi(t)}(v)=v^L_{\varphi(t)}$$Therefore, $\varphi(t)$ is an integral curve of $v^L$ through $e$ and by uniqueness, $\varphi=\gamma_{\varphi'(0)}$.
---
