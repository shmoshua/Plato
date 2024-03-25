#Definition #FunctionalAnalysis 

> [!def] Problem 1
> Let $X$ be a non-compact locally compact Hausdorff space and $\alpha X$ the one point compactification of $X$. Show that the natural isomorphism $C_{0}(X)_{I}\to C(\alpha X)$ is norm-preserving.

Let: $$\begin{array}{cccc} {\varphi:}&{C_{0}(X)_{I}}&\to&{C(\alpha X)}\\&{(f,\lambda)} &\mapsto & {f_{\alpha}+\lambda} \end{array}{}$$be the natural isomorphism where $f_{\alpha}(\infty)=0$ and $f_{\alpha}|_{X}=f$.  Then,
$$\left\| L_{(f,\lambda)} \right\| =\sup_{\|g\|_{\infty}\leq 1}\|(f+\lambda)g\|_{\infty}=\sup_{\left\| g \right\| _{\infty}\leq 1}\sup_{x\in X}\left| f(x)g(x)+\lambda g(x) \right|\leq \sup_{x\in X}\left| f(x)+\lambda \right| \leq\|f_{\alpha}+\lambda \|_{\infty}$$Conversely, as $\alpha X$ is compact, there exists $x\in \alpha X$ s.t. $|f_{\alpha}(x)+\lambda|=\|f_{\alpha}+\lambda\|_{\infty}$. 
1. If $x=\infty$, then: $\left\| f_{\alpha}+\lambda \right\|_{\infty}=\left| \lambda \right|$ and for all $x\in X$, $\left| f(x)+\lambda \right|<\left| \lambda \right|$. As $f\in C_{0}(X)$, for $\varepsilon>0$, there exists compact $K_{\varepsilon}\subseteq X$ s.t. $\sup_{x\in X \backslash K_{\varepsilon}}\left| f(x) \right|<\varepsilon$. If $K_{1 / n}=X$ for all $n\in \mathbb{N}$, then $f\equiv 0$ and one can easily see that for some bump function $g\in C_{0}(X)$ with $\|g\|_{\infty}=1$, $\|(f+\lambda)g\|_{\infty}=\left| \lambda \right|$. Otherwise, modulo taking a subsequence, we can find a sequence $(x_{k})_{k}\subseteq X \backslash K_{1 / n_{k}}$ and compact sets $(P_{k})_{k}$ where $x_{k}\in P_{k}$ and $P_{k}\cap K_{1 / n_{k}}=\varnothing$. Therefore, we have by Urysohn's lemma compactly supported functions $(g_{k})_{k}\subseteq C_{0}(X)$ s.t. $\text{Im }g_{k}\subseteq[0,1]$ and $g_{k}|_{P_{k}}\equiv1$ for all $k$. It follows that $$\left\| (f+\lambda)g_{k} \right\|_{\infty}=\sup_{x\in X}\left| f(x)g_{k}(x)+\lambda g_{k}(x) \right| \geq \left| f(x_{k})+\lambda \right| $$and as $\lim_{ k \to \infty }f(x_{k})=0$, $\|L_{(f,\lambda)}\|\geq \left| \lambda \right|=\left\| f_{\alpha}+\lambda \right\|_{\infty}$.
3. If $x\in X$, then there exists a compact neighborhood $K$ of $x$ and there exists by Urysohn's lemma a continuous function with compact support $g\in C_{0}(X)$ s.t. $g|_{K}\equiv1$ and $\text{Im }g\subseteq[0,1]$. Therefore, $\|L_{(f,\lambda)}\|\geq\|(f+\lambda)g\|_{\infty}=\left| f(x)+\lambda \right|=\left\| f_{\alpha}+\lambda \right\|_{\infty}$.
---
> [!def] Problem 2
> Let $\mathcal{H}$ be a complex Hilbert space and $E\subseteq \mathcal{H}$ a vector subspace. Show $(E^{\bot})^{\bot}=\overline{E}$.

We show that $E^{\bot}=\overline{E}^{\bot}$. If for $x\in \mathcal{H}$, $\braket{ x , y }=0$ for all $y\in E$, then $\braket{ x,y  }=0$ for all $y\in\overline{E}$ by continuity. The other direction is trivial. 

Then, we have $\overline{E}\subseteq(\overline{E}^{\bot})^{\bot}=(E^{\bot})^{\bot}$. Conversely, let $x\in (E^{\bot})^{\bot}$. Then, $x=x_{1}+x_{2}$ where $x_{1}\in \overline{E}$ and $x_{2}\in E^{\bot}$. Therefore, for any $y\in E^{\bot}$, $0=\braket{ x , y }=\braket{ x_{2} , y }$ and $x_{2}= 0$, which shows that $x\in \overline{E}$. This shows $(E^{\bot})^{\bot}\subseteq \overline{E}$.

---
> [!def] Problem 3
> Let $\mathcal{H}$ be a complex Hilbert space and $T\in \mathcal{B}(\mathcal{H})$. Prove $\text{ker}(T^{*})=(\text{Im }T)^{\bot}$ and $\text{ker }T=(\text{Im}(T^{*}))^{\bot}$.

Let $x\in \text{ker}(T^{*})$ and $y\in \text{Im }T$ with $y=Tz$. Then, $\braket{ x , y }=\braket{ x , Tz }=\braket{ T^{*}x , z }=\braket{ 0 , z }=0$. Similarly, for $x\in (\text{Im }T)^{\bot}$, we have that $\braket{ T^{*}x , z }=\braket{ x ,Tz  }=0$ for all $z\in \mathcal{H}$. This proves the statement. The other statement follows from symmetry and $(T^{*})^{*}=T$.

---
> [!def] Problem 4
> Let $\mathcal{H}$ be a finite-dimensional complex Hilbert space and $T\in \mathcal{B}(\mathcal{H})$. Prove that $T$ is normal if and only if $\mathcal{H}$ admits an orthonormal basis of eigenvectors.

Let $T\in \mathcal{B}(\mathcal{H})$ be normal. As $\mathcal{H}$ is finite-dimensional with dimension $n$, $\text{Sp}(T)$ is the set of roots of the characteristic polynomial of $T$. We know that distinct eigenvalues have orthogonal eigenspaces. Assume $A:=\{\alpha_{1},\dots,\alpha_{k} \}\subseteq \mathcal{H}$ for $k\leq n$ denote the maximal set of disjoint eigenvalues and $E$ the direct sum of the eigenspaces. Then, $T(E)\subseteq E$ and $T(E^{\bot})\subseteq E^{\bot}$: Indeed for $x\in E^{\bot}$ and $y\in E$, $$\braket{ Tx , y } =\braket{ x , T^{*}y } =\alpha \braket{ x , y } =0$$ for some $\alpha\in \mathbb{C}$. Then, consider $T|_{E^{\bot}}$ and assume $E^{\bot}\neq \{ 0 \}$. Then, $\text{Sp}_{\mathcal{B}(E^{\bot})}(T|_{E})$ is non-empty with the eigenpair $(\alpha,v)$. However, by the maximality of $A$, $\alpha\in A$ and $v\in E\cap E^{\bot}=\{ 0 \}$, which is a contradiction. Therefore, $E^{\bot}=\{ 0 \}$ and $E=\mathcal{H}$. This proves the statement.




Conversely, let $\{ v_{i} \}_{i}$ be a finite orthonormal basis of eigenvectors. Then, 
$$T^{*}T v_{i}=\lambda_{i}T^{*}v_{i}=\left| \lambda_{i} \right| ^{2}=\overline{\lambda_{i}}Tv_{i}=TT^{*}v_{i}$$This shows that $T$ is normal.
---
