#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a commutative [[Banach algebra]]. A ***character*** of $A$ is a non-trivial [[C-Algebra|$\mathbb{C}$-algebra]] homomorphism $\chi:A\to \mathbb{C}$. Then, the ***Guelfand spectrum*** $\hat{A}$ of $A$ is defined as the set of characters of $A$.
- **Remark**: For any character $\chi\in \hat{A}$, $\chi(A)$ is a vector subspace of $\mathbb{C}$, i.e. $\chi(A)=\mathbb{C}$.
- **Remark**: If a $\mathbb{C}$-algebra $A$ has a unit $e$, then for any $\mathbb{C}$-algebra homomorphism $\varphi:A\to \mathbb{C}$, $\varphi(e)=1$.
- **Remark**: Given any $\mathbb{C}$-algebra homomorphism $\varphi:A\to \mathbb{C}$, we can define: $$\begin{array}{cccc} {\varphi_{I}:}&{A\times \mathbb{C}}&\to&{\mathbb{C}}\\&{(x,\lambda)} &\mapsto & {\varphi(x)+\lambda} \end{array}{}$$Then, $\hat{A}_{I}=\{ \varphi_{I}:\varphi\in \hat{A} \}\cup \{ \varphi_{\infty} \}$ where $\varphi_{\infty}(x,\lambda)=\lambda$. One also often denotes $\hat{A}_{I}=\hat{A}\cup \{ \varphi_\infty \}$.
---
##### Properties
> [!lemma] Proposition 1
> For every $\varphi\in \hat{A}$ we have: $$\left| \varphi(x) \right| \leq\|x\|_{\text{sp}}\quad \forall x\in A$$ In particular, $\varphi\in A^{*}$ with $\left\| \varphi \right\|\leq 1$ with equality if $A$ is unital with $\|e\|=1$ for the unit.

> [!proof]-
> Due to the remark, we may assume that $A$ is unital. If $\left| \lambda \right|>\|x\|_{\text{sp}}$.  Then, $x-\lambda e$ is invertible. But then if $y\in A$ is the inverse of $x-\lambda e$, we have: $$y(x-\lambda e)=e\implies\varphi(y)\varphi(x-\lambda e)=\varphi(e)=1$$which means $\varphi(x-\lambda e)\neq 0$ and $\varphi(x)\neq\lambda$. Therefore, $\left| \varphi(x) \right|\leq \|x\|_{\text{sp}}$.
> 
> Further, as $\|x\|_{\text{sp}}\leq\|x\|$, $\left\| \varphi \right\|\leq 1$. If $\|e\|=1$, then since $\varphi(e)=1=\|e\|$, $\|\varphi\|=1$.
---
> [!lemma] Theorem 2
> Let $A$ be a commutative [[Banach algebra]]. Then, $\varphi\mapsto \text{ker }\varphi$ gives a bijection between $\hat{A}$ and $$\text{Max}(A):=\{ I\subseteq A :I \text{ regular maximal ideal}\}$$

> [!proof]-
> Let $\varphi\in\hat{A}$. Then, $\varphi:A\to \mathbb{C}$ is a non-trivial $\mathbb{C}$-algebra homomorphism. Hence, $\text{ker }\varphi$ is a proper ideal. $\varphi(A)=\mathbb{C}$ and there fore there exists $u\in A$ with $\varphi(u)=1$. Then, for all $x\in A$, $ux-x\in \text{ker }\varphi$. Since $A / \text{ker}(\varphi)\cong \mathbb{C}$, $\text{ker}(\varphi)$ is maximal.
> 
> Now, assume $I=\text{ker }\varphi_{1}=\text{ker }\varphi_{2}$ and let $u\in A$ be an identity modulo $I$. Clearly, $u\notin I$ and since $I$ has codimension 1 in $A$, $A=\mathbb{C}u+I$. Therefore, $\varphi_{1}(u)=\varphi_{2}(u)=1$. It follows that: $$\varphi_{1}(\lambda u+v)=\lambda\varphi_{1}(u)=\lambda=\lambda(\varphi_{2}(u))=\varphi_{2}(\lambda u+v)$$
> Let $I\subsetneq A$ be maximal regular. By [[Regular Ideal|Corollary 3.2]], $I=\overline{I}$ is closed. Then, by [[Banach Algebra|Proposition 3]], $A / I$ is a Banach algebra and $\pi:A \to A / I$ is a Banach algebra homomorphism. And $A / I$ is a unital banach algebra. Since $I$ is maximal every $x+I!+I$ in $A / I$ is invertible.
> 
> Indeed otherwise, if $x+I \neq I$, where not invertible, $J:=(x+I)A / I\subsetneq A / I$. Then, $$I\subseteq \pi ^{-1}(J)\subseteq A$$ correspodingin the maximality of $I$.
> 
> Therefore, by Guelfand-Mazur, $A / I\xrightarrow{\sim}\mathbb{C}$. Now, compsoing $A\xrightarrow{\pi}A / I\xrightarrow{\sim}\mathbb{C}$, we get a $\mathbb{C}$-algebra homomorphism $\varphi:A\to C$ with $\text{ker }\varphi=I$.
---
> [!lemma] Theorem 3 (Spectral Theorem)
> Let $A\subseteq \mathcal{B}(\mathcal{H})$ be an commutative sub-$C^{*}$-algebra containing $\text{id}_{\mathcal{H}}$ and $\widehat{A}$ is Guelfand spectrum. Then, 
> 1. there exists a unique [[resolution of identity]] $E$ on $\mathcal{B}_{\widehat{A}}$ s.t. for every $T\in A$,$$T=\int_{\widehat{A}}\widehat{T}  \, dE $$where $\widehat{T}\in C(\widehat{A})$ is the Guelfand transform of $T$. This is equivalent to: $$\braket{ T(x) , y } =\int_{\widehat{A}}\widehat{T}  \, dE_{x,y} $$
> 2. the inverse of the Guelfand transform $\gamma$ extends to a $C^{*}$-algebra isomorphism $\Phi:L^\infty(E)\to B$, with the following commutative diagram: $$\begin{CD}L^\infty(E) @>\Phi>> B\\@AAA&@AAA\\C(\widehat{A}) @>\gamma>>A\end{CD}$$given by $$\Phi(f):=\int_{\widehat{A}}f \, dE$$where $\Phi$ is linear, multiplicative and satisfies $\Phi(\bar{f})=\Phi(f)^{*}$ and $\left\| \Phi(f) \right\|=\left\| f \right\|_{\infty}$.
> 3. we have: $B=\overline{\Phi(\mathcal{S}(\hat{A}))}$
> 4. If $\omega \subseteq \widehat{A}$ is non-empty and open, then $E(\omega)\neq 0$.
> 5. an operator $S\in \mathcal{B}(\mathcal{H})$ commutes with $A$ if and only if $S$ commutes with $E(\omega)$ for all $\omega\in \mathcal{B}_{\widehat{A}}$.

> [!proof]+
> From lemma 5.21 we have a unique $\Phi(f)\in \mathcal{B}(\mathcal{H})$ s.t. $\int_{\widehat{A}}^{} f \, dE_{x,y}=\braket{ \Phi(f)x , y }$ for all $x,y\in \mathcal{H}$ with the characteristics:
> 1. $\Phi:\mathcal{B}^\infty(\widehat{A})\to \mathcal{B}(\mathcal{H})$ is linear.
> 2. the diagram in 2 commutes
> 3. $\Phi(f)^{*}=\Phi(\overline{f})$ for all $f\in \mathcal{B}^\infty(\widehat{A})$.
> 4. $\Phi(fg)=\Phi(f)\Phi(g)$
>
> Then, we
---
##### Examples
> [!h] Example 1
> Let $X$ be a [[locally compact Hausdorff space]]. Then, $$\begin{array}{cccc} {}&{X}&\to&{\widehat{C_{0}(X)}}\\&{x} &\mapsto & {\text{ev}(x)} \end{array}{}$$is a bijection.
---
> [!h] Example 2
> We have $\widehat{\ell^\infty(\mathbb{N})}\cong\{ \text{Ultra}(\mathbb{N}) \}$, i.e. the ultrafilters on $\mathbb{N}$.
---