#FunctionalAnalysis #Series 

##### Exercise 1
> Let $A$ be a unital $\mathbb{C}$-algebra and $x\in A$. Suppose there are $y,z\in A$ with $xy=zx=e$. Prove $y=z$. Moreover, prove that if there is $y'\in A$ with $xy'=e$ then $y'=y$.

We have that $\begin{align}y=ey=zxy=ze=z\end{align}$. Further, $xy'=xy=yx=e$. Therefore, $y'=y$.

---
##### Exercise 2
> Let $X$ be a locally compact Hausdorff space, which is not compact. Denote by $\alpha X$ the one-point compactification of $X$. Show that the unital algebra $C_{0}(X)_{I}$ is canonically isomorphic to $C(\alpha X)$.

Let $\alpha X:=X \cup \{ \infty \}$. Consider the map: $$\begin{array}{cccc} {\varphi:}&{C_{0}(X)_{I}}&\to&{C(\alpha X)}\\&{(f,\lambda)} &\mapsto & {f_{\alpha}+\lambda} \end{array}{}$$where $f_{\alpha}(x)=f(x)$ for $x\neq \infty$ and $f_{\alpha}(\infty)=0$. Then,
1. **Showing $\varphi$ is well-defined**:
	   For $f\in C_{0}(X)$ and $\lambda\in \mathbb{C}$, it suffices to show that $f_{\alpha}\in C(\alpha X)$. For $U\subseteq \mathbb{C}$ open, if $0\notin U$, then $f_{\alpha}^{-1}(U)=f^{-1}(U)$ which is open. Converse, if $0\in U$, then, $f^{-1}_{\alpha}(U)=f^{-1}(U)\cup \{ \infty \}$. So there exists $K\subseteq X$ compact s.t. $f^{-1}_{\alpha}(U)=(X \backslash K)\cup \{ \infty \}$. This proves that $f_{\alpha}$ is continuous.
2. **Showing $\varphi$ is an isomorphsim**:
	We have that: $$\begin{align}\varphi((f,\lambda)(g,\mu))&=\varphi((fg+\mu f+\lambda g,\lambda))\end{align}$$