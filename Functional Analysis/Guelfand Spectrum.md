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
> 2. the inverse $C(\widehat{A})\to A$ of the Guelfand transform extends to an isometric $C^{*}$-algebra isomorphism $\Psi:L^\infty(E)\to B$ where $B\supseteq A$ is a sub-$C^{*}$-algebra of $\mathcal{B}(\mathcal{H})$ and given by $$\Psi(f):=\int_{\widehat{A}}f \, dE,\quad \forall f\in L^\infty(E)$$Specifically, $B:= \overline{\Psi(\mathcal{S}(\widehat{A}))}$.
> 3. if $\omega \subseteq \widehat{A}$ is non-empty and open, then $E(\omega)\neq 0$.
> 4. an operator $S\in \mathcal{B}(\mathcal{H})$ commutes with $A$ if and only if $S$ commutes with $E(\mathcal{B}_{\widehat{A}})$.

> [!proof]+
> > [!lemma] 
> > Let $f:\mathcal{H}\times \mathcal{H}\to \mathbb{C}$ be a sesquilinear, bounded form in the sense that: $$M:=\sup_{\|x\|=\left\| y \right\| =1}\left| f(x,y) \right| <+\infty$$Then, 
> > 1. there exists a unique $T\in \mathcal{B}(\mathcal{H})$ s.t. $f(x,y)=\braket{ Tx , y }$ for all $x,y\in \mathcal{H}$.
> > 2. $\left\| T \right\|=M$.
> 
> From [[Resolution of Identity|Theorem 6]] we have a unique $\Phi(f)\in \mathcal{B}(\mathcal{H})$ s.t. $\int_{\widehat{A}}^{} f \, dE_{x,y}=\braket{ \Phi(f)x , y }$ for all $x,y\in \mathcal{H}$ with the characteristics:
> 1. $\Phi:\mathcal{B}^\infty(\widehat{A})\to \mathcal{B}(\mathcal{H})$ is linear.
> 2. the diagram in 2 commutes
> 3. $\Phi(f)^{*}=\Phi(\overline{f})$ for all $f\in \mathcal{B}^\infty(\widehat{A})$.
> 4. $\Phi(fg)=\Phi(f)\Phi(g)$
>
> Then, we can define the following resolution of identity: $E:\omega\mapsto \Phi(\chi_{\omega})$.
> 1. **Showing $E$ is a resolution of identity**:
> 	We have $E(\varnothing)=\Phi(0)=0$ as $\Phi$ is linear. Similarly, $E(\widehat{A})=\Phi(1)$. Consider $T=\text{id}_{\mathcal{H}}$. Then, $$\widehat{T}(\chi)=\chi(\text{id}_{\mathcal{H}})=1,\quad \forall \chi\in \widehat{A}$$Therefore, $$\braket{ x , y } =\braket{ \text{id}_{\mathcal{H}}(x) , y } =\int_{\widehat{A}}^{} 1 \, dE_{x,y}=\braket{ \Phi(1)x ,y  }  $$This shows that $E(\widehat{A})=\Phi(1)=\text{id}_{\mathcal{H}}$.
> 	
> 	We now have that: $$E(\omega)=\Phi(\chi_{\omega})=\Phi(\chi^{2}_{\omega})=\Phi(\chi_{\omega})\Phi(\chi_{\omega})=E(\omega)E(\omega)=E(\omega^{2})$$and $$E(\omega)^{*}=\Phi(\chi_{\omega})^{*}=\Phi(\chi_{\omega})=E(\omega)$$therefore $E(\omega)$ is normal and by [[Hilbert Space Operator|Proposition 2]], $E(\omega)$ is a self-adjoint projection,
> 	
> 	Now, $$E(\omega_{1}\cap\omega_{2})=\Phi(\chi_{\omega_{1}\cap\omega_{2}})=\Phi(\chi_{\omega_{1}})\Phi(\chi_{\omega_{2}})=\Phi(\chi_{\omega_{1}})\Phi(\chi_{\omega_{2}})=E(\omega_{1})E(\omega_{2})$$
> 	and for $\omega_{1}\sqcup \omega_{2}$, $$E(\omega_{1}\sqcup \omega_{2})=\Phi(\chi_{\omega_{1}}+\chi_{\omega_{2}})=\Phi(\chi_{\omega_{1}})+\Phi(\chi_{\omega_{2}})=E(\omega_{1})+E(\omega_{2})$$
> 		Lastly, $$\braket{ E(\omega)x , y } =\braket{ \Phi(\chi_{\omega})x , y } =\int_{\widehat{A}}^{} \chi_{\omega} \, dF_{x,y} =\int_{\omega}^{}  \, dF_{x,y}=E_{x,y}(\omega) $$
> 
> Recall that $\Psi$ was defined first on simple functions $s=\sum_{i}^{}\alpha_{i}\chi_{\omega_{i}}$ by $\Psi(s)=\sum_{i}\alpha_{i}E(\omega_{i})$. This gives a $C^{*}$-algebra map $\mathcal{S}(\widehat{A})\to \mathcal{B}(\mathcal{H})$ with $\left\| \Psi(s) \right\|=\|s\|_{\infty}$ This extends to $\mathcal{B}^\infty(\widehat{A})\to \mathcal{B}(\mathcal{H})$ and by factoring $L^\infty(E)\to \mathcal{B}(\mathcal{H})$.
> 
> But we also have $\Phi(s)=\sum_{i}^{}\alpha_{i}\Phi(\chi_{\omega_{i}})=\sum_{i}^{}\alpha_{i}E(\omega_{i})$. As $\mathcal{S}(\widehat{A})$ is dense in $\mathcal{B}^\infty(\widehat{A})$, $\Phi=\Psi$
> 
> We further show that $C(\widehat{A})\to L^\infty(E)$ is a norm-preserving injection. Let $\omega \subseteq \widehat{A}$ be non-empty open and $T\in A$ s.t. $\text{supp}(\widehat{T})\subseteq\omega$. Then, $$\left\| T (x)\right\|^{2}=\braket{ T(x) , T(x) } =\braket{ T^{*}T(x),x } =\int_{\widehat{A}}^{} \widehat{T^{*}T} \, dE_{x,x}=\int_{\widehat{A}}^{} \left| \widehat{T} \right| ^{2} \, dE_{x,x}=\int_{\omega}\left| \widehat{T} \right| ^{2} \, dE_{x,x}    $$ If $E(\omega)=0$, then for all $x\in \mathcal{H}$, $E_{x,x}(\omega)=\braket{ E(\omega)x , x }=0$ Hence, $$\left\| Tx \right\| ^{2}=\int_{\omega}^{} \left| \widehat{T} \right| ^{2} \, dE_{x,x}=0 $$Therefore, $T=0$ and $\widehat{T}=0$. So $C_{00}(\omega)=(0)$ but $\omega\neq \varnothing$ and this is a contradiction./
> 
> Let $f\in C(\widehat{A})$ and we claim $\text{im }f=\text{ess im}(f)$. Let $(D_{n})_{n}$ be a countable open cover of $\mathbb{C}$ and assume $D_{n}\cap \text{im }f=\varnothing$. Then, $f^{-1}(D_{n})=\varnothing$ and $E(f^{-1}(D_{n}))=0$. Therefore,$$D_{n}\subseteq \text{ess im}(f)=\varnothing$$Now, let $D_{n}\subseteq \mathbb{C}$ s.t. $D_{n}\cap \text{ess im}(f)=\varnothing$. Then, $E(f^{-1}(D_{n}))=0$. But as $D_n$ is open and $f$ is continuous, $f^{-1}(D_{n})$ is open and $f^{-1}(D_{n})=\varnothing$. Therefore, $D_{n}\cap \text{im}(f)=\varnothing$. In other words, for $f\in C(\widehat{A})$, $$\left\| f \right\| _{\infty}=\left\| f \right\| $$
> 
> Lastly, if $S$ commutes with $E(\omega)$ for all $\omega\in \mathcal{B}_{\widehat{A}}$, then it does with the simple functions $\mathcal{S}(\widehat{A})$ and the closure $B\supseteq A$.
> 
> Conversely, assume that $ST=TS$ for all $T\in A$. Then, $$\int_{\widehat{A}}^{} \widehat{T} \, dE_{S(x),y}= \braket{ TS(x) , y } =\braket{ ST(x) , y } =\braket{ T(x) , S^{*}(y) }=\int_{\widehat{A}}^{} \widehat{T} \, dE_{x,S^{*}(y)}  $$Therefore, $E_{S(x),y}$ and $E_{x,S^{*}(y)}$ represent the same linear form on $C(\widehat{A})$. Therefore, they coincide. Then, $$\braket{ E(\omega)S(x) , y } =E_{S(x),y}(\omega)=E_{x,S^{*}(y)}(\omega)=\braket{ E(\omega)x , S^{*}(y) } =\braket{ SE(\omega)x , y } $$and $E(\omega)S=SE(\omega)$.
- **Remark**: $C(\widehat{A})$ injects into $L^\infty(E)$ as follows: If $f\in C(\widehat{A})$ with $\left\| f \right\|_{\infty}=0$, then $$E(f^{-1}(\mathbb{C} \backslash\{ 0 \}))=0$$Therefore, by 3, $f^{-1}(\mathbb{C} \backslash \{ 0 \})=\varnothing$ and $f=0$.
- **Corollary**: Let $T\in \mathcal{B}(\mathcal{H})$ normal and $A:=\overline{\{ p(T,T^{*}):p\in \mathbb{C}[X,Y] \}}$. Then,
	1. there exists a unique resolution of identity $E$ on $\text{Sp}(T)$ s.t. $$T=\int_{\text{Sp}(T)}\lambda  \, dE(\lambda) $$
	2. we have a commutative diagram: $$\begin{CD}C(\text{Sp}(T))@>>>A\\@VVV&@VVV\\L^\infty(E)&@>\Psi>>B\end{CD}$$
	3. $B=\overline{\Psi(\mathcal{S}(\text{Sp}(T)))}$
	4. $S\in \mathcal{B}(\mathcal{H})$ commutes with $T$ and $T^{*}$ if and only if $S$ commutes with $E(\omega)$ for all $\omega\in \mathcal{B}_{\text{Sp}(T)}$
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