#Series #FunctionalAnalysis 

> [!def] Problem 1
> Let $\mathcal{H}$ be a Hilbert space and $T\in \mathcal{B}(\mathcal{H})$ a normal operator. Show that: $$\left\| T \right\| =\sup_{\|x\|\leq 1} \left| \braket{ Tx , x }  \right| $$

**Solution 1**:
By Cauchy-Schwarz, it is clear that $\left| \braket{ Tx , x } \right|\leq \left\| T \right\|$ for all $\|x\|\leq 1$. Therefore, it suffices to show that for every $\varepsilon>0$, there exists $x\in \mathcal{H}$ with $\|x\|\leq 1$ s.t. $\left| \braket{ Tx , x } \right|> \left\| T \right\|-\varepsilon$. As $T$ is normal, $\|T\|=\|T\|_{\text{sp}}$ and by the spectral radius formula, $$\left\| T \right\| =\left\| T \right\| _{\text{sp}}=\max\{ \left| \lambda \right| :\lambda\in \text{Sp}(T)\}$$Let $\lambda_{0}\in \text{Sp}(T)$ s.t. $\left| \lambda_{0} \right|=\left\| T \right\|$. Further, let $\omega:=\text{Sp}(T)\cap B_{<\varepsilon}(\lambda_{0})$. Then, $\omega$ is non-empty and open and by the spectral theorem, $E(\omega)\neq 0$. Let $x_{0}\in \text{Im}(\omega)$ with $\|x_{0}\|=1$. Then, $$(T-\lambda_{0}\text{id}_{\mathcal{H}})E(\omega)=((\text{id}_{\mathcal{H}}-\lambda_{0}1)\chi_{\omega})(T)$$and 
$$\begin{align}\left| \braket{ Tx_{0} , x_{0} } - \lambda_{0} \right|=\left| \braket{ Tx_{0} , x_{0} } - \lambda_{0}\braket{ x_{0} , x_{0} } \right| &=\left| \braket{ (T-\lambda_{0}\text{id}_{\mathcal{H}})E(\omega)x_{0} , x_{0} } \right|\\&\leq \int_{\omega}^{} \left| \lambda-\lambda_{0} \right|  \, dE_{x_{0},x_{0}}(\lambda)  \\&<\varepsilon \braket{  E(\omega)x_{0} , x_{0} } \\&=\varepsilon\end{align}$$As $\left| \lambda_{0} \right|=\left\| T \right\|\geq \left| \braket{ Tx_{0} , x_{0} } \right|$, $\left\| T \right\|-\left| \braket{ Tx_{0} , x_{0} } \right|<\varepsilon$. This proves the statement.

---
**Solution 2 without Spectral Theorem?**:
As $T$ is normal, $\|T\|=\|T\|_{\text{sp}}$ and by the spectral radius formula, $$\left\| T \right\| =\left\| T \right\| _{\text{sp}}=\max\{ \left| \lambda \right| :\lambda\in \text{Sp}(T)\}$$Let $\lambda\in \mathbb{C}$ s.t. $\left| \lambda \right|=\text{sup}_{\|x\|\leq 1}\left| \braket{ Tx , x } \right|+c$ for some $c>0$. Further, let $0\neq x\in \mathcal{H}$ with $\|x\|\leq 1$,  then:$$\left| \braket{ Tx , x } \right|\leq \left| \lambda \right|-c\leq(\left|\lambda \right|-c)\|x\|^{2}$$ It follows that $\left| \braket{ Tx , x } \right|-\left| \lambda \right|\|x\|^{2}\leq-c\|x\|^{2}\leq 0$ and  $$\left\| (T-\lambda \text{id}_{\mathcal{H}})x \right\| \|x\|\geq \left| \braket{ (T-\lambda \text{id}_{\mathcal{H}})x , x }  \right| =\left| \braket{ Tx , x } -\lambda \braket{ x , x }  \right| \geq \left| \left| \braket{ Tx , x } \right|  -\left| \lambda \right| \|x\|^{2} \right|\geq c\|x\|^{2} $$As $T-\lambda \text{id}_{\mathcal{H}}$ is normal as well, this shows that $T-\lambda \text{id}_{\mathcal{H}}$ is invertible and $\lambda\notin \text{Sp}(T)$. This shows that $\left\| T \right\|\leq \text{sup}_{\|x\|\leq 1}\left| \braket{ Tx , x } \right|$. 

The opposite inequality is shown using Cauchy-Schwarz as in Solution 1.

---
> [!def] Problem 2
> Let $\mathcal{H}$ be a Hilbert space and $T\in \mathcal{B}(\mathcal{H})$ a normal operator. Suppose there is an operator $S\in \mathcal{B}(\mathcal{H})$ such that $$S=\int_{\text{Sp}(T)}^{} f \, dE_{T}$$ for some $f\in\mathcal{B}^\infty(\text{Sp}(T))$. This implies that $S$ is a normal operator. Prove that the resolutions of the identity $E_{T}$ and $E_{S}$ associated with $T$ and $S$ by the spectral theorem are related by $$E_{S}(\omega)=E_{T}(f^{-1}(\omega))$$ for each Borel set $\omega \subseteq \text{Sp}(S)$.

We have that: $$\max_{\lambda\in \text{Sp}(S)}\left| \lambda \right|=\|S\|\leq\|f\|=\sup\{ \left| f(\lambda) \right|:\lambda\in \text{Sp}(T) \}$$Therefore, there exists a compact $K\subseteq \mathbb{C}$ s.t. $\text{Sp}(S)\subseteq K$ and $f(\text{Sp}(T))\subseteq K$. We will extend $E_{S}$ onto $K$ and show that $f_{*}(E_{T})$ and $E_{S}$ coincides on $K$, which proves the statement.
1. **Extension of $E_{S}$**: We define for $\omega\in \mathcal{B}_{K}$: $$\tilde{E}_{S}(\omega)=E_{S}(\omega \cap \text{Sp}(S))$$

   Then, let's show that $\tilde{E}$ is a resolution of identity on $K$. We have $\tilde{E}_{S}(\varnothing)=E_{S}(\varnothing)=0$, $\tilde{E}_{S}(K)=E_{S}(\text{Sp}(S))=\text{id}_{\mathcal{H}}$. For any $\omega \in \mathcal{B}_{K}$, $\tilde{E}_{S}(\omega)$ is a self-adjoint projection by definition. Then, $$\tilde{E}_{S}(\omega_{1}\cap\omega_{2})=E_{S}(\omega_{1}\cap \text{Sp}(S)\cap\omega_{2}\cap \text{Sp}(S))=E_{S}(\omega_{1}\cap \text{Sp}(S))E_{S}(\omega_{2}\cap \text{Sp}(S))=\tilde{E}_{S}(\omega_{1})\tilde{E}_{S}(\omega_{2})$$Further, for $\omega_{1}\sqcup \omega_{2}$, $$\tilde{E}_{S}(\omega_{1}\sqcup\omega_{2})=E_{S}((\omega_{1}\cap\text{Sp}(S))\sqcup(\omega_{2}\cap\text{Sp}(S))  )=\tilde{E}_{S}(\omega_{1})+\tilde{E}_{S}(\omega_{2})$$The last property is inherited from $E_{S}$ as well. Lastly, for $\omega\in \mathcal{B}_{\text{Sp}(S)}$, $\tilde{E}_{S}(\omega)=E_{S}(\omega)$.
   
1. **Showing that of $\tilde{E}_{S}$ coincides with $f_{*}E_{T}$**: 
   As $E_{T}(f^{-1}(K \backslash f(\text{Sp}(T))))=0$, $$S=\int_{\text{Sp}(T)}f(\lambda)  \, dE_{T}(\lambda)=\int_{f(\text{Sp}(T))}\xi  \, dE_{T}(f^{-1}(\xi))=\int_{K}\xi  \, dE_{T}(f^{-1}(\xi))$$Similarly, as $\tilde{E}_{S}(K \backslash\text{Sp}(S))=E_{S}(\varnothing)=0$,$$S=\int_{\text{Sp}(S)}\xi  \, d\tilde{E}_{S}(\xi)=\int_{K}\xi  \, d\tilde{E}_{S}(\xi) $$Due to the spectral theorem, it further holds that: $$\int_{K}\overline{\xi} \, dE_{T}(f^{-1}(\xi))=S^{*}=\int_{K}\overline{\xi}  \, d\tilde{E}_{S}(\xi)$$
	Then, it holds that for $p\in \mathbb{C}[X,Y]$, $$\int_{K}p(\xi,\overline{\xi}) \, dE_{T}(f^{-1}(\xi))=p(S,S^{*})=\int_{K}p(\xi,\overline{\xi}) \, d\tilde{E}_{S}(\xi)  $$As $\xi\mapsto p(\xi,\overline{\xi})$ is dense in $C(K)$, $$\int_{C}^{} g(\xi) \, dE_{T}(f^{-1}(\xi))=g(S)=\int_{C} g(\xi) \, d\tilde{E}_{S}(\xi), \quad \forall g\in C(K)  $$which implies that $f_{*}E_{T}=\tilde{E}$ on $K$ and thereby on $\text{Sp}(S)$.
---
> [!def] Problem 3
> Let $G$ be a finite group and $H\leq G$ a subgroup. Recall that $G$ acts on a set $X$ ***doubly transitively*** if for all $x_{1},x_{2},y_{1},y_{2}\in X$ with $x_{1}\neq x_{2}$ and $y_{1}\neq y_{2}$ there is $g\in G$ with $x_{1}=gx_{2}$ and $y_{1}=gy_{2}$. Define the Hilbert space $$\mathcal{H}:=\left\{  f\in \ell^2(G / H) :\sum_{gH\in G / H}^{}f(gH)=0 \right\}$$
>and put $(\pi(g)f)(xH):=f(g^{-1}xH)$ for all $f\in \mathcal{H}$ and $g,x\in G$. This $G$-action defines a unitary representation of $G$ on $\mathcal{H}$. Show that $\pi$ is irreducible if and only if the $G$-action on $G / H$ is doubly transitive.

We show the following:
1. **$G$-action on $G / H$ is doubly transitive if and only if $[G:H]\leq 2$**:
   Let the $G$-action be doubly transitive and assume $[G:H]\geq 3$. Then, we have $xH,yH,zH$, all different s.t. there exists $g\in G$ with: $yH=gxH=zH$ which is a contradiction.  
   
   Conversely, if $[G:H]=1$, the action is trivially doubly transitive. If $[G:H]=2$ with $G / H=\{ eH,aH \}$, then $H$ is a normal subgroup of $G$ with $a^{2}=e$. Therefore, there exists $a\in G$ s.t. $aeH=aH$ and $aaH=eH$. This shows that the action is doubly transitive.
2.  **$\pi$ is irreducible if and only if $[G:H]\leq 2$**:
   If $[G:H]=1$, $H=G$ and $\mathcal{H}=\{ 0 \}$. If $[G:H]=2$ with $G / H=\{ eH,xH \}$, then $\mathcal{H}\cong \mathbb{C}$ s.t. $$\begin{array}{cccc} {J:}&{\mathbb{C}}&\to&{\mathcal{H}}\\&{\lambda} &\mapsto & {f(eH)=\lambda,f(xH)=-\lambda} \end{array}{}$$Then, let $V$ be a non-zero closed invariant subspace with $J(\lambda)=f\in V$ with $\lambda\neq 0$. Let $g\in V^{\bot}$. Then, $$\braket{ f , g } =f(eH)\overline{g(eH)}+(-f(eH))(\overline{-g(eH)})=0$$and it follows that $g(eH)=0$ and $V^{\bot}=(0)$. Therefore, $V=\mathcal{H}$. This shows that $\pi$ is irreducible.
   
   Conversely, let $[G:H]\geq 3$ and let $eH,xH,yH\in G / H$ be pairwise different. Then, $$f$$
   
  
---
Assume that the $G$-action is not doubly transitive. Then, there exists $xH,yH,aH,bH\in G / H$ with $xH\neq aH$ and $yH\neq bH$ s.t. for all $g\in G$, either $yH\neq gxH$ or $bH\neq gaH$.
1. **Case 1**: $xH=yH$ or $aH=bH$. 
	Wlog assume that $xH=yH$. Then $aH\neq bH$ otherwise $g=e$ contradicts. As $xH=yH\neq bH$, we define $f,f'\in \mathcal{H}$ where: $$f(P):=\begin{cases}1&P=xH\\-1&P=aH\\0&\text{otherwise}\end{cases},\quad f'(P):=\begin{cases}1&P=yH\\-1&P=bH\\0&\text{otherwise}\end{cases}$$
---
Assume that the $G$-action is doubly transitive. Let $V\subseteq \mathcal{H}$ be a closed invariant subspace s.t. $V\neq(0)$. We claim that for any $xH\neq yH\in G / H$, there exists $e_{x,y}\in V$ s.t. $$e_{i,j}(P)=\begin{cases}1&P=xH\\-1&P=yH\\0&\text{otherwise}\end{cases}$$

Let $0\neq f\in V$ and as $G$-action is doubly transitive, wlog we can assume that $f(xH)\neq 0$. Now consider, $$h:=\sum_{g\in \text{St}(xH)}^{}\pi(g)f\in V$$where $\text{St}(xH)$ denotes the stabilizer of $xH$. Then, $h(xH)=\left| \text{St}(xH) \right|\cdot f(xH)$ and for every $yH\neq xH$, $$h(yH)=\sum_{g\in \text{St}(xH)}^{}f(g^{-1}yH)$$