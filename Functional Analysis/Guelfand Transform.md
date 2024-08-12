#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a commutative [[Banach Algebra]]. Then, 
> 1. the ***Guelfand transform*** of $x\in A$ is the function $$\widehat{x}:\widehat{A}\to \mathbb{C},\quad \varphi\mapsto \varphi(x)$$
---
##### Properties
> [!lemma] Theorem 1 (Guelfand Transform as Homomorphism)
> For a commutative Banach algebra $A$ and $x\in A$, 
> 1. $\widehat{x}\in C_{0}(\widehat{A})$ where $C_{0}$ is the [[Continuous function Vanishing at Infinity|space of continuous functions vanishing at infinity]].
> 2. $A\to C_{0}(\widehat{A}),x\mapsto \widehat{x}$ is an algebra homomorphism.
> 3. if $A$ is unital, $\text{Sp}_{A}(x)=\widehat{x}(\widehat{A})$.
> 4. if $A$ is non-unital, $\text{Sp}_{A}(x)=\widehat{x}(\widehat{A})\cup \{ 0 \}$.
> 5. $\|\widehat{x}\|_{\infty}=\|x\|_{\text{sp}}$.

> [!proof]-
> We have: 
> 1. If $A$ is unital, $\widehat{A}$ is compact and $C_{0}(\widehat{A})=C(\widehat{A})\ni \widehat{x}$. 
>    If $A$ is non-unital, let $\varepsilon>0$. As we have that $\varphi_{\infty}(x,0)=0$, we get that: $$K:=\{ \varphi\in \widehat{A}:\left| \widehat{x}(\varphi) \right| \geq \varepsilon \}\cong\{ \psi\in \widehat{A_{I}}:\left| \psi(x,0)\right| \geq \varepsilon \}$$where the RHS is a weak\*-closed set. Therefore, the RHS is weak\*-compact.
>    
>    Hence, $K$ is also weak\*-compact and $\widehat{x}$ vanishes at infinity.
> 2. We have that for $\varphi\in \widehat{A}$: $$\widehat{xy}(\varphi)=\varphi(xy)=\varphi(x)\varphi(y)=\widehat{x}(\varphi)\widehat{y}(\varphi)$$
> 3. Let $A$ be unital. If $\lambda\in \text{Sp}_{A}(x)$, then $x-\lambda e$ is not invertible and by [[Regular Ideal|Corollary 5]] $x-\lambda e$ is contained in some maximal ideal $I$. By [[Guelfand Spectrum|Theorem 3]], there exists $\varphi\in \widehat{A}$ s.t. $\text{ker }\varphi=I$. In particular, $\varphi(x-\lambda e)=0$ and $\lambda=\varphi(x)=\widehat{x}(\varphi)$. Therefore, $\text{Sp}_{A}(x)\subseteq \widehat{x}(\widehat{A})$.
>    
>    Similarly, let $\lambda\in \widehat{x}(\widehat{A})$, i.e. $\lambda=\varphi(x)$ for some $\varphi\in \widehat{A}$. Then, $\varphi(x-\lambda e)=0$ and $x-\lambda e$ cannot be invertible.
> 4. Let $A$ be non-unital. Then, $\text{Sp}_{A}(x)=\text{Sp}_{A_{I}}(x,0)=\widehat{(x,0)}(\widehat{A_{I}})$. As $\widehat{A_{I}}=\widehat{A}\cup \{ \varphi_{\infty} \}$, we have that: $$\widehat{(x,0)}(\widehat{A_{I}})=\widehat{(x,0)}(\widehat{A})\cup \{ \varphi_{\infty}(x,0) \}=\widehat{x}(\widehat{A})\cup \{ 0 \}$$
> 5. We have that: $$\|x\|_{\text{sp}}=\sup_{\lambda\in \text{Sp}_{A}(x)}\left| \lambda \right| =\sup_{\lambda\in \widehat{x}(\widehat{A})}\left| \lambda \right| = \sup_{\varphi\in \widehat{A}}\left| \widehat{x}(\varphi) \right| =\left\| \widehat{x} \right\| _{\infty}$$
>     
- **Corollary**: For $x,y\in A$, $\|xy\|_{\text{sp}}=\left\| \widehat{xy} \right\|_{\infty}\leq\|\hat{x}\|_{\infty}\|\hat{y}\|_{\infty}=\|x\|_{\text{sp}}\|y\|_{\text{sp}}$.
- **Remark**: For every non-commutative Banach algebra $A$ and $x,y\in A$, s.t. $xy=yx$, $\|xy\|_{\text{sp}}\leq\|x\|_{\text{sp}}\|y\|_{\text{sp}}$.
---
> [!lemma] Theorem 2 (Guelfand Transform as Isomorphism)
> For a commutative [[C*-Algebra|$C^{*}$-algebra]], 
> 1. $\|\widehat{x}\|_{\infty}=\|x\|_{\text{sp}}=\|x\|$ for  all $x\in A$.
> 2. $\widehat{x^{*}}=\overline{\widehat{x}}$ for all $x\in A$.
> 3. $A\to C_{0}(\widehat{A}),x\mapsto \widehat{x}$ is a $C^{*}$-algebra isomorphism.


> [!proof]+
> We have:
> 1. Since $A$ is commutative, every $x\in A$ is normal and by [[C*-Algebra|Proposition 2]] and Theorem 1, $\left\| \hat{x} \right\|_{\infty}=\|x\|_{\text{sp}}=\|x\|$ for all $x\in A$. 
> 2. Let $x\in A$. Then, $$x=\underbrace{ \left( \frac{x+x^{*}}{2} \right) }_{ =:x_{1} } +i\underbrace{ \left( \frac{x-x^{*}}{2i} \right) }_{ =:x_{2} }$$where $x_{1},x_{2}$ are self-adjoint. Then, by [[C*-Algebra|Proposition 5]] and Theorem 1, $$\widehat{x}_{i}(\widehat{A})\subseteq \text{Sp}_{A}(x_{i})\subseteq \mathbb{R}$$Therefore, $$\widehat{x^{*}}(\varphi)=\varphi((x_{1}+ix_{2})^{*})=\varphi(x_{1}-ix_{2})=\varphi(x_{1})-i\varphi(x_{2})=\overline{\varphi(x_{1})+i\varphi(x_{2})}=\overline{\varphi(x)}=\overline{\widehat{x}(\varphi)}$$
> 3. From 1, $A\to C_{0}(\widehat{A})$ is a norm-preserving algebra homomorphism. Let $\mathcal{B}:=\{ \widehat{x}: x\in A \}$. Then, $\mathcal{B}$ is a subalgebra and since $A$ is complete and $A\to C_{0}(\widehat{A})$ is norm-preserving, $\mathcal{B}$ is complete in $C_{0}(\widehat{A})$ and hence closed. 
>    
>    Now, we will use [[Continuous function Vanishing at Infinity|Stone-Weierstrass]]: 
>    1. if $\widehat{x}\in \mathcal{B}$, then 
> 
> 2. **Showing $\mathcal{B}$ satisfies the hypothesis of **:
> 	- If $\hat{x}\in \mathcal{B}$, then $\widehat{x^{*}}=\overline{\widehat{x}}$ and $\overline{\widehat{x}}\in \mathcal{B}$.
> 	- For all $\chi\in \hat{A}$, there exists $x\in A$ with $\chi(x)\neq 0$. Then, $\hat{x}(\chi)\neq 0$. 
> 	- For any $\chi_{1}\neq \chi_{2}$ in $\hat{A}$, there exists $x\in A$ with $\chi_{1}(x)\neq \chi_{2}(x)$ then $\hat{x}(\chi_{1})\neq \hat{x}(\chi_{2})$. 
> 	
> 	Therefore, $\mathcal{B}$ is dense in $C_{0}(\hat{A})$ and as the image is closed, $\mathcal{B}=C_{0}(\hat{A})$.
---
> [!lemma] Corollary 3
> For abelian $C^{*}$-algebras $A,B$, the following are equivalent:
> 1. $A\cong B$ as a $C$-algebra.
> 2. $\hat{A}\cong \hat{B}$ are homeomorphic.
> 3. $A$ and $B$ are isomorphic as $C^{*}$-algebra.
---
> [!lemma] Theorem 4 (Pre-spectral Theorem)
> Let $A$ be a unital $C^{*}$-algebra and $x\in A$ normal. We define: $$B:=\overline{\{ P(x,x^{*}):P\in \mathbb{C}[X,Y] \}}\subseteq A$$with $x^0=e$. Then, 
> 1. $B$ is an abelian sub-$C^{*}$-algebra of $A$.
> 2. $\widehat{B}\ \hat{\to}\ \text{Sp}_{A}(x)$ is a homomorphism. 
> 3. For every $f\in C(\text{Sp}_{A}(x))$ there exists a unique element denoted $f(x)\in B$ s.t. $$\widehat{f(x)}(\chi)=f(\chi(x)),\quad \forall x\in \widehat{B}$$The resulting map $$\begin{array}{cccc}&{C(\text{Sp}_{A}(x))}&\to&{B}\\&{\hat{f}} &\mapsto & {f(x)} \end{array}{}$$is a $C^{*}$-algebra isomorphism with $1\mapsto e$ and $\text{id}\mapsto x$.
---
