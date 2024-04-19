#Series #FunctionalAnalysis 

> [!def] Problem 1
> Let $\mathcal{H}$ be a Hilbert space and $T\in \mathcal{B}(\mathcal{H})$ a normal operator. Show that: $$\left\| T \right\| =\sup_{\|x\|\leq 1} \left| \braket{ Tx , x }  \right| $$

As $T$ is normal, $\|T\|=\|T\|_{\text{sp}}$ and by the spectral radius formula, $$\left\| T \right\| =\left\| T \right\| _{\text{sp}}=\max\{ \left| \lambda \right| :\lambda\in \text{Sp}(T)\}$$Let $\lambda\in \mathbb{C}$ s.t. $\left| \lambda \right|=\text{sup}_{\|x\|\leq 1}\left| \braket{ Tx , x } \right|+c$ for some $c>0$. Further, let $0\neq x\in \mathcal{H}$ with $\|x\|\leq 1$,  then:$$\left| \braket{ Tx , x } \right|\leq \left| \lambda \right|-c\leq(\left|\lambda \right|-c)\|x\|^{2}$$ It follows that $\left| \braket{ Tx , x } \right|-\left| \lambda \right|\|x\|^{2}\leq-c\|x\|^{2}\leq 0$ and  $$\left\| (T-\lambda \text{id}_{\mathcal{H}})x \right\| \|x\|\geq \left| \braket{ (T-\lambda \text{id}_{\mathcal{H}})x , x }  \right| =\left| \braket{ Tx , x } -\lambda \braket{ x , x }  \right| \geq \left| \left| \braket{ Tx , x } \right|  -\left| \lambda \right| \|x\|^{2} \right|\geq c\|x\|^{2} $$As $T-\lambda \text{id}_{\mathcal{H}}$ is normal as well, this shows that $T-\lambda \text{id}_{\mathcal{H}}$ is invertible and $\lambda\notin \text{Sp}(T)$. This shows that $\left\| T \right\|\leq \text{sup}_{\|x\|\leq 1}\left| \braket{ Tx , x } \right|$. 

For the opposite inequality, from the spectral theorem there exists a unique resolution of identity $E$ on $\text{Sp}(T)$ s.t. $$T=\int_{\text{Sp}(T)}^{} \lambda \, dE(\lambda) $$Then, for any $x\in \mathcal{H}$ s.t. $\|x\|\leq 1$,$$\left| \braket{ Tx , x } \right|  \leq\int_{\text{Sp}(T)}^{}\left| \lambda \right|  \, dE_{x,x}(\lambda)\leq \max_{\lambda\in \text{Sp}(T)}\left| \lambda \right| \cdot E_{x,x}(\text{Sp}(T))=\|T\| E_{x,x}(\text{Sp}(T)) =\left\| T \right\| \|x\|^{2}\leq\|T\| $$
Equivalently, one can simply use the Cauchy-Schwarz inequality to show: $$\left| \braket{ Tx , x } \right|\leq \left\| Tx \right\|\|x\|\leq\|T\|\|x\|^{2}\leq\|T\|$$This proves the statement.

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

Assume that $\pi$ is irreducible. Then, by Schur's lemma, $\text{Int}(\pi)=\mathbb{C}\cdot \text{id}_{\mathcal{H}}$. Let $x_{1}H,x_{2}H,y_{1}H,y_{2}H\in G / H$ s.t. $x_{1}x_{2}^{-1}\notin H$ and $y_{1}y_{2}^{-1}\notin H$. We have that $T:=\lambda \cdot \text{id}_\mathcal{H}\in \text{Int}(\pi)$ and for any $g\in G$: $$\lambda f(g^{-1}xH)=(T\pi(g)f)(xH)=(\pi(g)(\lambda f))(xH)=\lambda f(g^{-1}x H)$$
Let $\pi$ be not irreducible. Then, there exists a closed invariant subspace $V$ s.t. $0\subsetneq V\subsetneq \mathcal{H}$. Let $0\neq f,g\in \mathcal{H}$ s.t. $f\in V$ and $h\in V^{\bot}$. Then, $$\sum_{xH\in G / H}^{}f(xH)\overline{h(xH)}=0$$and $\psi:G / H\to \mathbb{C},xH\mapsto f(xH)\overline{h(xH)}$. Then, $\psi\in \mathcal{H}$ and $\psi=\psi_{1}+\psi_{2}$ and: $$0=\sum_{xH\in G / H}^{}f(g^{-1}xH)\overline{h(g^{-1}xH)}=\sum_{xH\in G / H}^{}\pi(g)\psi(xH)$$

---
Let the action be doubly transitive. Then, let $V$ be a closed invariant subspace of $\mathcal{H}$. If $0\neq f\in V$, let $h\in \mathcal{H}$. We need to show that $V=\mathcal{H}$, i.e. we will show that there exists a sequence $g_{1},\dots,g_{n}\in G$ s.t. $$\pi(g_{1})\pi(g_{2})\dots \pi(g_{n})f=h$$Let $xH\in G / H$. If $f(xH)\neq h(xH)$.
$$\sum_{xH\in G / H}^{}f(xH)=0$$, $$\sum_{xH\in G / H}^{}f(g^{-1}xH)=0$$

$G=C_{8}=\{ e,a,a^{2},a^{3},\dots \}$
$H=C_{2}=\{ e,a^4 \}$

Then, $$G / H=\{ eH,aH,a^{2}H,a^3H \}$$Let $f\in \mathcal{H}$. Then, $$f(eH)+f(aH)+f(a^{2}H)+f(a^3H)=0$$$$f(eH)\overline{h(eH)}$$
