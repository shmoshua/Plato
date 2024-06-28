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

> [!proof]+
> We have that:
> 1. It suffices to show that the map is well-defined. Let $(U,\varphi)$ and $(V,\psi)$ be two charts at $p$ s.t. $(U,\varphi,v)\sim(V,\psi,w)$. Then, $$\begin{align}\sum_{i=1}^{m}w^i\left. \frac{ \partial f  }{ \partial y^i }  \right| _{p}&=\sum_{i=1}^{m}d_{\varphi(p)}(\pi^i\psi\varphi ^{-1})v\left. \frac{ \partial  f\circ \psi ^{-1}}{ \partial \pi^i }  \right| _{\psi(p)}\\&=\sum_{j=1}^{m}\sum_{i=1}^{m}\left. \frac{ \partial  f\circ \psi ^{-1}}{ \partial \pi^i }  \right| _{\psi(p)}\left. \frac{ \partial \pi^i\psi\varphi ^{-1} }{ \partial \pi^j }  \right|_{\varphi(p)} v^j\\&= \sum_{j=1}^{m}\sum_{i=1}^{m}\left. \frac{ \partial  f\circ \psi ^{-1}}{ \partial \pi^i }  \right| _{\psi(p)}\left. \frac{ \partial \pi^i\psi\varphi ^{-1} }{ \partial \pi^j }  \right|_{\varphi(p)} v^j\end{align} $$