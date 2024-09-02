#Definition #ComplexAnalysis

> [!definition]
> For $\Omega \subseteq \mathbb{C}$ open, a function $f:\Omega\to \mathbb{C}$ is:
> 1. ***holomorphic at $z\in \Omega$*** if $f'(z):=\lim_{ h \to 0 } \frac{f(z+h)-f(z)}{h}$ exists.
> 2. ***holomorphic*** on an open set $U\subseteq\Omega$ if it is holomorphic at every $z\in U$.
> 3. ***holomorphic*** on a closed $C\subseteq\Omega$ if there exists $C\subseteq U\subseteq\Omega$ where $f$ is holomorphic on $U$.

^af578a

- **Related definition**: A function $f:\mathbb{C}\to \mathbb{C}$ is called ***entire*** if it is holomorphic on $\mathbb{C}$. ^39c223
---
##### Properties

> [!lemma] Proposition 1
> For $f:\Omega\to \mathbb{C}$, TFAE:
> 1. $f$ is holomorphic at $z\in \Omega$.
> 2. there exists $a\in \mathbb{C}$, $\varepsilon>0$ and $\psi:B_{<\varepsilon}(0) \backslash \{ 0 \}\to \mathbb{C}$ with $\lim_{ h \to 0 }\psi(h)=0$ s.t. $$f(z+h)-f(z)-ah=h\psi(h)\quad \forall h\in B_{<\varepsilon}(0)$$

> [!proof]-
> We have:
> 1. We define $a:=f'(z)$ and: $\psi(h):=\frac{f(z+h)-f(z)}{h}-a$ which is well-defined in $B_{<\varepsilon}(0) \backslash\{ 0 \}$ as $a$ exists. Then, we have that: $$\lim_{ h \to 0 } \psi(h)=a-a=0$$
> 2. We have that for $h\in B_{<\varepsilon}(0) \backslash\{ 0 \}$, $$\lim_{ h \to 0 }\frac{ f(z+h)-f(z)}{h}=\lim_{ h \to 0 } \psi(h)+a=a\in \mathbb{C}$$
- **Corollary**: if $f$ is holomorphic at $z\in \Omega$ it is continuous at $z$.
---
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