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
1. Let $\lambda\in \text{ess im }f$. Then, $\left| \lambda \right|\leq \left\| f \right\|_{\infty}=\text{inf}\{ t\geq 0: E_{T}(f^{-1}(\{ \left| z \right|>t \}))=0 \}$
2. Let $\alpha\notin \text{Sp}(S)$. Then, $S-\alpha \text{id}_{\mathcal{H}}$ is invertible. 
	- There exists $c>0$ s.t. $\|(S-\alpha \text{id}_{\mathcal{H}})x\|\geq c\|x\|$ for all $x\in\mathcal{H}$.$$E_{T}(f^{-1}(\{ \left| z \right| >\left| \alpha \right|  \}))$$