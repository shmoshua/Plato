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