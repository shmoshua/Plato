#Definition #DifferentialGeometry 
> [!definition]
> Let $M$ be a [[smooth manifold]]. For $p\in M$, the ***tangent space*** $\text{T}_{p}M$ is defined as: $$\text{T}_{p}M:=\left\{  v\in C^\infty(M)^{*}\left| \exists \gamma:(-\varepsilon,\varepsilon)\to M\text{ smooth curve, } \gamma(0)=p\text{ s.t. }vf=\left. \frac{d}{dt} \right|_{t=0}f(\gamma(t)) \right. \right\}$$
> 
---
##### Properties
> [!lemma] Theorem 1 (Tangent Space is a Vector Space)
> For $\text{T}_{p}M$ and $(U,\varphi)$ a chart at $p$ with coordinate functions $x^1,\dots,x^m\in C^\infty(\mathbb{R})$,
> 1. the ***coordinate vectors***, defined as: $$\left. \frac{ \partial  }{ \partial x ^i} \right| _{p}:C^\infty(M)\to \mathbb{R},\quad f\mapsto \left. \frac{ \partial f }{ \partial x^i }  \right| _{p}:=\left. \frac{ \partial f\circ \varphi ^{-1} }{ \partial \pi^i } \right| _{\varphi(p)} $$form a basis of $\text{T}_{p}M$.
> 2. $\text{T}_{p}M\cong \mathbb{R}^m$ as a vector space.

> [!proof]-
> We have that: 
> 1. **Claim 1: $\left. \frac{ \partial  }{ \partial x^i } \right|_{p}\in \text{T}_{p}M$**. 
>    Let us define a curve $\tilde{\gamma}:(-\varepsilon,\varepsilon)\to \mathbb{R}^m,t\mapsto \varphi(p)+te_{i}$. Then, it is smooth and therefore, $\gamma:=\varphi ^{-1}\circ\tilde{\gamma}$ is smooth and:$$\left. \frac{d}{dt} \right| _{t=0}f(\gamma(t))=\left. \frac{d}{dt} \right| _{t=0}f(\varphi ^{-1}(\tilde{\gamma}(t)))=d_{\varphi(p)}(f\circ \varphi ^{-1})(e_{i})=\left. \frac{ \partial f\circ \varphi ^{-1} }{ \partial \pi^j }  \right|_{\varphi(p)} \delta_{i}^j=\left. \frac{ \partial f }{ \partial x^i } \right| _{p} $$
> 2. **Claim 2: the span of $\left. \frac{ \partial  }{ \partial x^i } \right|_{p}$ is equal to $\text{T}_{p}M$**:
>    Let $\gamma:(-\varepsilon,\varepsilon)\to M$ be a smooth curve. Then, let $v\in C^\infty(M)^{*}$ with $vf=\frac{d}{dt}|_{t=0}f(\gamma(t))$. Therefore, $v\in \text{T}_{p}M$. Then, we have $\varphi(\gamma(t))=\sum_{i=1}^{m}(x^i\circ\gamma)(t)e_{i}$. Therefore, $$\begin{align}vf&=\left. \frac{d}{dt} \right|_{t=0}f(\gamma(t))=\sum_{i=1}^{m}\left. \frac{ \partial (f\circ \varphi ^{-1}) }{ \partial \pi^i }  \right|_{\varphi(p)}\underbrace{ \left. \frac{ d (x^i\circ \gamma) }{ d t }  \right| _{0} }_{ =:\alpha^i\in \mathbb{R} }=\sum_{i=1}^{m}\alpha^i\left. \frac{ \partial  }{ \partial x^i }  \right| _{p}(f)\end{align}$$This shows that $\text{T}_{p}M\subseteq \text{Span}(\left. \frac{ \partial  }{ \partial x^1 } \right|_{p},\dots,\left. \frac{ \partial  }{ \partial x^m } \right|_{p})$.
>    
>    Conversely, let $v$ in the span. Then, let $v=\sum_{i=1}^{m}v^i\frac{ \partial  }{ \partial x^i }|_{p}$. Let $\tilde{\gamma}:(-\varepsilon,\varepsilon)\to \mathbb{R}^m, t\mapsto \varphi(p)+t(v^1,\dots,v^m)$, which is smooth. Consider $\gamma:=\varphi ^{-1}\circ\tilde{\gamma}$. Then, $$\left. \frac{d}{dt} \right| _{t=0}f(\gamma(t))=d_{\varphi(p)}(f\circ \varphi ^{-1})(v^1,\dots,v^m)=\left. \frac{ \partial f\circ \varphi ^{-1} }{ \partial \pi^i } \right| _{\varphi(p)}v^i=v^i\left. \frac{ \partial  }{ \partial x^i }  \right| _{p}(f)=vf $$ Therefore, $\text{T}_{p}M=\text{Span}(\left. \frac{ \partial  }{ \partial x^1 } \right|_{p},\dots,\left. \frac{ \partial  }{ \partial x^m } \right|_{p})$.
> 3. **Claim 3: $\frac{ \partial  }{ \partial x^i }|_{p}$ are linearly independent.**
>    Let $v:=v^i\left. \frac{ \partial  }{ \partial x^i }  \right| _{p}=0$. Then, from above we have that for any $f\in C^\infty(M)$, $vf=0$. From the definition, we get that $\gamma$ is constant and as $\gamma(0)=p$, $\gamma=p$. Then, as above, $$\alpha^i=\left. \frac{d}{dt} \right| _{t=0}(x^i\circ \gamma)=0$$ 
---
> [!lemma] Theorem 2 (Equivalent Definitions of Tangent Space)
> We have that:
> 1. the map:$$\begin{array}{cccc} &{\{ (U,\varphi,v):(U,\varphi)\text{ chart containing }p,v\in \mathbb{R}^m \}_{/\sim}}&\to&{\text{T}_{p}M}\\&{(U,\varphi,v)} &\mapsto & {v^i\left. \frac{ \partial }{ \partial x^i }  \right|_{p} } \end{array}{}$$is a vector space isomorphism, where $\varphi=(x^1,\dots,x^m)$ and $(U,\varphi,v)\sim(V,\psi,w)$ if and only if $d_{\varphi(p)}(\psi\varphi ^{-1})v=w$.
> 2. $\text{T}_{p}M= \text{Der}_{p}C^\infty(M):=\{ v\in C_{p}^\infty(M)^{*}:v(fg)=f(p)v(g)+v(f)g(p) \}$ where $C_{p}^\infty(M)$ is the [[Ring of Germs|ring of germs]] at $p$.

> [!proof]+
> We have that:
> 1. It suffices to show that the map is well-defined. Let $(U,\varphi)$ and $(V,\psi)$ be two charts at $p$ s.t. $(U,\varphi,v)\sim(V,\psi,w)$. Then, $$\begin{align}\sum_{i=1}^{m}w^i\left. \frac{ \partial f  }{ \partial y^i }  \right| _{p}&=\sum_{i=1}^{m}d_{\varphi(p)}(\pi^i\psi\varphi ^{-1})v\left. \frac{ \partial  f\circ \psi ^{-1}}{ \partial \pi^i }  \right| _{\psi(p)}\\&=\sum_{j=1}^{m}\sum_{i=1}^{m}\left. \frac{ \partial  f\circ \psi ^{-1}}{ \partial \pi^i }  \right| _{\psi(p)}\left. \frac{ \partial \pi^i\psi\varphi ^{-1} }{ \partial \pi^j }  \right|_{\varphi(p)} v^j\\&= \sum_{j=1}^{m}\left. \frac{ \partial f\circ \varphi ^{-1} }{ \partial \pi^j }  \right|_{\varphi(p)} v^j\\&=\sum_{j=1}^{m}v^j\left. \frac{ \partial f }{ \partial x^j }  \right|_{p} \end{align} $$
> 2. For $v=v^i\frac{ \partial  }{ \partial x^i }|_{p}\in \text{T}_{p}M$, we have that: $$\begin{align}v(fg)&=\left. \frac{d}{dt} \right| _{t=0}fg(\gamma(t))\\&=\sum_{i=1}^{m}\left. \frac{ \partial ((f\cdot g)\circ \varphi ^{-1}) }{ \partial \pi^i }  \right| _{\varphi(p)}\left. \frac{ \partial x^i\circ \gamma }{ \partial t }  \right|_{0} \\&=\sum_{i=1}^{m}\left. \frac{ \partial (f\circ \varphi ^{-1}\cdot g\circ \varphi ^{-1}) }{ \partial \pi^i }  \right| _{\varphi(p)}\left. \frac{ \partial x^i\circ \gamma }{ \partial t }  \right|_{0} \\&=\sum_{i=1}^{m}\left(g(p) \left. \frac{ \partial (f\circ \varphi ^{-1}) }{ \partial \pi^i }  \right| _{\varphi(p)}+f(p) \left. \frac{ \partial (g\circ \varphi ^{-1}) }{ \partial \pi^i }  \right| _{\varphi(p)} \right)\left. \frac{ \partial x^i\circ \gamma }{ \partial t }  \right|_{0}\\&=g(p)v(f)+f(p)v(g) \end{align}$$Therefore, $\text{T}_{p}M\subseteq \text{Der}_{p}C^\infty(M)$. Conversely, let $v\in \text{Der}_{p}C^\infty(M)$. Then, 
> 	1. **Claim 1: for $g\in C^\infty(M)$ with $g \equiv 1$ in a neighborhood of $p$, we have $v( fg)=v(f)$ for all $f\in C^\infty(M)$.**
> 	   By linearity of $v$, it suffices to show that $v(h)=0$ for $h:=f-fg$. Observe that $h$ vanishes on a neighborhood $V$ of $p$. Then, we will construct $\psi\in C^\infty(M)$ s.t. $\text{supp }\psi \subseteq V$ and $\psi(p)\neq 0$. as follows. 
> 	   
> 	   Let $(U,\varphi)$ be a chart at $p$ s.t. $U\subseteq V$. Let $C\subseteq \mathbb{R}^m$ be a hypercube centered at $\varphi(p)$ contained in $\varphi(U)$. Then, by Urysohn's lemma, we can construct a smooth function $\beta:\mathbb{R}^m\to \mathbb{R}$ with $\text{supp}(\beta)\subseteq C$ and $\beta(\varphi (p))=1$. Therefore, $\psi:=\beta \circ\varphi\in C^\infty(U)$ naturally extends to $C^\infty(M)$ with $0$ outside of $U$, with the desired conditions as above.  
> 	   
> 	   Then, we have that $h\cdot\psi=0$. Therefore, $$0=v(h\psi)=v(h)\psi(p)+h(p)v(\psi)=v(h)\psi(p)$$Hence, $v(h)=0$ as $\psi(p)\neq 0$.
> 	   
>    Now, let $C\subseteq \mathbb{R}^m$ be the hypercube at $\varphi(p)$ and $C_{\frac{1}{2}}$ be the hypercube at $\varphi(p)$ with half the length than $C$. Then, let $\beta:\mathbb{R}^m\to \mathbb{R}$ be the smooth function s.t. $\text{supp}(\beta)\subseteq C$ and $\beta|_{C_{1 /2}}\equiv 1$ given by the [[Smooth Manifold|smooth version of Urysohn lemma]].
>    
> 	2. Claim 2: Let $(U,\varphi)$ be a chart at $p$. Choose $\varepsilon>0$ s.t. $V:=\prod_{i=1}^{m}(\varphi(p)_{i}-2\varepsilon,\varphi(p)_{i}+2\varepsilon)\subseteq\varphi(U)$. Now, by the smooth version of the Urysohn lemma, there exists a functon $g\in C^\infty(\mathbb{R}^m,[0,1])$ s.t. 
> 1. $g(x)=1$ for $x\in \prod_{i=1}^{m}\left( \varphi(p)_{i}-\frac{\varepsilon}{2},\varphi(p)_{i}+\frac{\varepsilon}{2} \right)$ and 
> 2. $g(x)=0$ for $x\notin \prod_{i=1}^{m}\left( \varphi(p)_{i}-\varepsilon,\varphi(p)_{i}+\varepsilon \right)$
> 
> For $f\in C^\infty(M)$, by Lemma 1, we have $\delta(f)=\delta(f\cdot(g\circ\varphi))$ where we extend $g\circ\varphi$ to $M \backslash U$ with zero. Then, $$\delta(f)=\delta(f\cdot (g\circ \varphi))=\delta(((f\circ \varphi^{-1})\cdot g)\circ \varphi)$$where $(f\circ\varphi ^{-1})\cdot g\in C^\infty(\mathbb{R}^n)$ with support in $\prod_{i=1}^{m}\left( \varphi(p)_{i}-\varepsilon,\varphi(p)_{i}+\varepsilon \right)$.
> 
> Now, for every $F\in C^\infty(V)$ define $\alpha(F):=\delta((F\cdot g)\circ\varphi)$ which is a derivation of $C^\infty(V)$ at $\varphi(p)$ as: $$\begin{align}\alpha(FG)&=\delta((F\cdot G\cdot g)\circ \varphi)\\&=\delta((F\cdot g)\circ \varphi)(G\cdot g)(\varphi(p))+(F\cdot g)(\varphi(p))\delta((G\cdot g)\circ \varphi)\\&=\alpha(F)G(\varphi(p))+ F(\varphi(p))\alpha(G)\end{align}$$Therefore, by Lemma 2, there exists $G_{1},\dots,G_{n}\in C^\infty(V)$ with: 
> 1. $G_{i}(\varphi(p))=\partial_{i}F(\varphi(p))$ and
> 2. $F(x)=F(\varphi(p))+\sum_{i=1}^{n}(x_{i}-\varphi(p)_{i})G_{i}(x)$
>    
> Then, $$\begin{align}\alpha(F)&=\alpha(F(\varphi(p))\cdot 1)+\sum_{i=1}^{n}\alpha(x\mapsto x_{i}-\varphi(p)_{i})G_{i}(\varphi(p))\\&=\sum_{i=1}^{n}\underbrace{ \alpha(x\mapsto x_{i}-\varphi(p)_{i}) }_{ =:v_{i} }\frac{ \partial F }{ \partial x_{i} } (\varphi(p))\end{align}$$Therefore, $$\begin{align}\delta(f)&=\delta(((f\circ \varphi ^{-1})\cdot g)\circ \varphi)\\&=\alpha(f\circ \varphi ^{-1})\\&=\sum_{i=1}^{n}v_{i}\frac{ \partial (f\circ \varphi^{-1}) }{ \partial x _{i}}\varphi(p)\\&=d_{\varphi(p)}(f\circ \varphi ^{-1})(v)\\&=d_{p}f(v)\end{align} $$
> 	   
> 	