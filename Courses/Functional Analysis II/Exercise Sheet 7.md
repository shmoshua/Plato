#Series #FunctionalAnalysis 

> [!def] Problem 1
> Let $\mathcal{H}$ be a Hilbert space and $T\in \mathcal{B}(\mathcal{H})$ a normal operator. Show that: $$\left\| T \right\| =\sup_{\|x\|\leq 1} \left| \braket{ Tx , x }  \right| $$

As $T$ is normal, $\|T\|=\|T\|_{\text{sp}}$ and by the spectral radius formula, $$\left\| T \right\| =\left\| T \right\| _{\text{sp}}=\max\{ \left| \lambda \right| :\lambda\in \text{Sp}(T)\}$$Let $\lambda\in \mathbb{C}$ s.t. $\left| \lambda \right|=\text{sup}_{\|x\|\leq 1}\left| \braket{ Tx , x } \right|+c$ for some $c>0$. Further, let $0\neq x\in \mathcal{H}$ with $\|x\|\leq 1$,  then:$$\left| \braket{ Tx , x } \right|\leq \left| \lambda \right|-c\leq(\left|\lambda \right|-c)\|x\|^{2}$$ It follows that $\left| \braket{ Tx , x } \right|-\left| \lambda \right|\|x\|^{2}\leq-c\|x\|^{2}\leq 0$ and  $$\left\| (T-\lambda \text{id}_{\mathcal{H}})x \right\| \|x\|\geq \left| \braket{ (T-\lambda \text{id}_{\mathcal{H}})x , x }  \right| =\left| \braket{ Tx , x } -\lambda \braket{ x , x }  \right| \geq \left| \left| \braket{ Tx , x } \right|  -\left| \lambda \right| \|x\|^{2} \right|\geq c\|x\|^{2} $$As $T-\lambda \text{id}_{\mathcal{H}}$ is normal as well, this shows that $T-\lambda \text{id}_{\mathcal{H}}$ is invertible and $\lambda\notin \text{Sp}(T)$. This shows that $\left\| T \right\|\leq \text{sup}_{\|x\|\leq 1}\left| \braket{ Tx , x } \right|$. 

For the opposite inequality, from the spectral theorem there exists a unique resolution of identity $E$ on $\text{Sp}(T)$ s.t. $$T=\int_{\text{Sp}(T)}^{} \lambda \, dE(\lambda) $$Then, for any $x\in \mathcal{H}$ s.t. $\|x\|\leq 1$,$$\left| \braket{ Tx , x } \right|  \leq\int_{\text{Sp}(T)}^{}\left| \lambda \right|  \, dE_{x,x}(\lambda)\leq \max_{\lambda\in \text{Sp}(T)}\left| \lambda \right| \cdot E_{x,x}(\text{Sp}(T))=\|T\| E_{x,x}(\text{Sp}(T)) =\left\| T \right\| \|x\|^{2}\leq\|T\| $$
Equivalently, one can simply use the Cauchy-Schwarz inequality to show: $$\left| \braket{ Tx , x } \right|\leq \left\| Tx \right\|\|x\|\leq\|T\|\|x\|^{2}\leq\|T\|$$This proves the statement.

---
> [!def] Problem 2
> Let $\mathcal{H}$ be a Hilbert space and $T\in \mathcal{B}(\mathcal{H})$ a normal operator. Suppose there is an operator $S\in \mathcal{B}(\mathcal{H})$ such that $$S=\int_{\text{Sp}(T)}^{} f \, dE_{T}$$ for some $f\in\mathcal{B}^\infty(\text{Sp}(T))$. This implies that $S$ is a normal operator. Prove that the resolutions of the identity $E_{T}$ and $E_{S}$ associated with $T$ and $S$ by the spectral theorem are related by $$E_{S}(\omega)=E_{T}(f^{-1}(\omega))$$ for each Borel set $\omega \subseteq \text{Sp}(S)$.

Let us define $E$ as a resolution of identity on $\text{Sp}(S)$ as follows, for any $\omega \subseteq \text{Sp}(S)$, $$E(\omega):=E_{T}(f^{-1}(\omega \sqcup  \text{Sp}(S)^c))=E_{T}(f^{-1}(\omega))E_{T}(f^{-1}(\text{Sp}(S)^c))$$Then, 
1. **Showing that $E$ is a resolution of identity on $\text{Sp}(S)$**:
   We have $E(\varnothing)=0$ and $E(\text{Sp}(S))=E_{T}(f^{-1}(\text{Sp}(S)\sqcup \text{Sp}(S)^c))=E_{T}(\text{Sp}(T))=\text{id}$. Further, by definition, $E(\omega)$ is a self-adjoint projection and: $$E(\omega_{1}\cap\omega_{2})=E(\omega)$$

$f^{-1}(\text{Sp}(S))\subsetneq \text{Sp}(T)$??
$$E(\omega)$$
---
$$E_{T}(f^{-1}(\omega))$$ is a resolution of identity? $$E_{T}(f^{-1}(\text{Sp}(S)))=\text{id}$$
$$S=\int_{\text{Sp}(T)}^{} f(\xi) \, dE_{T}(\xi)=\int_{\text{Sp}(S)}\lambda  \, dE_{S}(\lambda)$$

Let $E_{T}(f^{-1}(\text{Sp}(S)))=\text{id}$. Then, we have that $E(\omega):=E_{T}(f^{-1}(\omega))$ is a resolution of identity, s.t. $$S=\int_{\text{Sp}(S)}^{} \lambda \, dE_{S}(\lambda)=\int_{\text{Sp}(T)}f(\xi) \, dE_{T}(\xi)=\int_{f^{-1}(\text{Sp}(S))}f(\xi)  \, dE_{T}(\xi)=\int_{\text{Sp}(S)}^{} \lambda \, dE(\lambda)     $$

---
It suffices to show that:
$$E_{T}(f^{-1}(\mathbb{C} \backslash \text{Sp}(S)))=E_{T}(\text{Sp}(T) \backslash f^{-1}(\text{Sp}(S)))=0$$
If suffices to show that $\text{ess im }f\subseteq \text{Sp}(S)$. 
1. Let $\alpha\in \text{ess im }f$. Then, let $U\ni\alpha$ be open and $E_{T}(U)\neq 0$ and $\text{Im }E_{T}(U)\neq (0)$. Now, let $0\neq x\in \text{Im }E_{T}(U)$. Then, $E_{T}(U)x=x$. Then, $$\braket{ Sx , x } =\int_{U}f(\xi)  \, d(E_{T})_{x,x} $$This shows that $x\in \text{Im }E_{S}(f(U))$. Otherwise, $x=y+z$ with $y\in \text{Im }E_{S}(U)$ and $z\in \text{ker }E_{T}(U)$$$\braket{ Sx , x }=\int_{\text{Sp}(S)} \lambda \, d(E_{S})_{x,x}   $$
2. Let $\alpha\notin \text{Sp}(S)$. Then, $S-\alpha \text{id}_{\mathcal{H}}$ is invertible. 
	- There exists $c>0$ s.t. $\|(S-\alpha \text{id}_{\mathcal{H}})x\|\geq c\|x\|$ for all $x\in\mathcal{H}$.$$E_{T}(f^{-1}(\{ \left| z \right| >\left| \alpha \right|  \}))$$
---
We will extend $E_{S}$ onto $\mathbb{C}$ as follows: $$\tilde{E}_{S}(\omega)=E_{S}(\omega \cap \text{Sp}(S))$$Then, 
1. **Showing $\tilde{E}_{S}$ is a resolution of identity**:
   We have $\tilde{E}_{S}(\varnothing)=E_{S}(\varnothing)=0$, $\tilde{E}_{S}(\mathbb{C})=E_{S}(\text{Sp}(S))=\text{id}_{\mathcal{H}}$. For any $\omega \in \mathcal{B}_{\mathbb{C}}$, $\tilde{E}_{S}(\omega)$ is a self-adjoint projection by definition. Then, $$\tilde{E}_{S}(\omega_{1}\cap\omega_{2})=E_{S}(\omega_{1}\cap \text{Sp}(S)\cap\omega_{2}\cap \text{Sp}(S))=E_{S}(\omega_{1}\cap \text{Sp}(S))E_{S}(\omega_{2}\cap \text{Sp}(S))=\tilde{E}_{S}(\omega_{1})\tilde{E}_{S}(\omega_{2})$$Further, for $\omega_{1}\sqcup \omega_{2}$, $$\tilde{E}_{S}(\omega_{1}\sqcup\omega_{2})=E_{S}((\omega_{1}\cap\text{Sp}(S))\sqcup(\omega_{2}\cap\text{Sp}(S))  )=\tilde{E}_{S}(\omega_{1})+\tilde{E}_{S}(\omega_{2})$$The last property is inherited from $E_{S}$ as well. Then, $$S=\int_{\text{Sp}(S)}^{} \xi \, dE_{S}(\xi)=\int_{\text{Sp}(S)}^{} \xi \, d\tilde{E}_{S}(\xi)=\int_{f(\text{Sp}(T))}^{} \xi \, d\tilde{E}_{S}(\xi)  $$
2. **Pushforward of $E_{T}$**: We have: $$\int_{f(\text{Sp}(T))}\xi  \, dE_{T}(f^{-1}(\xi))=\int_{\text{Sp}(T)}^{}  f(\lambda) \, dE_{T}(\lambda) =S=\int_{f(\text{Sp}(T))}^{} \xi \, d\tilde{E}_{S}(\xi)   $$Then, we get the result that for $p\in \mathbb{C}[X,Y]$, $$\int_{f(\text{Sp}(T))}p(\xi,\overline{\xi}) \, dE_{T}(f^{-1}(\xi))=p(S,S^{*})=\int_{f(\text{Sp}(T))}p(\xi,\overline{\xi}) \, d\tilde{E}_{S}(\xi)  $$As $\xi\mapsto p(\xi,\tilde{\xi})$ is dense in $C(f(\text{Sp}(T)))$, $$\int_{f(\text{Sp}(T))}^{} g(\xi) \, dE_{T}(f^{-1}(\xi))=g(S)=\int_{f(\text{Sp}(T))} g(\xi) \, d\tilde{E}_{S}(\xi), \quad \forall g\in C(f(\text{Sp}(T)))  $$which implies that $E_{T}(f^{-1}(\xi))$
---
Let $\lambda_{0}\in \text{Sp}(T)$. Then, $SE_{T}(\lambda_{0})=(f\cdot \chi_{\{ \lambda_{0} \}})(T)$ and: $$\begin{align}\braket{ SE_{T}(\lambda_{0})x , y } &=\int_{\text{Sp}(T)}^{} f(\lambda)\chi_{\{ \lambda_{0} \}}(\lambda) \, dE^T_{x,y}(\lambda)\\&= f(\lambda_{0})E^T_{x,y}(\lambda_{0})\\&= f(\lambda_{0})\braket{ E^T(\lambda_{0}) x,  y} \end{align}$$Therefore, $(S-f(\lambda_{0})\text{id}_{\mathcal{H}})E_{T}(\lambda_{0})=0$ and $$\text{ker}(T-\lambda_{0}\text{id}_{\mathcal{H}})=\text{Im }E_{T}(\lambda_{0})\subseteq \text{ker}(S-f(\lambda_{0})\text{id}_{\mathcal{H}})$$

---
Let $x\in \text{ker}(S-f(\lambda_{0})\text{id}_{\mathcal{H}})$. Then, $Sx=f(\lambda_{0})x$ and $S^{*}x=\overline{f(\lambda_{0})}x$. Therefore, $$p(S,S^{*})=p(f(\lambda_{0}),\overline{f(\lambda_{0})})x$$For all $g\in C(\text{Sp}(T))$, $g$

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
