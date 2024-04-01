#Series #FunctionalAnalysis 
> [!def] Problem 1
> Let $X$ be a compact Hausdorff space, $\mathcal{B}_{X}$ the set of Borel sets in $X$, $\mathcal{H}$ a Hilbert space, and $E:\mathcal{B}_{X}\to \mathcal{B}(\mathcal{H})$ a resolution of the identity.
> Show that the space $\mathcal{B}^\infty(X)$ equipped with the supremum norm $\|\cdot\|$ is a $C^{*}$-algebra.

We have:
1. **Showing $\mathcal{B}^\infty(X)$ is a Banach space with the sup norm**:
   Firstly, one can easily see that $\mathcal{B}^\infty(X)$ is a normed space. To see that $\mathcal{B}^\infty(X)$ is a Banach space, let $(f_{n})_{n}\subseteq \mathcal{B}^\infty(X)$ be a Cauchy sequence. Then, $(f_{n}(x))_{n}$ is a Cauchy sequence in $\mathbb{C}$ for all $x\in X$ and there exists $f:X\to \mathbb{C},x\mapsto \lim_{ n \to \infty }f_{n}(x)$. Then, as $f=\limsup_{ n \to \infty }f_{n}$, $f$ is Borel-measurable. Further, $$\|f\|=\sup_{x\in X}$$

---
> [!def] Problem 2
> Prove for all $f,g\in \mathcal{B}^\infty(X)$:
> 1. $\|f\|_{\infty}\leq\|f\|$
> 2. $\|f+g\|_{\infty}\leq\|f\|_{\infty}+\|g\|_{\infty}$
> 3. $\|fg\|_{\infty}\leq\|f\|_{\infty}\|g\|_{\infty}$
---
> [!def] Problem 3
> Prove the equality $\|f+g\|_{\infty}=\|f\|_{\infty}$ for all $f\in \mathcal{B}^\infty(X)$ and $g\in N$. Deduce that the quotient norm on $\mathcal{B}^\infty(X) / N$ is given by $\|f+N\|_{\infty}=\|f\|_{\infty}$.
---
> [!def] Problem 4
> Show that the $L^\infty(X):=\mathcal{B}^\infty(X) / N$ equipped with the quotient norm is a $C^{*}$-algebra. Furthermore, show that $$\text{Sp}_{L^\infty(X)}(f+N)=\text{ess im}(f)$$the spectrum equals the essential image for all $f\in \mathcal{B}^\infty(X)$.

