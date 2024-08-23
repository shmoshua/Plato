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

> [!proof]-
> We have:
> 1. **Short term existence of a solution**: 
>    Let $p\in M$ and $(U,\varphi)$ be the largest chart containing $p$. Then, our ODE: $$\begin{align}\dot{\gamma}(t)&=X(\gamma(t))\\\gamma(0)&=p\end{align}$$translates locally to an ODE: $$\begin{align}\chi(t)&=(\chi^1(t),\dots,\chi^m(t))\\\dot{\chi^1}(t)&=X^1(\chi^1(t),\dots,\chi^m(t))\\\vdots\\\dot{\chi^m}(t)&=X^m(\chi^1(t),\dots,\chi^m(t))\end{align}$$for $a<t<b$. Then, by existence and uniqueness of ODE, there exists a solution $\gamma:(-\delta,\delta)\to M$ with the above qualities.
> 2. **$I_{p}$ is open**. Consider that we don't. Wlog, assume that we have an integral curve $\gamma:[0,T]\to M$. By having it restart at $\gamma(T)$, by short term existence, there exists $\beta:(-\delta,\delta)\to M$ s.t. $\dot{\beta}(t)=X(\beta(t))$ and $\beta(0)=\gamma(T)$. Then, consider: $$\gamma_{\text{ext}}:[0,T+\delta),\quad t\mapsto \begin{cases}\gamma(t)&0\leq t\leq T\\\beta(t-T)&T\leq t<T+\delta\end{cases}$$which is continuous and we have: $$\dot{\gamma}(T)=X(\gamma(T))=X(\beta(0))=\dot{\beta}(0)$$Therefore, $\gamma_{\text{ext}}$ is an integral curve solving the ODE system on a larger interval, which is a contradiction. The other side of the interval is analogous.
>    
- **Related definition**: $X$ is called ***complete*** if $I_{p}=\mathbb{R}$ for all $p\in M$.
---
> [!lemma] Proposition 2
> Let $X\in \Gamma(\text{T}M)$. For $p\in M$ and $I_{p}=(S,T)\subseteq \mathbb{R}$, 
> 1. if $T<+\infty$, for every compact $K\subseteq M$, there exists $t_{k}>0$ s.t. for all $t\geq t_{k}$, $\gamma_{p}(t)\notin K$.
> 2. if $S>+\infty$, for every compact $K\subseteq M$, there exists $t_{k}<0$ s.t. for all $t\leq t_{k}$, $\gamma_{p}(t)\notin K$. 

> [!proof]-
>    Let $\gamma_{p}:[0,T)\to M$ be the solution integral curve which is not extendable beyond $T$. Let $T<+\infty$ and assume that there exists a compact $K$ s.t. there exists $(t_{i})_{i}$ with $t_{i}\to T$ s.t. $\gamma_{p}(t_{i})\in K$. As compactness implies sequential compactness in 2nd countable spaces by [[Second Countable Space|Proposition 2]], modulo taking a subsequence there exists $q\in M$ s.t. $\gamma_{p}(t_{i})\to q$. By continuity, there exists $U\ni q$ open s.t. there exists a $\delta>0$ with for all $r\in U$, $\gamma_{r}:[0,\delta)\to M$ exists. 
>    
> Fix $i$ s.t. $\left| t_{i}-T \right|<\delta /2$ and $q:=\gamma(t_{i})\in U$. Then, define: $$\alpha(t)=\begin{cases}\gamma_{p}(t)&0\leq t<T\\\gamma_{q}(t-t_{i})&t_{i}\leq t<t_{i}+\delta\end{cases}$$This is well-defined as for $t\in [t_{i},T)$, both solve the ODE system $\dot{\gamma}(t)=X(\gamma(t))$ starting at $\gamma_{p}(t_{i})=q=\gamma_{q}(0)=\gamma_{q}(t_{i}-t_{i})$. Therefore, by the uniqueness $\alpha$ is well-defined. This is the contradiction to the maximality of $T$. 
- **Corollary**: If $M$ is compact, every $X\in \Gamma(\text{T}M)$ is complete.
---
##### Examples
> [!h] Example 1 (Lie Groups)
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
> [!h] Example 2 (Rn)
> Let $M:=\mathbb{R}^n$ and $X\in \Gamma(\text{T}\mathbb{R}^n)$ where
> 1. $X$ does not vanish.
> 2. $\left\| X(p) \right\|\leq C\left\| p \right\|+C$ for some $C>0$. 
> 
> Then, $X$ is complete.

> [!proof]-
> Let $p\in M$, let $\gamma$ be the maximal integral curve. Then, $$\begin{align}\left. \frac{d}{dt} \right.\left\| \gamma(t) \right\| =\frac{\gamma(t)}{\left\| \gamma(t) \right\| }\cdot \dot{\gamma}(t)\leq \left\|\dot{\gamma}(t)\right\| =\left\| X (\gamma(t))\right\| \leq C\left\| \gamma(t) \right\| +C\end{align}$$ and $\left\| \gamma(t) \right\|+1\leq \exp(Ct)(\left\|p\right\|+1)$. Therefore, on any finite interval $[0,T)$, $\left\| x(t) \right\|$ is contained in some closed ball around 0 and $x(t)$ is contained in a compact set. By Proposition 2, we get that $X$ is complete.
---
