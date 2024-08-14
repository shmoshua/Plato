#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a commutative [[Banach Algebra]]. 
> 1. A ***character*** of $A$ is a non-trivial [[C-Algebra|$\mathbb{C}$-algebra]] homomorphism $\chi:A\to \mathbb{C}$. 
> 2. the ***Guelfand spectrum*** $\widehat{A}$ of $A$ is defined as the set of characters of $A$.

- **Remark**: Given any $\mathbb{C}$-algebra homomorphism $\varphi:A\to \mathbb{C}$, we can define: $$\begin{array}{cccc} {\varphi_{I}:}&{A\times \mathbb{C}}&\to&{\mathbb{C}}\\&{(x,\lambda)} &\mapsto & {\varphi(x)+\lambda} \end{array}{}$$Then, $\widehat{A_{I}}=\{ \varphi_{I}:\varphi\in \widehat{A} \}\cup \{ \varphi_{\infty} \}$ where $\varphi_{\infty}(x,\lambda)=\lambda$. One also often denotes $\widehat{A_{I}}=\widehat{A}\cup \{ \varphi_\infty \}$.
- **Related definition**: From Proposition 2, $\widehat{A}\subseteq A^*$ and $\widehat{A}$ can be equipped with the  [[Weak Topology|weak*-topology]] on $A^{*}$, called the ***Guelfand topology***. (cf. Theorem 4)
---
##### Properties
> [!lemma] Proposition 1
> Let $\chi\in \widehat{A}$ be a character. Then, 
> 1. $\chi(A)=\mathbb{C}$. 
> 2. If $A$ is unital, $\chi(e)=1$.

> [!proof]-
> We have:
> 1. As $\chi$ is a $\mathbb{C}$-algebra homomorphism, $\chi(A)$ is a $\mathbb{C}$-vector subspace of $\mathbb{C}$ which is $(0)$ or $\mathbb{C}$. But $\chi$ is non-trivial by definition. 
> 2. Let $A$ be unital. For all $\lambda\in \mathbb{C}$, there exists $x\in A$ s.t. $\chi(x)=\lambda$. Therefore, $$\chi(e)\lambda=\chi(e)\chi(x)=\chi(ex)=\chi(x)=\lambda$$
---
> [!lemma] Proposition 2
> For every $\varphi\in \widehat{A}$ we have
> 1. $\left| \varphi(x) \right| \leq\|x\|_{\text{sp}}$ for all $x\in A$.
> 2. $\varphi\in A^{*}$ with $\left\| \varphi \right\|\leq 1$ with equality if $A$ is unital with $\|e\|=1$ for the unit.

> [!proof]-
> First, by the remark, we may assume that $A$ is unital. If $\left| \lambda \right|>\|x\|_{\text{sp}}$, then there exists $y\in A$ s.t. $(x-\lambda e)y=e$. Therefore, $$\varphi(y)\varphi(x-\lambda e)=\varphi(e)=1$$Indeed $\varphi(x-\lambda e)\neq 0$ and $\varphi(x)\neq\lambda$. Therefore, $\left| \varphi(x) \right|\leq\|x\|_{\text{sp}}$. 
> 
> Further, as $\|x\|_{\text{sp}}\leq\|x\|$, $\left\| \varphi \right\|\leq 1$. If $\|e\|=1$, then since $\varphi(e)=1=\|e\|$, $\|\varphi\|=1$.
---
> [!lemma] Theorem 3
> Let $A$ be a commutative [[Banach Algebra]]. Then, 
> $$\widehat{A}\to \text{Max}(A):=\{ I\subseteq A :I \text{ regular maximal ideal}\},\quad \varphi\mapsto \text{ker }\varphi$$is a bijection.

> [!proof]-
> We have:
> 1. **Showing that $\text{ker }\varphi$ is a regular maximal ideal**: 
>    Let $\varphi\in \widehat{A}$. Then, $\varphi:A\to \mathbb{C}$ is a non-trivial $\mathbb{C}$-algebra homomorphism. Hence, $\text{ker }\varphi$ is a proper ideal. Further, $\varphi(A)=\mathbb{C}$ and therefore there exists $u\in A$ with $\varphi(u)=1$. Then, for all $x\in A$, $ux-x\in \text{ker }\varphi$ which shows that $\text{ker }\varphi$ is regular. Lastly, since $A / \text{ker}(\varphi)\cong \mathbb{C}$, $\text{ker}(\varphi)$ is maximal.
>  2. **Showing injectivity**: 
>     Assume $I:=\text{ker }\varphi_{1}=\text{ker }\varphi_{2}$ and let $u\in A$ be a unit modulo $I$. Clearly, $u\notin I$ by [[Regular Ideal|Proposition 1]] and since $I$ has codimension 1 in $A$, $A=\mathbb{C}u+I$. As, $\varphi_{1}(u)=\varphi_{2}(u)=1$, it follows that: $$\varphi_{1}(\lambda u+v)=\lambda\varphi_{1}(u)=\lambda=\lambda(\varphi_{2}(u))=\varphi_{2}(\lambda u+v)$$
>  3. **Showing surjectivity**:
> 	Let $I\subsetneq A$ be maximal regular. By [[Regular Ideal|Corollary 3.2]], $I$ is closed. Then, by [[Banach Algebra|Proposition 3]], $A / I$ is a Banach algebra and $\pi:A \to A / I$ is a Banach algebra homomorphism. And $A / I$ is a unital banach algebra from the definition of regular ideals. 
> 	
> 	Now, since $I$ is maximal every $x+I\neq I$ in $A / I$ is invertible. Indeed otherwise, if $x+I \neq I$, where not invertible, $J:=(x+I)A / I\subsetneq A / I$. Then, $$I\subsetneq \pi ^{-1}(J)\subsetneq A$$ corresponding the maximality of $I$.
> 
> 	Therefore, by Guelfand-Mazur, $A / I\xrightarrow{\sim}\mathbb{C}$. Now, composing $A\xrightarrow{\pi}A / I\xrightarrow{\sim}\mathbb{C}$, we get a $\mathbb{C}$-algebra homomorphism $\varphi:A\to C$ with $\text{ker }\varphi=I$.
---
> [!lemma] Theorem 4 (Guelfand Topology)
> Let $A$ be a commutative [[Banach Algebra|Banach algebra]]. Then, we have: 
> 1. $\widehat{A}$ is locally compact Hausdorff w.r.t. Guelfand topology.
> 2. If $A$ is unital, $\widehat{A}$ is compact.
> 3. If $A$ is non-unital, $\widehat{A_{I}}$ is the [[one-point compactification]] of $\widehat{A}$.

^a2c505

> [!proof]-
> We have:
> 1. As an open subspace of a compact Hausdorff space is locally compact Hausdorff by [[Compact Space|Compact Hausdorff Space Proposition 2]], we aim to show that $\widehat{A}$ is open in some compact Hausdorff space.
>    
>    We check that $\Omega:=\widehat{A}\cup \{ 0 \}\subseteq B_{\leq 1}^{A^{*}}(0)$ is weak\*-closed. Let $\varphi\in \overline{\Omega}$. Then, for a convergent net $\{ \varphi_{i} \}_{i\in I}$ converging to $\varphi$, we have that: $$\varphi(xy)=\lim \varphi_{i}(xy)=\lim \varphi_{i}(x)\varphi_{i}(y)=\varphi(x)\varphi(y) $$Hence $\varphi\in \Omega$ and $\Omega$ is closed in $B_{\leq 1}^{A^{*}}(0)$, which is a weak\*-compact set by [[Weak Topology|Banach Alagolu]].  As $\Omega$ is Hausdorff, $\{ 0 \}$ is closed and $\widehat{A}$ is an open subspace of a weak\*-compact set, which shows that $\widehat{A}$ is locally compact Hausdorff.
> 2. If $A$ is unital, then: $$\begin{align}\widehat{A}&:=\{ \varphi\in B_{\leq 1}^{A^{*}}(0):\varphi(xy)=\varphi(x)\varphi(y),\varphi(e)=1,\quad \forall x,y\in A\}\\&=\{\varphi\in B_{\leq 1}^{A^{*}}(0):\varphi(e)=1 \}\cap\bigcap_{x,y\in A}^{}\{ \varphi\in B_{\leq 1}^{A^{*}}(0):\varphi(xy)=\varphi(x)\varphi(y)\}\end{align}$$which is weak\*-closed in $B_{\leq 1}^{A^{*}}(0)$. Hence, it is weak\*-compact.
> 3. By the identification $\widehat{A_{I}}=\widehat{A}\cup \{ \varphi_{\infty} \}$ and the fact that $\widehat{A_{I}}$ is compact Hausdorff and $\widehat{A}$ is locally compact Hausdorff, we get that $\widehat{A_{I}}$ is the one-point compactification of $\widehat{A}$.



---
> [!lemma] Theorem 5 (Spectral Theorem)
> Let $A\subseteq \mathcal{B}(\mathcal{H})$ be an commutative sub-$C^{*}$-algebra containing $\text{id}_{\mathcal{H}}$. Then, 
> 1. there exists a unique [[resolution of Identity]] $E$ on $\mathcal{B}_{\widehat{A}}$ s.t. for every $T\in A$,$$T=\int_{\widehat{A}}\widehat{T}  \, dE $$where $\widehat{T}\in C(\widehat{A})$ is the [[Guelfand transform]] of $T$. This is equivalent to: $$\braket{ T(x) , y } =\int_{\widehat{A}}\widehat{T}  \, dE_{x,y},\quad \forall x,y\in \mathcal{H} $$
> 2. the inverse $C(\widehat{A})\to A$ of the Guelfand transform extends to an isometric $C^{*}$-algebra isomorphism $\Psi:L^\infty(E)\to B$ where $B\supseteq A$ is a sub-$C^{*}$-algebra of $\mathcal{B}(\mathcal{H})$ and given by $$\Psi(f):=\int_{\widehat{A}}f \, dE,\quad \forall f\in L^\infty(E)$$Specifically, $B:= \overline{\text{Span}\{ E(\omega):\omega\in \mathcal{B}_{\widehat{A}} \}}$.
> 3. if $\omega \subseteq \widehat{A}$ is non-empty and open, then $E(\omega)\neq 0$.
> 4. an operator $S\in \mathcal{B}(\mathcal{H})$ commutes with $A$ if and only if $S$ commutes with $E(\mathcal{B}_{\widehat{A}})$.

> [!proof]-
> > [!lemma] 
> > Let $f:\mathcal{H}\times \mathcal{H}\to \mathbb{C}$ be a sesquilinear, bounded form in the sense that: $$M:=\sup_{\|x\|=\left\| y \right\| =1}\left| f(x,y) \right| <+\infty$$Then, 
> > 1. there exists a unique $T\in \mathcal{B}(\mathcal{H})$ s.t. $f(x,y)=\braket{ Tx , y }$ for all $x,y\in \mathcal{H}$.
> > 2. $\left\| T \right\|=M$.
>     
> > [!proof]-
> > Let $x,y\in \mathcal{H}$. Then, we have: $$\left| f\left( \frac{x}{\|x\|}, \frac{y}{\left\| y \right\| } \right) \right|\leq M $$and $\left| f(x,y) \right|\leq M\|x\|\|y\|$. Further, for any $y\in \mathcal{H}$, $x\mapsto f(x,y)$ is a bounded continuous linear map, i.e. it is a map in $\mathcal{H}^{*}$. Hence, by [[Hilbert Space|Riesz representation]], there exists $S(y)\in \mathcal{H}$ s.t. $f(x,y)=\braket{ x , S(y) }$.
> > 
> > Further, $S$ is continuous and bounded as $f$ is sesquilinear. We get $T:=S^{*}$ and lastly: $$\left\| S \right\| =\sup_{\left\| y \right\| =1}\left\| Sy \right\| =\sup_{\|x\|=\|y\|=1 }\left| \braket{ x , Sy }  \right| =\sup_{\|x\|=\|y\|=1 }\left| f(x,y) \right|=M $$
> 
> We have:
> 1. This is done in the following steps:
> 	1. **Constructing the resolution of identity**:
> 	   Let $\gamma:C(\widehat{A})\to A$ be the $C^{*}$-algebra isomorphism. Then, pick $x\in \mathcal{H}$ and consider $$C(\widehat{A})\to \mathbb{C},\quad f\mapsto \braket{ \gamma(f)x , x } $$which is a linear functional on $C(\widehat{A})$. Moreover, if $f\geq 0$ and $h:=\sqrt{ f }$, then $f=\overline{h}h$ and $\gamma(f)=\gamma(h)^{*}\gamma(h)$ from which it follows that: $$\braket{ \gamma(f)x , x } =\braket{ \gamma(h)^{*}\gamma(h)x , x } =\left\| \gamma(h)x \right\| ^{2}\geq 0$$Then, by [[Measure Theory/Complex Measure|Riesz]] there exists a positive Borel regular measure $E_{x,x}$ on $\widehat{A}$ s.t. $$\braket{ Tx , x } =\int_{\widehat{A}}\widehat{T}  \, dE_{x,x},\quad \forall T\in A,x\in \mathcal{H} $$Now define by polarization: $$E_{x,y}:=\frac{1}{2}\left( E_{x+y,x+y}+iE_{x+iy,x+iy}-(1+i)E_{x,x}-(1+i)E_{y,y} \right) $$Then, we get that: $$\begin{align}\int_{\widehat{A}}\widehat{T}  \, dE_{x,y}&=\frac{1}{2}\left( \braket{ Tx+Ty , x+y } +i\braket{ Tx+iTy , x+iy } -(1+i)\braket{ Tx , x } -(1+i)\braket{ Ty , y }  \right) \\&= \frac{1}{2}(\braket{ Tx , y } +\braket{ Ty , x } +\braket{ Tx , y }-\braket{ Ty ,  x}  )\\&=\braket{ Tx , y } \end{align} $$
> 	2. **Showing the sesquilinearity**:
> 	   Now, for any $f\in C(\widehat{A})$, we have that: $(x,y)\mapsto \int_{\widehat{A}}^{} f \, dE_{x,y}$ is sesquilinear. However, by the [[Measure Theory/Complex Measure|complex Riesz]] the complex measure is uniquely defined by their value on $C(\widehat{A})$. Therefore, this holds for any $f\in \mathcal{B}^\infty(\widehat{A})$.
> 	   
>		Now, for any $v\in \mathcal{H}$ and $f\in \mathcal{B}^\infty(\widehat{A})$, $$\left| \int_{\widehat{A}}^{} f \, dE_{v,v}  \right|\leq \left\| f \right\| _{b}\int_{\widehat{A}}^{} 1 \, dE_{v,v} = \left\| f \right\| _{b}\int_{\widehat{A}}^{} \widehat{\text{id}_{\mathcal{H}}} \, dE_{v,v}=\left\| f \right\| _{b}\braket{ v , v }=\left\| f \right\| _{b}\|v\|^{2} $$Therefore, for $\|x\|=\|y\|=1$, $\left| \int_{\widehat{A}}^{} f \, dE_{x,y} \right|$ is bounded and hence by the lemma, there exists a unique $\Phi(f)\in\mathcal{B}(\mathcal{H})$ s.t. $$\int_{\widehat{A}}^{} f \, dE_{x,y}=\braket{ \Phi(f)x , y },\quad \forall f\in \mathcal{B}^\infty(\widehat{A}) $$where we can define $\Phi$ as a function $\mathcal{B}^\infty(\widehat{A})\to \mathcal{B}(\mathcal{H})$. We then define the resolution of identity as: $$E(\omega):=\Phi(\chi_{\omega})$$
>	3. **Showing that $\Phi$ is a linear, multiplicative $C^{*}$-homomorphism**: 
>	   1. **Linear**: We have that for $x,y\in \mathcal{H}$: $$\braket{ \Phi(f+\lambda g)x , y } =\int_{\widehat{A}}^{} f+\lambda g \, dE_{x,y}=\braket{ \Phi(f)x , y } +\lambda\braket{ \Phi(g)x , y } =\braket{ (\Phi(f)+\lambda\Phi(g) )x,y  }  $$
>	   2. **Multiplicative**: Let $S,T\in A$. Then, $\widehat{ST}=\widehat{S}\widehat{T}$. Therefore, $$\int_{\widehat{A}}^{} \widehat{S}\widehat{T} \, dE_{x,y}=\int_{\widehat{A}}^{} \widehat{ST} \, dE_{x,y}=\braket{ S(Tx) , y } =\int_{\widehat{A}}^{} \widehat{S} \, dE_{Tx,y}   $$As $\widehat{T}dE_{x,y}$ and $dE_{Tx,y}$ coincide on all $\widehat{S}\in C(\widehat{A})$, they do on all $f\in \mathcal{B}^\infty(\widehat{A})$. Hence, $$\int_{\widehat{A}}^{} f\widehat{T} \, dE_{x,y}=\int_{\widehat{A}}^{} f \, dE_{Tx,y}=\braket{ \Phi(f)(Tx) , y } =\braket{ Tx , \Phi(f)^{*}y } =\int_{\widehat{A}}^{} \widehat{T} \, dE_{x,\Phi(f)^{*}y}   $$ As $fdE_{x,y}$ and $dE_{x,\Phi(f)^{*}y}$ coincide on all $\widehat{T}\in C(\widehat{A})$, they do on all $g\in \mathcal{B}^\infty(\widehat{A})$. Therefore, $$\braket{ \Phi(fg)x , y } =\int_{\widehat{A}}^{} fg \, dE_{x,y}= \int_{\widehat{A}}^{} g \, dE_{x,\Phi(f)^{*}y}=\braket{ \Phi(g)x , \Phi(f)^{*}y } =\braket{ \Phi(f)\Phi(g)x , y }  $$which shows that $\Phi$ is multiplicative.
>	   3. **$C^{*}$-homomorphism**: We have that $$\braket{ \Phi(f)^{*}x , x }=\braket{ x , \Phi(f)x } =\overline{\braket{ \Phi(f)x , x } }=\overline{\int_{\widehat{A}}^{} f \, dE_{x,x} }=\int_{\widehat{A}}^{} \overline{f} \, dE_{x,x}=\braket{ \Phi(\overline{f})x , x }   $$
>	
>	1. **Checking $E$ is a resolution identity**:
>	   1. $E(\varnothing)=\Phi(0)=0$ and $E(\widehat{A})=\Phi(1)$ where $$\braket{ \Phi(1)x , y } =\int_{\widehat{A}}^{} 1 \, dE_{x,y}=\braket{ \text{id}_{\mathcal{H}}x , y } =\braket{ x , y }  $$Therefore, $E(\widehat{A})=\text{id}_{\mathcal{H}}$.
>	   2. For any $\omega\in \mathcal{B}_{\widehat{A}}$, from the multiplicity:$$E(\omega)^{2}=E(\omega)E(\omega)=\Phi(\chi_{\omega})\Phi(\chi_{\omega})=\Phi(\chi_{\omega})=E(\omega)$$and $$E(\omega)^{*}=\Phi(\chi_{\omega})^{*}=\Phi(\chi_{\omega})=E(\omega)$$Hence, $E$ is a self-adjoint projection.
>	   3. For $\omega_{1},\omega_{2}\in \mathcal{B}_{\widehat{A}}$, $$E(\omega_{1}\cap\omega_{2})=\Phi(\chi_{\omega_{1}\cap\omega_{2}})=\Phi(\chi_{\omega_{1}}\chi_{\omega_{2}})=\Phi(\chi_{\omega_{1}})\Phi(\chi_{\omega_{2}})=E(\omega_{1})E(\omega_{2})$$
>	   4. For $\omega_{1},\omega_{2}\in \mathcal{B}_{\widehat{A}}$ with $\omega_{1}\cap\omega_{2}=\varnothing$, $$E(\omega_{1}\sqcup\omega_{2})=\Phi(\chi_{\omega_{1}}+\chi_{\omega_{2}})=\Phi(\chi_{\omega_{1}})+\Phi(\chi_{\omega_{2}})=E(\omega_{1})+E(\omega_{2})$$
>	   5. For $x,y\in \mathcal{H}$, $$\braket{ E(\omega)x , y } =\braket{ \Phi(\chi_{\omega})x , y } =\int_{\widehat{A}}^{} \chi_{\omega} \, dE_{x,y}=\int_{\omega}^{}  \, dE_{x,y}=E_{x,y}(\omega)  $$which is regular complex by construction.
>	2. **Verifying the Statement**:
>	   Now, by [[Resolution of Identity|Theorem 6]] there exists a $C^{*}$-isomorphism $\Psi:L^\infty(E)\to B\subseteq\mathcal{B}(\mathcal{H})$ s.t. $$\braket{ \Psi(f)x , y } =\int_{\widehat{A}}^{} f \, dE_{x,y}, \quad\forall x,y\in \mathcal{H},f\in L^\infty(E)$$Then, for any $T\in A$, $\braket{ Tx , y } =\int_{\widehat{A}}^{} \widehat{T} \, dE_{x,y}=\braket{ \Psi(\widehat{T})x , y }$ and $$T=\Psi(\widehat{T})=\int_{\widehat{A}}^{} \widehat{T} \, dE $$
>2. Let $\Psi:L^\infty(E)\to \mathcal{B}(\mathcal{H})$ be the isometric $C^{*}$-isomorphism from above. Then, it's left to show that $\Psi$ extends the inverse Guelfand transform. For $\widehat{T}\in C(\widehat{A})$, $$\Psi(\widehat{T})=T$$Further, as for every $f\in L^\infty(E)$ and $\varepsilon>0$ we have a simple function $s=\sum_{i=1}^{n}\alpha_{i}\chi_{\omega_{i}}$ with $\left\| f-s \right\|_{\infty}<\varepsilon$ we have that for any $S=\Psi(f)\in B$, we have that: $$\left\| \Psi(f) -\Psi(s)\right\| =\left\| \Psi(f-s) \right\| =\left\| f-s \right\|_{\infty}<\varepsilon $$ where $\Psi(s)=\sum_{i=1}^{n}\alpha_{i}E(\omega_{i})$. 
>3. Let $\omega \subseteq \widehat{A}$ be open and $E(\omega)=0$. Then, for all $x\in \mathcal{H}$, $E_{x,x}(\omega)=\braket{ E(\omega)x , x }=0$. Hence, for any $T\in A$ s.t. $\text{supp}(\widehat{T})\subseteq \omega$. Then, $$\left\| Tx \right\| ^{2}=\braket{ T^{*}Tx , x } =\int_{\widehat{A}}^{} \widehat{T^{*}T} \, dE_{x,x}=\int_{\widehat{A}}^{} \left| \widehat{T} \right| ^{2} \, dE_{x,x}=0  $$which implies that $T=0$, which implies that $\omega=\varnothing$. 
>4. Follows from the fact that $B:= \overline{\text{Span}\{ E(\omega):\omega\in \mathcal{B}_{\widehat{A}} \}}$.

- **Remark**: $C(\widehat{A})$ injects into $L^\infty(E)$ as follows: If $f\in C(\widehat{A})$ with $\left\| f \right\|_{\infty}=0$, then $$E(f^{-1}(\mathbb{C} \backslash\{ 0 \}))=0$$Therefore, by 3, $f^{-1}(\mathbb{C} \backslash \{ 0 \})=\varnothing$ and $f=0$.
---
> [!lemma] Corollary 6 (Spectral Theorem with a Normal Operator)
> Let $T\in \mathcal{B}(\mathcal{H})$ be normal and $A:=\overline{\{ p(T,T^{*}):p\in \mathbb{C}[X,Y] \}}$. Then, 
> 1. there exists a unique [[resolution of identity]] $E$ on $\text{Sp}(T)$ s.t. $$T=\int_{\text{Sp}(T)}^{} \lambda \, dE(\lambda) $$
> 2. the $C^{*}$-algebra isomorphism  $C(\text{Sp}(T))\to A,f\mapsto f(T)$ extends to an isometric $C^{*}$-algebra isomorphism $\Psi:L^\infty(E)\to B$ where $B\supseteq A$ is a sub-$C^{*}$-algebra of $\mathcal{B}(\mathcal{H})$ given by: $$\Psi(f):=\int_{\text{Sp}(T)}f \, dE,\quad \forall f\in L^\infty(E) $$with $B:=\overline{\text{Span}\{ E(\omega):\omega\in \mathcal{B}_{\text{Sp}(T)} \}}$
> 3. an operator $S\in \mathcal{B}(\mathcal{H})$ commutes with $T$ and $T^{*}$ if and only if $S$ commutes with $E(\mathcal{B}_{\text{Sp}(T)})$.

> [!proof]-
> From the [[C*-Algebra|Pre-spectral theorem]], we have that $\widehat{T}:\widehat{A}\to \text{Sp}(T)$ is a homeomorphism and a $C^{*}$-algebra isomorphism $C(\text{Sp}(T))\to A,f\mapsto f(T)$ s.t. $$\widehat{f(T)}(\varphi)=f(\varphi(T)),\quad \forall \varphi\in\widehat{A}$$Therefore, for any $\lambda\in \text{Sp}(T)$, $$\widehat{f(T)}(\widehat{T}^{-1}(\lambda))=f(\widehat{T}^{-1}(\lambda)(T))=f(\widehat{T}(\widehat{T}^{-1}(\lambda)))=f(\lambda)$$
> 1. From the spectral theorem, let $F$ be the unique resolution of identity on $\widehat{A}$ s.t. for all $S\in A$, $S=\int_{\widehat{A}}^{} \widehat{S} \, dF$. Then, we define a pushforward resolution of identity $E:\mathcal{B}_{\text{Sp}(T)}\to \mathcal{B}(\mathcal{H})$ given as: $$E(\omega)=F(\widehat{T}^{-1}(\omega))$$One can easily verify that $E$ is a resolution of identity. Now, as the $C^{*}$-algebra isomorphism sends $1\mapsto \text{id}_{\mathcal{H}}$ and $\text{id}\mapsto T$, we have that $p(\lambda,\overline{\lambda})\mapsto p(T,T^{*})$. Therefore, $$p(T,T^{*})=\int_{\widehat{A}}^{} \widehat{p(T,T^{*})} \, dF=\int_{\text{Sp}(T)}^{} \widehat{p(T,T^{*})}\circ \widehat{T}^{-1} \, dE=\int_{\text{Sp}(T)}p(\lambda,\overline{\lambda})  \, dE(\lambda)   $$Hence, $T=\int_{\text{Sp}(T)}\lambda \, dE(\lambda)$. 
>    
>    To prove the uniqueness, let $E'$ be another such resolution of identity on $\text{Sp}(T)$. Then, from [[Resolution of Identity|Theorem 6]], we get a $C^{*}$-algebra homomorphism $\Psi':L^\infty(E)\to \mathcal{B}(\mathcal{H})$ and we get that: $$\int_{\text{Sp}(T)}^{} p(\lambda,\overline{\lambda}) \, dE'_{x,y}=p(T,T^{*})=\int_{\text{Sp}(T)}^{} p(\lambda,\overline{\lambda}) \, dE_{x,y}  $$However, as $\lambda\mapsto p(\lambda,\overline{\lambda})$ are dense in $C(\text{Sp}(T))$, we get that the resolutions of identity coincide on the whole $C(\text{Sp}(T))$. This means that $E=E'$.
> 2. 
---
> [!lemma] Corollary
> Let $T\in \mathcal{B}(\mathcal{H})$ be normal, $\lambda_{0}\in \text{Sp}(T)$ and $\mathcal{H}_{\lambda_{0}}:=\text{ker}(T-\lambda_{0}\text{id}_{\mathcal{H}})$. Then, $E(\lambda_{0})=\Pi_{\mathcal{H}_{\lambda_{0}}}$.

> [!proof]-
> We have: $$TE(\lambda_{0})=(\text{id}_{\mathcal{H}}\cdot \chi_{\{ \lambda_{0} \}})(T)$$Therefore, $$\braket{ TE(\lambda_{0})x , y } =\lambda_{0}E_{x,y}(\lambda_{0})=\lambda_{0}\braket{ E(\lambda_{0})x , y } $$This means that $TE(\lambda_{0})-\lambda_{0}E(\lambda_{0})=0$ and $(T-\lambda_{0} \text{id}_{\mathcal{H}})E(\lambda_{0})=0$ and $\text{Im }E(\lambda_{0})\subseteq \text{ker}(T-\lambda_{0}\text{id}_{\mathcal{H}})$. Conversely, let $x\in \mathcal{H}_{\lambda_{0}}$. Then, $Tx=\lambda_{0}x$ and $T^{*}x=\overline{\lambda_{0}}x$. Therefore, for all $p\in \mathbb{C}[X,Y]$, $$p(T,T^{*})x=p(\lambda,\overline{\lambda})x$$As $\{ \lambda\mapsto p(\lambda,\overline{\lambda}):p\in \mathbb{C}[X,Y] \}$ is dense in $C(\text{Sp}(T))$, for all $C\in \text{Sp}(T)$, $f(T)x=f(\lambda_{0})x$. This implies: $$\braket{ f(T)x , y } =\int_{\text{Sp}(T)}^{} f(\lambda) \, dE_{x,y}(\lambda) $$Therefore, $E_{x,y}=\braket{ x , y }\delta_{\lambda_{0}}$ and $\braket{ E(\lambda_{0})x , y }=E_{x,y}(\lambda_{0})=\braket{ x , y }$ for all $y\in \mathcal{H}$. Therefore, $E(\{ \lambda_{0} \})x=x$ and $\mathcal{H}_{\lambda_{0}}\subseteq \text{Im }E(\lambda_{0})$.
---
##### Examples
> [!h] Example 1
> Let $X$ be a [[locally compact Hausdorff space]]. Then, $$\begin{array}{cccc} {}&{X}&\to&{\widehat{C_{0}(X)}}\\&{x} &\mapsto & {\text{ev}(x)} \end{array}{}$$is a bijection.
---
> [!h] Example 2
> We have $\widehat{\ell^\infty(\mathbb{N})}\cong\{ \text{Ultra}(\mathbb{N}) \}$, i.e. the ultrafilters on $\mathbb{N}$.
---