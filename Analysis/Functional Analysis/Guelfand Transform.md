#Definition #FunctionalAnalysis 

> [!definition]
> Let $A$ be a commutative [[Banach algebra]]. Then, the ***Guelfand transform*** of $x\in A$ is the function: $$\begin{array}{cccc} {\hat{x}:}&{\hat{A}}&\to&{\mathbb{C}}\\&{\chi} &\mapsto & {\chi(x)} \end{array}{}$$
---
##### Properties
> [!lemma] Theorem 1
> For any $x\in A$, 
> 1. $\hat{x}\in$ [[Continuous function Vanishing at Infinity|$C_{0}(\hat{A})$]].
> 2. $A\to C_{0}(\hat{A}),x\mapsto \hat{x}$ is an algebra homomorphism.
> 3. if $A$ is unital, $\text{Sp}_{A}(x)=\hat{x}(\hat{A})$.
> 4. if $A$ is non-unital, $\text{Sp}_{A}(x)=\hat{x}(\hat{A})\cup \{ 0 \}$.
> 5. $\|\hat{x}\|_{\infty}=\|x\|_{\text{sp}}$

> [!proof]-
> We have: 
> 1. Let $A$ be non-unital. Observe that for all $\varphi\in \hat{A}$, $\hat{x}(\varphi)=\varphi(x)=\tilde{\varphi}((x,0))=\widehat{(x,0)}(\tilde{\varphi})$. Of course, $\widehat{(x,0)}:\widehat{A_{I}}\to \mathbb{C}$ with $\widehat{(x,0)}(\varphi_{\infty})=\varphi_{\infty}(x,0)=0$. 
>    
>    Let $\varepsilon>0$ and $\varphi_{\infty}\in U\subseteq\widehat{A_{I}}$ open with $\left| \widehat{(x,0)}(\psi) \right|<\varepsilon$ for all $\psi\in U$. Then, $$\widehat{A_{I}}\backslash U \subseteq \widehat{A_{I}}\backslash \{ \varphi_{\infty} \} =\gamma(\hat{A})$$But then, $$K:=\{ \varphi\in \hat{A}:\gamma(\varphi)\in \widehat{A_{I}}\backslash U \}$$is compact as well for all $\varphi\notin K$, $$\left| \hat{x}(\varphi) \right| =\left| \widehat{(x,0)}(\tilde{\varphi}) \right|$$
>  2. Let $A$ be unital. If $\lambda\in \text{Sp}_{A}(x)$, then $x-\lambda e$ is not invertible. Therefore, by [[Regular Ideal|Corollary 5]], $x-\lambda e\in I\subsetneq A$ where $I$ is maximal. By there exists $\varphi\in \widehat{A}$ with $\text{ker }\varphi=I$. In particular, $\varphi(x-\lambda e)=0$. Therefore, $\lambda=\varphi(x)=\widehat{x}(\varphi)$. Therefore, $\text{Sp}_{A}(x)\subseteq\widehat{x}(\widehat{A})$
>     
>     Conversely, assume that $\lambda\in \widehat{x}(\widehat{A})$, i.e. $\lambda=\varphi(x)$ for some $\varphi\in \widehat{A}$. Then, $\varphi(x-\lambda e)=0$. Then, $x-\lambda e$ cannot be invertible, since otherwise there exists $y\in A$ s.t. $(x-\lambda e)y=e$. This implies that: $$\varphi(x-\lambda e)\varphi(y)=1$$which is a contradiction.
>     
>     
- **Corollary**: For $x,y\in A$, $\|xy\|_{\text{sp}}=\left\| \widehat{xy} \right\|_{\infty}\leq\|\hat{x}\|_{\infty}\|\hat{y}\|_{\infty}=\|x\|_{\text{sp}}\|y\|_{\text{sp}}$.
- **Remark**: For every non-commutative Banach algebra $A$ and $x,y\in A$, s.t. $xy=yx$, $\|xy\|_{\text{sp}}\leq\|x\|_{\text{sp}}\|y\|_{\text{sp}}$.
---
> [!lemma] Theorem 2
> Let $A$ be an abelian [[C*-Algebra|$C^{*}$-algebra]]. Then, the Guelfand transformation: $$A\to C_{0}(\hat{A})$$is an $C^{*}$-algebra isomorphism. More precisely, 
> 1. $\|\hat{x}\|_{\infty}=\|x\|$ for all $x\in A$.
> 2. $\widehat{x^{*}}=\overline{\widehat{x}}$ for all $x\in A$.

> [!proof]-
> Since $A$ is abelian, every $x\in A$ is normal and by [[C*-Algebra|Proposition 2]] and Theorem 1, $\left\| \hat{x} \right\|_{\infty}=\|x\|_{\text{sp}}=\|x\|$ for all $x\in A$. 
> 
> Hence, $A\ \hat{\to}\ C_{0}(\hat{A})$ is a norm-preserving $\mathbb{C}$-algebra homomorphism. In particular, it is injective and its image is closed, because an isometric image of $A$ is complete and thereby closed.
> 
> Let $\mathcal{B}:=\{ \hat{x}: x\in A \}\subseteq C_{0}(\hat{A})$. 
> 1. **Showing that $\widehat{x^{*}}=\overline{\widehat{x}}$**:
>    Let $$x=\underbrace{ \left( \frac{x+x^{*}}{2} \right) }_{ =: x_{1} }+i\underbrace{ \left( \frac{x-x^{*} }{2i}\right) }_{ =: x_{2} } $$ where $x_{1},x_{2}$ are self-adjoint. Then, by Theorem 2, $\widehat{x_{i}}(\hat{A})\subseteq \text{Sp}_{A}(x_{i})\subseteq \mathbb{R}$. Therefore, $$\widehat{x^{*}}(\chi)=\widehat{x_{1}}(\chi)-i\widehat{x_{2}}(\chi)=\widehat{x_{1}}(\chi)+i\widehat{x_{2}}(\chi)=\overline{\widehat{x}}(\chi)$$
> 2. **Showing $\mathcal{B}$ satisfies the hypothesis of [[Continuous function Vanishing at Infinity|Stone-Weierstrass]]**:
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
