#Definition #FunctionalAnalysis 

> [!def] 
> Let $X$ be a non-compact locally compact Hausdorff space and $\alpha X$ the one point compactification of $X$. Show that the natural isomorphism $C_{0}(X)_{I}\to C(\alpha X)$ is norm-preserving.

Let: $$\begin{array}{cccc} {\varphi:}&{C_{0}(X)_{I}}&\to&{C(\alpha X)}\\&{(f,\lambda)} &\mapsto & {f_{\alpha}+\lambda} \end{array}{}$$be the natural isomorphism where $f_{\alpha}(\infty)=0$ and $f_{\alpha}|_{X}=f$.  Then,
$$\left\| L_{(f,\lambda)} \right\| =\sup_{\|g\|_{\infty}\leq 1}\|(f+\lambda)g\|_{\infty}=\sup_{\left\| g \right\| _{\infty}\leq 1}\sup_{x\in X}\left| f(x)g(x)+\lambda g(x) \right|\leq \sup_{x\in X}\left| f(x)+\lambda \right| \leq\|f_{\alpha}+\lambda \|_{\infty}$$Conversely, as $\alpha X$ is compact, there exists $x\in \alpha X$ s.t. $|f_{\alpha}(x)+\lambda|=\|f_{\alpha}+\lambda\|_{\infty}$. 
1. If $x=\infty$, then: $\left\| f_{\alpha}+\lambda \right\|_{\infty}=\left| \lambda \right|$ and for all $x\in X$, $\left| f(x)+\lambda \right|<\left| \lambda \right|$. As $f\in C_{0}(X)$, for $\varepsilon>0$, there exists compact $K\subseteq X$ s.t. $\sup_{x\in X \backslash K}\left| f(x) \right|<\varepsilon$. 
2. If $x\in X$, then there exists a compact neighborhood $K$ of $x$ and there exists by Urysohn's lemma a continuous function with compact support $g\in C_{0}(X)$ s.t. $g|_{K}\equiv1$ and $\text{Im }g\subseteq[0,1]$. Therefore, $\|L_{(f,\lambda)}\|\geq\|(f+\lambda)g\|_{\infty}=\left| f(x)+\lambda \right|=\left\| f_{\alpha}+\lambda \right\|_{\infty}$.
---
