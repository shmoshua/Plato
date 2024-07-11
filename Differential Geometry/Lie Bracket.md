#Definition #DifferentialGeometry 

> [!definition]
> Let $V$ be a $K$-[[vector space]] and $A,B\in \text{End}(V)$. 
> 1. The ***bracket of $A$ and $B$*** is given by: $$[A,B]:=AB-BA\in \text{End}(V)$$
> 2. For a [[Smooth Manifold|smooth manifold]] $M$, the ***Lie bracket*** is a bilinear map: $[\cdot,\cdot]:\Gamma(\text{T}M)\times\Gamma(\text{T}M)\to\Gamma(\text{T}M)$ where: $$[X,Y]_{p}(f)=X_{p}(Y(f))-Y_{p}(X(f))$$
- **Remark**: $[X,Y]$ is bilinear but not associative.
- **Remark**: From [[Vector Field|Example 1]], consider the isomorphism $\alpha :\Gamma(\text{T}M)\to \text{Der }C^\infty(M)$. Then, $$\alpha([X,Y])=\alpha X\alpha Y-\alpha Y\alpha X=[\alpha X,\alpha Y]$$
- **Related definition**: $X,Y$ ***commute*** if $[X,Y]=0$.
---
##### Properties

> [!lemma] Lemma 1
> Let $X,Y,Z\in \Gamma(\text{T}M)$. Then,
> 1. for $f,g\in C^\infty(M)$, $[fX,gY]=fg[X,Y]+f\cdot X(g)\cdot Y-g\cdot Y(f)\cdot X$.
> 2. $[Y,X]=-[X,Y]$
> 3. $[[X,Y],Z]+[[Y,Z],X]+[[Z,X],Y]=0$, i.e. the ***Jacobi identity*** holds.

> [!proof]-
> We have:
> 1. For $p\in M$ and $h\in C^\infty(M)$, $$\begin{align}[fX,gY]_{p}(h)&=f(p)X_{p}(gY(h))-g(p)Y_{p}(fX(h))\\&=f(p)(g(p)X_{p}(Yh)+X_{p}(g)Y_{p}h)-g(p)(f(p)Y_{p}(Xh)+Y_{p}f\cdot X_{p}h)\\&=f(p)g(p)[X,Y]_{p}(h)+f(p)X_{p}(g)Y_{p}h-g(p)Y_{p}f\cdot X_{p}h\end{align}$$
> 2. We have that: $$[Y,X]_{p}(f)=Y_{p}(Xf)-X_{p}(Yf)=-(X_{p}(Yf)-Y_{p}(Xf))=-[X,Y]$$
> 3. We have that: $$\begin{align}[[X,Y],Z]_{p}(f)+[[Y,Z],X]_{p}(f)&=[X,Y]_{p}(Zf)-Z_{p}([X,Y]f)+[Y,Z]_{p}(Xf)-X_{p}([Y,Z]f)\\&=X_{p}(ZYf)-Y_{p}(XZf)-Z_{p}(XYf)+Y_{p}(ZXf)\\&=Y_{p}([Z,X]f)-[Z,X]_{p}(Yf)\\&=[Y,[Z,X]]_{p}f\\&=-[[Z,X],Y]_{p}f\end{align}$$
---
> [!lemma] Proposition 2
> Let $X,Y\in \Gamma(\text{T}M)$ and $p\in M$.  
> 1. for a chart $(U,\varphi)$, the local coordinates of $[X,Y]$ is given as $[X,Y]|_{U}=\sum_{j=1}^{m}Z^j\frac{ \partial  }{ \partial x^j }$ where $Z^j \in C^\infty(U)$ given by:: $$Z^j(p):=\sum_{i=1}^{m}X^i(p)\frac{ \partial Y^j }{ \partial x^i } (p)-Y^i(p)\frac{ \partial X^j }{ \partial x^i }(p) $$

> [!proof]-
> Let $(U,\varphi)$ be a chart on $M$ and $p,q\in U$. Then, $$X_{p}=\sum_{i=1}^{m}X^i(p)\left. \frac{ \partial  }{ \partial x^i }  \right|_{p},\quad Y_{q}=\sum_{i=1}^{m}Y^i(q)\left. \frac{ \partial  }{ \partial x^i }  \right|_{q} $$Then, $$(L_{X}L_{Y})(f)(p)=\sum_{i=1}^{m}X_{i}(p)\left. \frac{ \partial  }{ \partial x^i }  \right|_{p}(L_{Y}f)=\sum_{i=1}^{m}X_{i}(p) \frac{ \partial L_{Y}f  }{ \partial x^i }(p)$$where: $$\frac{ \partial L_{Y}f }{ \partial x^i } (p)=\sum_{j=1}^{m}\frac{ \partial  }{ \partial x^i }  \left( Y_{j}\cdot \frac{ \partial f }{ \partial x^j }  \right)(p)=\sum_{j=1}^{m}\frac{ \partial Y_{j} }{ \partial x^i } (p)\frac{ \partial f }{ \partial x^j }(p)+\sum_{j=1}^{m}Y_{j}(p)\frac{ \partial^{2}f }{ \partial x^i\partial x^j } (p) $$Therefore, $$\begin{align}(L_{X}L_{Y})(f)(p)&=\sum_{i,j=1}^{m}X_{i}(p)\frac{ \partial Y_{j} }{ \partial x^i } (p)\frac{ \partial f }{ \partial x^j }(p)+\sum_{i,j=1}^{m}X_{i}(p)Y_{j}(p)\frac{ \partial^{2}f }{ \partial x^i\partial x^j } (p)\\(L_{Y}L_{X})(f)(p)&=\sum_{i,j=1}^{m}Y_{i}(p)\frac{ \partial X_{j} }{ \partial x^i } (p)\frac{ \partial f }{ \partial x^j }(p)+\sum_{i,j=1}^{m}Y_{i}(p)X_{j}(p)\frac{ \partial^{2}f }{ \partial x^i\partial x^j } (p)\end{align}$$By Schwarz's Theorem, $$L_{[X,Y]}(f)(p)=\sum_{j=1}^{m}\underbrace{ \left( \sum_{i=1}^{m}X_{i}(p)\frac{ \partial Y_{j} }{ \partial x^i } (p)-Y_{i}(p)\frac{ \partial X_{j} }{ \partial x^i }(p)  \right) }_{ =:Z^j(p) } \frac{ \partial f }{ \partial x^j } (p)$$Therefore, $$[X,Y]_{p}=\sum_{j=1}^{m}Z^j(p) \left. \frac{ \partial  }{ \partial x^j } \right| _{p} $$
---