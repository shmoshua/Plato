#Definition #FunctionalAnalysis 

For $T\in \mathcal{B}(\mathcal{H})$, we have that: $$\begin{align}\braket{ T(x+y) , x+y } -\braket{ Tx , x } -\braket{ Ty , y } &=\braket{ Tx , y } +\braket{ x , Ty }\\\braket{ T(x+iy) , x+iy } -\braket{ Tx , x } -\braket{ Ty , y } &=-i\braket{ Tx , y } +i\braket{ Ty, x } \end{align}$$This gives us a formula for $\braket{ Tx , y }$ as a combination of $G$ diagonal coefficients. 

---
##### Properties
> [!lemma] Proposition 1
> For a [[Hilbert space]] operator $T\in \mathcal{B}(\mathcal{H})$, $T$ is normal if and only if $\left\| T^{*}x \right\|=\left\| Tx \right\|$ for all $x\in \mathcal{H}$. If $T$ is normal, we then have:
> 1. $\text{ker }T=\text{ker }T^{*}$
> 2. $\text{ker }T=(\overline{\text{Im }T})^{\bot}$. In particular, $\text{ker }T=0$ if and only if $\overline{T(\mathcal{H})}=\mathcal{H}$
> 3. $T$ is invertible if and only if there exists $c>0$ s.t. $\left\| Tx \right\|\geq c\|x\|$ for all $x\in \mathcal{H}$.
> 4. if $Tx=\alpha x$ for some $x\in \mathcal{H}$, then $T^{*}x=\overline{\alpha}x$.
> 5. if $\alpha\neq\beta$, then the $\alpha$-eigenspace of $T$ is orthogonal to the $\beta$-eigenspace.

> [!proof]-
> We have that: $$T^{*}T=TT^{*} \iff \braket{ TT^{*}x , x } =\braket{ T^{*}Tx ,x  } ,\quad \forall x\in \mathcal{H} \iff \left\| T^{*}x \right\| ^{2}=\left\| Tx \right\| ^{2},\quad \forall x\in \mathcal{H}$$
> Then, 
> 1. teehee
> 2. We have: $\text{ker }T=\text{ker }T^{*}=(\overline{\text{Im }T})^{\bot}$. In particular, $\text{ker }T=0$ if and only if $(\overline{\text{Im }T})^{\bot}=0$.
> 3. (=>): Follows from the [[Bounded Linear Map|Open mapping theorem]]. Conversely, we have that $\text{ker }T=0$ and $\overline{\text{Im }T}=\mathcal{H}$, but $\text{Im }T$ is closed. Therefore, $\text{Im }T=\mathcal{H}$.
> 4. $\text{ker}(T-\alpha \text{id})=\text{ker}(T^{*}-\overline{\alpha}\text{id})$.
> 5. Let $Tx=\alpha x$ and $Ty=\beta y$. Then, $$\alpha \braket{ x , y } =\braket{ Tx , y } =\braket{ x , T^{*}y } =\braket{ x , \overline{\beta}y } =\beta \braket{ x , y } $$However, as $\alpha\neq\beta$, $\braket{ x , y }=0$.
---
> [!lemma] Proposition 2
> For a projection $P\in \mathcal{B}(\mathcal{H})$, the following are equivalent:
> 1. $P$ is self-adjoint.
> 2. $P$ is normal.
> 3. $\text{Im }P=(\text{ker }P)^{\bot}$
> 4. $\braket{ Px , x }=\left\| Px \right\|^{2}$ for all $x\in \mathcal{H}$

> [!proof]-
> We have: 
> - (1=>2): Obvious.
> - (2=>3): It suffices to show that $\text{Im }P$ is closed. If $y\in \text{Im }P$, then there exists $x\in \mathcal{H}$ s.t. $y=Px$. Then, $Py=P^{2}x=Px=y$. Conversely, if $Py=y$, then $y\in \text{Im }P$. Therefore, $$\text{Im }P=\text{ker}(P-\text{id})$$which is always closed.
> - (3=>4): We have $\text{Im }P\oplus \text{ker }P=\mathcal{H}$. Therefore, for any $x\in \mathcal{H}$, there exists $y\in \text{Im }P$ and $z\in \text{ker } P$ s.t. $x=y+z$. Therefore, $$\braket{ Px , x } =\braket{ y , y+z } =\braket{ y , y } =\braket{ Px , Px } =\left\| Px \right\| ^{2}$$
> - (4=>1): As $\braket{ Px , x }=\left\| Px \right\|^{2}\in \mathbb{R}$, $$\braket{ Px , x } =\braket{ x , Px } =\braket{ P^{*}x , x } $$for all $x\in \mathcal{H}$.
---
> [!lemma] Proposition 3
> Let $P,Q\in \mathcal{B}(\mathcal{H})$ be self-adjoint projections. Then, $$\text{Im }P\ \bot\ \text{Im }Q\iff PQ=0$$

> [!proof]-
> We have: $$\begin{align}PQ=0 &\iff \braket{ PQx , y } =0,\forall x,y\in \mathcal{H}\\&\iff\braket{Qx  ,Py  }=0,\forall x,y\in \mathcal{H}\\&\iff \text{Im }P\ \bot\ \text{Im }Q\end{align}$$
---
##### Examples
> [!h] Example 1(Projection)
> $P\in \mathcal{B}(\mathcal{H})$ is a ***projection*** if $P^{2}=P$.
---
> [!h] Example 2
> $T: \ell^{2}(\mathbb{Z})\to \ell^{2}(\mathbb{Z})$ then
>1. $Tf(x)=f(x+1)$
>2. $T^{*}f(x)=f(x-1)$
>3. $T$ is unitary
>4. $\text{Sp}_{\mathcal{B}(\ell^2(\mathbb{Z}))}T\subseteq \mathbb{T}$ by [[C*-Algebra|Proposition 5]]. Assume that there exists $\mu\in \mathbb{T}$ s.t. $\mu\notin \text{Sp }T$. Then, $(T-\mu \cdot\text{id})^{-1}$ exists. Let us define $\mu_{n}:=\left( 1+\frac{1}{n} \right)\mu$. Then, $$(T-\mu_{n}\cdot \text{id})^{-1}=\left( \mu_{n}\left[ \frac{T}{\mu_{n}}-\text{id} \right] \right) ^{-1}$$So, $$\lim_{ \mu_{n}\to \mu } \left( \text{id}+\frac{T}{\mu_{n}}+\frac{T^{2}}{\mu_{n}^{2}}+\dots \right)\delta_{1}=(T-\mu \cdot \text{id})^{-1}\delta_{1}$$Then, $$\left\| \delta_{1}+ \frac{1}{\mu_{n}}\delta_{2}+ \frac{1}{\mu_{n}^{2}}\delta_{3} +\dots\right\| ^{2}=1+\frac{1}{\left| \mu_{n} \right| ^{2}}+ \frac{1}{\left| \mu_{n} \right| ^{3}}+\dots\to +\infty$$which is a contradiction.