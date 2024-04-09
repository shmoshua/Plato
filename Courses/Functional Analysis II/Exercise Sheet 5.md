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

We first show that for $A,B\in \mathcal{B}_{X}$, if $A\subseteq B$ and $E(B)=0$, then $E(A)=0$. We have for any $x\in \mathcal{H}$, $$\braket{ E(A)x , x } =E_{x,x}(A)\leq E_{x,x}(B)=\braket{ E(B)x , x } =0$$as $E_{x,x}$ is a positive $\sigma$-additive measure. Therefore, $E(A)=0$. 


Then, we have:
1. Assume $\|f\|<\|f\|_{\infty}$. Then, there exists $\lambda\in \text{ess im}(f)$ s.t. $\|f\|<\left| \lambda \right|$. However, this means that $\lambda\notin \overline{\text{im }f}$ and there exists $D_{n}\ni \lambda$ s.t. $D_{n}\cap \text{im }f=\varnothing$. Therefore, $f^{-1}(D_{n})=\varnothing$ and $E(f^{-1}(D_{n}))=0$, which gives us that $\lambda\notin \text{ess im}(f)$. This is a contradiction.
2. Assume $\|f+g\|_{\infty}>\|f\|_{\infty}+\|g\|_{\infty}$. Then, there exists $\lambda\in \text{ess im}(f+g)$ s.t. $$\left| \lambda \right|>\|f\|_{\infty}+\|g\|_{\infty}\geq \left| a \right| +\left| b \right|\geq \left| a+b \right| ,\quad \forall a\in \text{ess im}(f),b\in \text{ess im}(g) $$In other words, for any $a\in \text{ess im}(f)$, $\lambda-a\notin \text{ess im}(g)$. Therefore, $(\lambda-\text{ess im}(f))\cap \text{ess im}(g)=\varnothing$. As $\text{ess im}(f)$ and $\text{ess im}(g)$ are both closed, we cam set $\varepsilon:=d(\lambda-\text{ess im}(f),\text{ess im}(g))>0$. By letting $D:=B_{<\varepsilon / 2}(\lambda)$, we have $D$ as an open neighborhood of $\lambda$ and consequently, $$E((f+g)^{-1}(D))\neq 0$$Further, by definition, we also have that $(D-\text{ess im}(f))\cap \text{ess im}(g)=\varnothing$. However, $$\begin{align}(f+g)^{-1}(D)&=\bigsqcup_{x\in\mathbb{C}}^{}f^{-1}(x)\cap g^{-1}(D-x)\\&\subseteq \left[ f^{-1}(\mathbb{C} \backslash \text{ess im}(f))\cap g^{-1}(D-(\mathbb{C} \backslash \text{ess im}(f))) \right]\sqcup\left[ f^{-1}(\text{ess im}(f))\cap g^{-1}(D-\text{ess im}(f)) \right] \end{align}$$where $E(f^{-1}(\mathbb{C} \backslash \text{ess im}(f)))=0$ and $E(g^{-1}(D-\text{ess im}(f)))=0$. Therefore, by the identity we have shown above, $E((f+g)^{-1}(D))=0$ which is a contradiction.

---
> [!def] Problem 3
> Prove the equality $\|f+g\|_{\infty}=\|f\|_{\infty}$ for all $f\in \mathcal{B}^\infty(X)$ and $g\in N$. Deduce that the quotient norm on $\mathcal{B}^\infty(X) / N$ is given by $\|f+N\|=\|f\|_{\infty}$.

For any $a\in \mathbb{C} \backslash \{ 0 \}$, let $(D_{n_{k}})_{k}$ be a decreasing subseqeunce of $(D_{n})_{n}$ s.t. $a\in \bigcap_{k}^{}D_{n_{k}}$. Then, by assumption, for any $k\geq 1$, $E(g^{-1}(D_{n_{k}}))=0$ and $E(X \backslash g^{-1}( D_{n_{k}}))=\text{id}_{\mathcal{H}}$. Therefore, by $\sigma$-additivity of $E_{x,x}$ for any $x\in \mathcal{H}$, $$\braket{ E(X \backslash g^{-1}(a))x ,x  } =E_{x,x}(X \backslash g^{-1}(a))=\lim_{ k \to \infty }E_{x,x}(X \backslash g^{-1}(D_{n_{k}})) $$and $E(X \backslash g^{-1}(a))=\text{id}_{\mathcal{H}}$. Therefore, $E(g^{-1}(a))=0$. 

Now, let $\lambda\notin \text{ess im}(f+g)$. Then, for any $D_{n}\ni \lambda$, $E((f+g)^{-1}(D_{n}))=0$, where: $$(f+g)^{-1}(D_{n})=[f^{-1}(D_{n})\cap g^{-1}(0)]\sqcup \bigcup_{a\in \mathbb{C} \backslash \{ 0 \}}^{}[f^{-1}(D_{n}-a)\cap g^{-1}(a)]$$However, as $E([f^{-1}(D_{n}-a)\cap g^{-1}(a)])=E(f^{-1}(D_{n}-a))E(g^{-1}(a))=0$, we have that by [[Resolution of Identity|Lemma 5.17]], $$0=E((f+g)^{-1}(D_{n}))=E(f^{-1}(D_{n}))E(g^{-1}(0))=E(f^{-1}(D_{n}))$$Therefore, $\lambda\notin \text{ess im}(f)$. This shows that $\text{ess im}(f)\subseteq\text{ess im}(f+g)$ and $\|f\|_{\infty}\leq\|f+g\|_{\infty}$. The other inequality is given by Problem 2. 



---
> [!def] Problem 4
> Show that the $L^\infty(X):=\mathcal{B}^\infty(X) / N$ equipped with the quotient norm is a $C^{*}$-algebra. Furthermore, show that $$\text{Sp}_{L^\infty(X)}(f+N)=\text{ess im}(f)$$the spectrum equals the essential image for all $f\in \mathcal{B}^\infty(X)$.

