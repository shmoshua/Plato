#Definition #FunctionalAnalysis 

For $T\in \mathcal{B}(\mathcal{H})$, we have that: $$\begin{align}\braket{ T(x+y) , x+y } -\braket{ Tx , x } -\braket{ Ty , y } &=\braket{ Tx , y } +\braket{ x , Ty }\\\braket{ T(x+iy) , x+iy } -\braket{ Tx , x } -\braket{ Ty , y } &=-i\braket{ Tx , y } +i\braket{ Ty, x } \end{align}$$This gives us a formula for $\braket{ Tx , y }$ as a combination of $G$ diagonal coefficients. 

---
##### Properties
> [!lemma] Proposition 1
> For a Hilbert space operator $T\in \mathcal{B}(\mathcal{H})$, $T$ is normal if and only if $\left\| T^{*}x \right\|=\left\| Tx \right\|$ for all $x\in \mathcal{H}$. If $T$ is normal, we then have:
> 1. $\text{ker }T=\text{ker }T^{*}$
> 2. $\text{ker }T=0$ if and only if $\overline{T(\mathcal{H})}=\mathcal{H}$
> 3. $T$ is invertible if and only if there exists $c>0$ s.t. $\left\| Tx \right\|\geq c\|x\|$ for all $x\in \mathcal{H}$.
> 4. if $Tx=\alpha x$ for some $x\in \mathcal{H}$, then $T^{*}x=\overline{\alpha}x$.
> 5. if $\alpha\neq\beta$, then the $\alpha$-eigenspace of $T$ is orthogonal to the $\beta$-eigenspace.

> [!proof]+
> We have that: $$T^{*}T=TT^{*} \iff \braket{ TT^{*}x , x } =\braket{ T^{*}Tx ,x  } ,\quad \forall x\in \mathcal{H} \iff$$
