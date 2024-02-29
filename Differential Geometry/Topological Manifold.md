#Definition #DifferentialGeometry 

> [!definition]
> A ***topological manifold $M$ of dimension $m$*** is a [[topological space]] that is:
> 1. [[Hausdorff Space|Hausdorff]] $(T_{2})$ 
> 2. **second countable**: the topology admits a countable basis $\mathcal{B}=\{ U_{n} \}_{n}$
> 3. **locally homeomorphic to $\mathbb{R}^m$**: every point $p\in M$ admits an open neighborhood $U\subseteq M$ s.t. $\varphi :U\to \varphi(U)\subseteq\mathbb{R}^m$ is a [[homeomorphism]].
- **Related definition**: In a topological manifold $M$, we have:
  1. a ***chart*** $(U,\varphi)$
	2. the ***coordinate neighborhood*** $U$ of $\varphi$.
	3. the ***coordinate space*** $\varphi(U)$ of $\varphi$.
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
##### Examples
> [!h] Example 1
> The following are topological manifolds:
> 1. A countable discrete space $X$ is a zero-dimensional topological manifold.
> 1. $\mathbb{R}^m$ or a non-empty open set $U\subseteq \mathbb{R}^m$ is a manifold of dimension $m$.
> 2. $S^n:=\left\{  (x_{1},\dots,x_{n+1})\in \mathbb{R}^{n+1}:\sum_{i=1}^{n+1}x_{i}^{2}=1 \right\}$