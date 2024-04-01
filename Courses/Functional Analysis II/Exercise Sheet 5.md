#Series #FunctionalAnalysis 
> [!def] Problem 1
> Let $X$ be a compact Hausdorff space, $\mathcal{B}_{X}$ the set of Borel sets in $X$, $\mathcal{H}$ a Hilbert space, and $E:\mathcal{B}_{X}\to \mathcal{B}(\mathcal{H})$ a resolution of the identity.
> Show that the space $\mathcal{B}^\infty(X)$ equipped with the supremum norm $\|\cdot\|$ is a $C^{*}$-algebra.

We have:
1. **Showing $\mathcal{B}^\infty(X)$ is a Banach space with the sup norm**:
	Let $\{ f_{k} \}_{k}\subseteq \mathcal{B}^\infty(X)$ be a Cauchy sequence. Then, for all $x\in X$, $\{ f_{k}(x) \}_{k}$ is a Cauchy sequence and there exists $f:X\to \mathbb{C}$ s.t. $f_{k}(x)\to f(x)$ for all $x\in X$. As $f=\limsup_{ n \to \infty }$
	
	Then, for $\varepsilon>0$, there exists $N$ s.t. $\left\| f_{n}-f_{k} \right\|<\varepsilon$ for all $n,k\geq N$. We have, $$\left\| f-f_{k} \right\| =\sup_{x\in X}\left|f(x)-f_{k}(x)  \right|\leq \limsup_{ n \to \infty } \left\| f_{n}-f_{k} \right\| \leq \varepsilon $$and $f_{k}\to f$ in supremum norm. Further, $\|f\|\leq\|f-f_{k}\|+\|f_{k}\|<+\infty$. It's left to show that $f$ is Borel measurable.
 	

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

