#Definition #ComplexAnalysis

> [!definition]
> For $\Omega \subseteq \mathbb{C}$ open, a function $f:\Omega\to \mathbb{C}$ is:
> 1. ***holomorphic at $z\in \Omega$*** if $f'(z):=\lim_{ h \to 0 } \frac{f(z+h)-f(z)}{h}$ exists.
> 2. ***holomorphic on $\Omega$*** if it is holomorphic at every $z\in \Omega$.
- **Related definition**: For $C\subseteq \mathbb{C}$ closed, $f$ is holomorphic on $C$ if it is in some open set containing $C$.
- **Related definition**: A function $f:\mathbb{C}\to \mathbb{C}$ is called ***entire*** if it is holomorphic on $\mathbb{C}$.
---
##### Properties

> [!lemma] Proposition
> Let $f:\mathbb{C}\to \mathbb{C}$ be holomorphic and $A$ is a unital Banach algebra. Then, 
> 1. $\text{Sp}_{A}(f(x))=f(\text{Sp}_{A}(x))$ where $f(x):=\sum_{n=0}^{\infty}\frac{f^{(n)}(0)}{n!}x^n$.

> [!proof]-
> We have that:
> 1. Let $x\in A$ and as $\text{Sp}_{A}(x)$ is compact, let $U\supseteq \text{Sp}_{A}(x)$ be open s.t. 
>    
>    Further, let $C$ be a closed path on $U$ enclosing $\text{Sp}_{A}(x)$. Then, $$\begin{array}{cccc} {}&{C}&\to&{A}\\&{\lambda} &\mapsto & {(\lambda e-x)^{-1}} \end{array}{}$$is a continuous function and for any $\varphi\in A^{*}$, $$\begin{array}{cccc} {}&{C}&\to&{\mathbb{C}}\\&{\lambda} &\mapsto & {\varphi((\lambda e-x)^{-1})} \end{array}{}$$is continuous. Then, $$F(\varphi):= \frac{1}{2\pi i} \int_{C}^{} f(\lambda)\varphi((\lambda e-x)^{-1}) \, d\lambda $$is continuous and $F\in (A^{*})^{*}$.
>    
>    Then, there exists $v\in A$ s.t. $F(\varphi)=\varphi(v)$ for all $\varphi\in A^{*}$. We will call $v=:f(x)$ for each $x$. Then, $$\text{Sp}_{A}(f(x))=f(\text{Sp}_{A}(x))$$