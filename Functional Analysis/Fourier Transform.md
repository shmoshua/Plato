#Definition #FunctionalAnalysis 

> [!definition]
> Let $G$ be an [[LCA group]]. Then, $L^1(G)$ is a commutative [[C*-Algebra|involutive Banach algebra]]. For $f\in L^1(G)$ and $\chi\in \widehat{G}$, the ***Fourier transform*** $\widehat{f}$ is defined as: $$\widehat{f}(\chi):=\int_{G}^{} f(x)\overline{(x,\chi)} \, d\mu(x) $$where $\mu$ is some fixed [[Haar measure]] on $G$ and $\widehat{G}$ is the [[Pontryagin dual]] of $G$.
---
##### Properties

> [!lemma] Theorem 1
> It holds that:
> 1. The Fourier transform: $$\begin{array}{cccc} {}&{L^1(G)}&\to&{C_{0}(\widehat{G})}\\&{f} &\mapsto & {\widehat{f}} \end{array}{}$$is a norm decreasing $*$-homomorphism where the image $A(\widehat{G})\subseteq C_{0}(\widehat{G})$ is dense.
> 2. $A(\widehat{G})$ is invariant under translations by $\widehat{G}$ and multiplication by $\chi\mapsto(x,\chi)$ for all $x\in G$.
> 3. For $f\in L^1(G)$ and $\chi\in \widehat{G}$, $$(f*\chi)(x)=(x,\chi)\widehat{f}(\chi),\quad \forall x\in G$$

> [!proof]-
> We have:
> 1. Under the identification of $\widehat{G}$ with $\widehat{L^1(G)}$, the Fourier transform coincides with the Guelfand transform: $$\widehat{f^*}(\chi)=\int_{G}\overline{f(x ^{-1})}\overline{(x,\chi)}  \, d\mu(x)=\overline{\int_{G}^{} f(x ^{-1})(x,\chi) \, d\mu(x) }=\overline{\int_{G}^{} f(x)\underbrace{ (x ^{-1},\chi) }_{ =\chi(x ^{-1})=\chi(x) ^{-1}=\overline{\chi(x)} } \, d\mu(x) }=\overline{\widehat{f}(\chi)} $$Now, $A(\widehat{G})$ is a subalgebra of $C_{0}(\widehat{G})$ for which:
>    1. invariant under complex conjugate
>    2. for any $\chi\in \widehat{G}$, since $\left| \chi(x)\right|=1$ for all $x\in G$, there exists $f\in L^1(G)$ s.t. $\int_{G}f(x)\overline{\chi(x)}  \, d\mu(x)\neq 0$. Therefore, $\widehat{f}(\chi)\neq 0$.
>    3. As $\widehat{G}\hookrightarrow L^\infty(G)$ is injective, for any $\chi_{1}\neq \chi_{2}\in \widehat{G}$, there exists $f\in L^1(G)$ s.t. $\widehat{f}(\chi_{1})\neq \widehat{f}(\chi_{2})$
>    
>    Therefore, the density follows from [[Continuous function Vanishing at Infinity#^2e5b88|Stone-Weierstrass]].
>   3. We have: $$\widehat{f}(\chi \chi_{0})=\int_{G}^{} f(x)\overline{\chi_{0}(x)}\overline{(x,\chi)} \, d\mu(x)=\widehat{(f\cdot \overline{\chi_{0}})}(\chi)  $$and$$\begin{align}\widehat{f}(\chi)(x,\chi)&=\int_{G}^{} f(y)\overline{(y,\chi)} \, d\mu(y) (x,\chi)\\&=\int_{G}^{} f(y)\overline{(yx ^{-1},\chi)} \, d\mu(y) \\&=\int_{G}^{} f(xy)\overline{(y,\chi)} \, d\mu(y) \\&=\widehat{(\lambda(x ^{-1}f))}(\chi)\end{align}$$
---
##### Examples
