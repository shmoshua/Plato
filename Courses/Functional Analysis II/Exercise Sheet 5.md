#Series #FunctionalAnalysis 
> [!def] Problem 1
> Let $X$ be a compact Hausdorff space, $\mathcal{B}_{X}$ the set of Borel sets in $X$, $\mathcal{H}$ a Hilbert space, and $E:\mathcal{B}_{X}\to \mathcal{B}(\mathcal{H})$ a resolution of the identity.
> Show that the space $\mathcal{B}^\infty(X)$ equipped with the supremum norm $\|\cdot\|$ is a $C^{*}$-algebra.

We have:
1. **Showing $\mathcal{B}^\infty(X)$ is a Banach space with the sup norm**:
	Let $\{ f_{k} \}_{k}\subseteq \mathcal{B}^\infty(X)$ be a Cauchy sequence. Then, for all $x\in X$, $\{ f_{k}(x) \}_{k}$ is a Cauchy sequence and there exists $f:X\to \mathbb{C}$ s.t. $f_{k}(x)\to f(x)$ for all $x\in X$. As $f=\limsup_{ k \to \infty }f_{k}$, $f$ is Borel-measurable. 
	
	Then, for $\varepsilon>0$, there exists $N$ s.t. $\left\| f_{n}-f_{k} \right\|<\varepsilon$ for all $n,k\geq N$. We have, $$\left\| f-f_{k} \right\| =\sup_{x\in X}\left|f(x)-f_{k}(x)  \right|\leq \limsup_{ n \to \infty } \left\| f_{n}-f_{k} \right\| \leq \varepsilon $$and $f_{k}\to f$ in supremum norm. Further, $\|f\|\leq\|f-f_{k}\|+\|f_{k}\|<+\infty$. Therefore, $f\in \mathcal{B}^\infty(X)$.
2. **Showing $\mathcal{B}^\infty(X)$ is an involutive Banach algebra**:
	Let $f,g\in \mathcal{B}^\infty(X)$. Then, $$\left\| fg \right\| =\sup_{x\in X}\left| f(x)g(x) \right| \leq \sup_{x\in X}\left| f(x) \right| \sup_{x\in X}\left| g(x) \right|=\|f\|\cdot \|g\| $$Further, with the involution $f^{*}=\overline{f}$, one easily sees that $\mathcal{B}^\infty(X)$ is an involutive Banach algebra.
3. **Showing $\mathcal{B}^\infty(X)$ is a $C^{*}$-algebra**:
	For $f\in\mathcal{B}^\infty(X)$,$$\left\| f\overline{f} \right\|=\sup_{x\in X}\left| f(x) \right| ^{2}=(\sup_{x\in X}\left| f(x) \right| )^{2}=\left\| f \right\| ^{2} $$
 	Therefore, $\mathcal{B}^\infty(X)$ is a $C^{*}$-algebra.
---
> [!def] Problem 2
> Prove for all $f,g\in \mathcal{B}^\infty(X)$:
> 1. $\|f\|_{\infty}\leq\|f\|$
> 2. $\|f+g\|_{\infty}\leq\|f\|_{\infty}+\|g\|_{\infty}$
> 3. $\|fg\|_{\infty}\leq\|f\|_{\infty}\|g\|_{\infty}$

We have:
1. It suffices to show that $\text{ess im}(f)\subseteq \text{im}(f)$. Let $(D_{n})_{n}$ be a countable basis of $\mathbb{C}$ and $B:=B_{\leq\|f\|}(0)$ in $\mathbb{C}$. Then, $\text{im }f\subseteq B$.
   
   If 
2. 
3. If $\text{im}(f)=\mathbb{C}$, the inclusion holds trivially. Assume $\text{im}(f)$ is dense and $\lambda\in \text{ess im}(f)$. Then, for any $D_{n}$ with there exisst $\lambda_{n}\in D_{n}\cap \text{im}(f)$ and $\varnothing\neq f^{-1}(\lambda_{n})\subseteq f^{-1}(D_{n})$
4. 
   Assume there exists $\lambda\in \text{ess im}(f)$ but $\lambda\notin \text{im}(f)$. 
3. Let $D_{n}\cap \text{im}(f)=\varnothing$. Then, $f^{-1}(D_{n})=\varnothing$ and $E(f^{-1}(D_{n}))=0$. Therefore, $D_{n}\cap \text{ess im}(f)=\varnothing$.
4. 
---
> [!def] Problem 3
> Prove the equality $\|f+g\|_{\infty}=\|f\|_{\infty}$ for all $f\in \mathcal{B}^\infty(X)$ and $g\in N$. Deduce that the quotient norm on $\mathcal{B}^\infty(X) / N$ is given by $\|f+N\|_{\infty}=\|f\|_{\infty}$.
---
> [!def] Problem 4
> Show that the $L^\infty(X):=\mathcal{B}^\infty(X) / N$ equipped with the quotient norm is a $C^{*}$-algebra. Furthermore, show that $$\text{Sp}_{L^\infty(X)}(f+N)=\text{ess im}(f)$$the spectrum equals the essential image for all $f\in \mathcal{B}^\infty(X)$.

