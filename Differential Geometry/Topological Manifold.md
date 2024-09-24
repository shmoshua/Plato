#Definition #DifferentialGeometry 

> [!definition]
> A ***topological manifold $M$ of dimension $m$*** is a [[Topological Space]] that is:
> 1. [[Hausdorff Space|Hausdorff]] $(T_{2})$ 
> 2. **second countable**: the topology admits a countable base $\mathcal{B}=\{ U_{n} \}_{n}$
> 3. **locally homeomorphic to $\mathbb{R}^m$**: every point $p\in M$ admits an open neighborhood $U\subseteq M$ s.t. $\varphi :U\to \varphi(U)\subseteq\mathbb{R}^m$ is a [[Homeomorphism]] and $\varphi(U)\subseteq \mathbb{R}^m$ is open.
- **Related definition**: In a topological manifold $M$, we have:
  1. a ***chart*** $(U,\varphi)$, i.e. a homeomorphism $\varphi:U\to\varphi(U)\subseteq \mathbb{R}^m$
	2. the ***coordinate neighborhood*** $U$ of $\varphi$.
	3. the ***coordinate space*** $\varphi(U)$ of $\varphi$.
	4. the ***coordinate functions*** $x^1,\dots,x^m:U\to \mathbb{R}$ s.t. $\varphi=(x_{1},\dots,x^m)$. 
- **Related definition**: Let $(U_{\alpha},\varphi_{\alpha}),(U_{\beta},\varphi_{\beta})$ be two charts s.t. $U_{\alpha}\cap U_{\beta}\neq \varnothing$. Then, 
	$\\$
	```tikz
	\usepackage{tikz-cd}
	\definecolor{hihi}{RGB}{197,173,227}
	\usetikzlibrary{3d,patterns}
	\begin{document}
	\begin{tikzpicture}[domain=-4:4] 
	\begin{scope}
	  \clip (3,0) ellipse (1.5cm and 1cm);
	  \fill[color=hihi](5,0) ellipse (1.5cm and 1cm);
	\end{scope}
	\draw (3,0) ellipse (1.5cm and 1cm);
	\node at (1.5,1) {$U_\alpha$};
	\node at (6.5,1) {$U_\beta$};
	\draw (5,0) ellipse (1.5cm and 1cm); 
	\draw (0,-4) -- (2.5,-4) -- (3,-2) -- (0.5,-2) -- cycle;
	\node at (0.5,-1.7){$\varphi_\alpha(U_\alpha)$};
	\node at (7.5,-1.7){$\varphi_\beta(U_\beta)$};
	\begin{scope}
	  \clip (0,-4) -- (2.5,-4) -- (3,-2) -- (0.5,-2) -- cycle;
	  \fill[color=hihi] (2,-4) -- (2.5,-4) -- (3,-2) -- (2.5,-2) -- cycle;
	\end{scope}
	\begin{scope}
	  \clip (8,-4) -- (5.5,-4) -- (5,-2) -- (7.5,-2) -- cycle;
	  \fill[color=hihi] (6,-4) -- (5.5,-4) -- (5,-2) -- (5.5,-2) -- cycle;
	\end{scope}
	\draw (8,-4) -- (5.5,-4) -- (5,-2) -- (7.5,-2) -- cycle;
	\draw[->] (2.7,-1.2) -- (2.3,-1.8);
	\node at (2.2,-1.4) {$\varphi_\alpha$};
	\draw[->] (5.3,-1.2) -- (5.7,-1.8);
	\node at (5.8,-1.4) {$\varphi_\beta$};
	\draw[->] (3.5,-2.8) -- (4.5,-2.8);
	\draw[->] (4.5,-3.2) -- (3.5,-3.2);
	\node at (4,-2.5) {$\theta_{\beta\alpha}$};
	\node at (4,-3.5) {$\theta_{\alpha\beta}$};
	\end{tikzpicture} 
	
	\end{document}
	```
	where the ***coordinate transformations*** are defined as:
	1. $\theta_{\beta\alpha}:=\varphi_{\beta}\circ(\varphi_{\alpha}|_{U_{\alpha}\cap U_{\beta}})^{-1}:\varphi_{\alpha}(U_{\alpha}\cap U_{\beta})\to\varphi_{\beta}(U_{\alpha}\cap U_{\beta})$
	2. $\theta_{\alpha\beta}:=\varphi_{\alpha}\circ(\varphi_{\beta}|_{U_{\alpha}\cap U_{\beta}})^{-1}:\varphi_{\beta}(U_{\alpha}\cap U_{\beta})\to\varphi_{\alpha}(U_{\alpha}\cap U_{\beta})$
- **Remark**: The coordinate transformations are [[Homeomorphism|homeomorphisms]].
	
- **Related definition**: Two charts $(U_{\alpha},\varphi_{\alpha}),(U_{\beta},\varphi_{\beta})$ are ***$C^k$-compatible***, if $\theta_{\beta\alpha},\theta_{\alpha\beta}\in C^k$.
---
##### Properties
> [!lemma] Proposition 1 
> Let $M$ be a Hausdorff space that is locally homeomorphic to $\mathbb{R}^m$. Then, 
> 1. $M$ is [[Locally Compact Hausdorff Space|locally compact]].

> [!proof]-
> As $M$ is Hausdorff, it suffices to show that every point has a compact neighborhood. Let $p\in M$. Then, let $(U,\varphi)$ be the chart containing $p$. Then, there exists $r>0$ s.t. $B:=B_{<r}(\varphi(p))\subseteq \varphi(U)$. Further, $\varphi ^{-1}(\overline{B})$ is a compact neighborhood of $p$. 
---
> [!lemma] Proposition 2 (Equivalence of Second Countability)
> Let $M$ be a Hausdorff space that is locally homeomorphic to $\mathbb{R}^m$. Then, TFAE:
> 1. $M$ is second countable.
> 2. $M$ has a countable atlas.
> 3. $M$ is $\sigma$-compact.
> 4. $M$ is a countable union of second countable connected components.
> 5. $M$ is paracompact and separable.

> [!proof]-
> We have:
> 1. (1=>2): Let $\{ U_{n} \}_{n}$ be the countable base and $(V_{\alpha},\varphi_{\alpha})_{\alpha\in I}$ be an arbitrary atlas. Modulo taking a subsequence, we can assume that there exists $\alpha\in I$ for each $n$ s.t. $U_{n}\subseteq V_{\alpha}$. Define this $V_{\alpha}$ to be $V_{n}$. Then, $(V_{n},\varphi_{n})$ is a countable atlas. 
>    
>    For any $p\in M$, there exists $V_{\alpha}\ni p$ and there exists $p\in U_{n}\subseteq V_{\alpha}$. Then, $p\in V_{n}$.
> 2. (2=>1): For each atlas, we have a countable base given by $\mathbb{R}^m$. Therefore, we have a countable base for $M$.
> 4. (1=>3): By local compactness, for each $p\in M$, there exists $p\in U_{p}$ with $\overline{U_{p}}$ compact. Further, for the countable base $\{ V_{n} \}_{n}$, there exists $p\in V_{n}\subseteq U_{p}$. Therefore, $\overline{V_{n}}\subseteq \overline{U_{p}}$ and as $\overline{U_{p}}$ is compact, so is $\overline{V_{n}}$. Therefore, $\{ \overline{V_{n}} \}_{n}$ is a countable cover of $M$ of compact sets.
> 5. (3=>1): Let $\{ K_{n} \}_{n}$ be countable compact sets s.t. $M=\bigcup_{n}^{}K_{n}$. Wlog we may assume that they are all non-empty. For each $p\in M$, let $(U,\varphi)$ be the chart containing $p$. Then, for each $k\in \mathbb{N}$, we can define $U_{p,k}:=\varphi ^{-1}(B_{< 1/k}(\varphi(p)))$ where $B_{< 1/k}(\varphi(p))\subseteq \varphi(U)$. It follows that for each $k$, $$K_{n}=\bigcup_{p\in K_{n}}^{}U_{p,k}$$and there exists a finite subcover. Hence, for each $k$ there exists a countable cover. Unioning over all $k\in \mathbb{N}$ gives us a countable basis. 
---
> [!lemma] Proposition 3 (Equivalence of  Paracompactness)
> Let $M$ be a Hausdorff space that is locally homeomorphic to $\mathbb{R}^m$. Then, TFAE:
> 1. $M$ is paracompact.
> 2. $M$ is an arbitrary union of second countable connected components.


> [!proof]- Proof (Incomplete)
> We have that:

---
##### Examples
> [!h] Example 1
> The following are topological manifolds:
> 1. A countable discrete space $X$ is a zero-dimensional topological manifold.
> 1. $\mathbb{R}^m$ or a non-empty open set $U\subseteq \mathbb{R}^m$ is a manifold of dimension $m$.
> 2. $S^n:=\left\{  (x_{1},\dots,x_{n+1})\in \mathbb{R}^{n+1}:\sum_{i=1}^{n+1}x_{i}^{2}=1 \right\}$