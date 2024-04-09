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
1. Assume $\|f\|<\|f\|_{\infty}$. Then, there exists $\lambda\in \text{ess im}(f)$ s.t. $\|f\|<\left| \lambda \right|$. However, this means that $\lambda\notin \overline{\text{im }f}$ and there exists $D_{n}\ni \lambda$ s.t. $D_{n}\cap \text{im }f=\varnothing$. Therefore, $f^{-1}(D_{n})=\varnothing$ and $E(f^{-1}(D_{n}))=0$, which gives us that $\lambda\notin \text{ess im}(f)$. This is a contradiction.
2. Let $\lambda\in \mathbb{C}$ s.t. $\|f\|_{\infty}+\|g\|_{\infty}\leq \left| \lambda \right|$. Then, for all $x\in \text{ess im}(f)$ and $y\in \text{ess im}(g)$, $\left| x +y \right|\leq \left| \lambda \right|$. We now show that $\text{ess im}(f+g)\subseteq \text{ess im}(f)+\text{ess im}(g)$. Now let $z\in \text{ess im}(f+g)$. If $z\notin \text{ess im}(f)+\text{ess im}(g)$, then for $x \in \text{ess im}(f)$, $z-x\notin \text{ess im}(g)$. This means there exists $D_{y}\ni z-x$ s.t. $E(g^{-1}(D_{y}))=0$. Let $D_{x}$ be also an 
   
	If $c\in \text{ess im}(f)\cap \text{ess im}(g)$, then $c\in \mathbb{C} \backslash \left( \bigcup_{E(f^{-1}(D_{n}))=0}^{}D_{n}\cup\bigcup_{E(g^{-1}(D_{n}))=0}^{}D_{n} \right)$. Now, for $D_{n}\ni 2c$, 

	Let $(D_{n})_{n}$ be a subcover that covers $\text{ess im}(f)$. Wlog we may assume that $D_{n}\cap \text{ess im}(f)\neq \varnothing$ and $E(f^{-1}(D_{n}))\neq 0$. 
---
> [!def] Problem 3
> Prove the equality $\|f+g\|_{\infty}=\|f\|_{\infty}$ for all $f\in \mathcal{B}^\infty(X)$ and $g\in N$. Deduce that the quotient norm on $\mathcal{B}^\infty(X) / N$ is given by $\|f+N\|_{\infty}=\|f\|_{\infty}$.

For any $a\in \mathbb{C} \backslash \{ 0 \}$, let $(D_{n_{k}})_{k}$ be a decreasing subseqeunce of $(D_{n})_{n}$ s.t. $a\in \bigcap_{k}^{}D_{n_{k}}$. Then, by assumption, for any $k\geq 1$, $E(g^{-1}(D_{n_{k}}))=0$ and $E(X \backslash g^{-1}( D_{n_{k}}))=\text{id}_{\mathcal{H}}$. Therefore, by $\sigma$-additivity of $E_{x,x}$ for any $x\in \mathcal{H}$, $$\braket{ E(X \backslash g^{-1}(a))x ,x  } =E_{x,x}$$

and $x\in \mathcal{H}$, we have that: $$\braket{ E(g^{-1}(a))x ,x  }=E_{x,x}(bigc) $$
For any $x\in \mathbb{C} \backslash \{ 0 \}$, we first show that $E(f^{-1}(x))=0$. We have that: $\text{Im }E(f^{-1}(x))\bot\ \text{Im }E(f^{-1}(\mathbb{C} \backslash \{ x \}))$. 

If $E(f^{-1}(x))\neq0$, $E(f^{-1}(x))$ and $E(f^{-1}(\mathbb{C} \backslash X))$ are non-zero and 

For any $D_{n}\ni x$, we have that $E(f^{-1}(D_{n}))=0$. Therefore,  


For any $x\in\mathbb{C} \backslash\{ 0 \}$, let $D_{x}\ni x$ be the open set in $(D_{n})_{n}$ s.t. $E(g^{-1}(D_{x}))=0$. Then, $\mathbb{C} \backslash \{ 0 \}\subseteq \bigcup_{x\in \mathbb{C} \backslash \{ 0 \}}^{}D_{x}$ and the equality holds as well as $0\in \text{ess im}(g)$. As $\{ D_{x} \}_{x\in \mathbb{C} \backslash \{ 0 \}}$ is still a sub-family of $\{ D_{n} \}_{n}$, wlog we can use $\{ D_{n_{m}} \}_{m}$ to denote this family. 

$E(f^{-1}(x))=0$. 

Now, let $\lambda\notin \text{ess im}(f+g)$. Then, for any $D_{n}\ni\lambda$, $E((f+g)^{-1}(D_{n}))=0$, where:
$$(f+g)^{-1}(D_{n})=[f^{-1}(D_{n})\cap g^{-1}(0)]\cup\bigcup_{m}^{}\{ x\in X:(f(x)+D_{n_{m}})\cap D_{n }\neq \varnothing \}\cap g^{-1}(D_{n_{m}})$$

Let $\mathbb{C} \backslash\{ 0 \}=\bigcup_{k}^{}D_{n_{k}}$. 
We have that $E(g^{-1}(\mathbb{C} \backslash\{ 0 \}))=0$. Let $\lambda\notin \text{ess im}(f+g)$. Then, for any $D_{n}\ni\lambda$, $E((f+g)^{-1}(D_{n}))=0$, where: $$(f+g)^{-1}(D_{n})=\bigcup_{x\in\mathbb{C}}^{}f^{-1}(D_{n}-x)\cap g^{-1}(x)=\bigcup_{n}^{}\bigcup_{x\in D_{n}}^{}f^{-1}(D_{n}-x)\cap g^{-1}(x)$$
It suffices to show that $\left\| f +g\right\|_{\infty}\geq \left\| f \right\|_{\infty}$. If $\left\| f+g \right\|_{\infty}<\left\| f \right\|_{\infty}$, then there exists $\lambda\in \text{ess im}(f)$ s.t. $\left\| f+g \right\|_{\infty}<\left| \lambda \right|$. Then, $\lambda\notin \text{ess im}(f+g)$ and for all $D_{n}\ni\lambda$, $E((f+g)^{-1}(D_{n}))=0$. 

---
> [!def] Problem 4
> Show that the $L^\infty(X):=\mathcal{B}^\infty(X) / N$ equipped with the quotient norm is a $C^{*}$-algebra. Furthermore, show that $$\text{Sp}_{L^\infty(X)}(f+N)=\text{ess im}(f)$$the spectrum equals the essential image for all $f\in \mathcal{B}^\infty(X)$.

