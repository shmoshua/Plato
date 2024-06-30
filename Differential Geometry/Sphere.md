#Definition #DifferentialGeometry 
>[!definition]
>For $n\geq 1$, the ***$n$-sphere*** is given as: $$S^n:=\{ x\in \mathbb{R}^{n+1}:\|x\|=1 \}\subseteq \mathbb{R}^{n+1}$$
---
##### Properties

> [!lemma] Proposition 1 (Atlases on Spheres)
> For $S^n\subseteq \mathbb{R}^{n+1}$, we have that:
> 1. $(U_{j}^\pm,\varphi_{j}^{\pm})$ is a chart where: $U_{j}^+:=\{ x\in S^n:x^j>0 \}$ and $U_{j}^-:=\{ x\in S^n:x^j<0 \}$ with: $$\varphi_{j}^+:U_{j}^+ \to \mathbb{R}^n,\quad x\mapsto(x^0,\dots,\widehat{x^j},\dots,x^{n})$$
> 2. $\{ (U_{N},\varphi_{N}),(U_{S},\varphi_{S}) \}$ where: $U_{N}:=S^n \backslash\{ (0,\dots,0,1) \}$ and $U_{S}:=S^n \backslash\{ (0,\dots,0,-1) \}$ with: $$\varphi_{N}:U_{N}\to \mathbb{R}^n,\quad x\mapsto \frac{(x^0,\dots,\widehat{x^n})}{1-x^n},\quad \varphi_{S}:U_{S}\to \mathbb{R}^n,\quad x\mapsto \frac{(x^0,\dots,\widehat{x^n})}{1+x^n}$$given by ***stereographic projections***.

> [!proof]-
> We have that:
> 1. Firstly, $U_{j}^\pm$ are open. Then, $\varphi_{j}^+(U_{j}^+)=B_{<1}(0)\subseteq \mathbb{R}^{n}$. For $x\in U_{j}^+$, we have: $$\left\| \varphi_{j}^+(U_{j}^+) \right\| ^{2}=\|x\|^{2}-(x^j)^{2}<1$$ Further, for $a:=(a^0,\dots,a^{n-1})\in B_{<1}(0)$, let $\lambda:=\sqrt{ 1-\|a\|^{2} }>0$ and then: $$\varphi^+_{j}(a^0,\dots,a^{j-1},\lambda,a^j,...,a^{n-1})=a$$
> 	One easily sees that this is an injection as $x^j>0$. Therefore, $\varphi_{j}^+$ is bijective to its image and one easily sees that it is a homeomorphism. Further, to see that it is a smooth atlas for $j,k$, for $a\in\varphi^+_{k}(U_{j}^+\cap U_{k}^+)$:  $$\begin{align}\varphi_{j}^+(\varphi_{k}^+)^{-1}(a)&=\varphi_{j}^+(a^0,\dots,a^{k-1},\sqrt{ 1-\|a\|^{2} },a^k,\dots,a^{n-1})\\&=(a^0,\dots,\widehat{a^j},\dots,a^{k-1},\sqrt{ 1-\|a\|^{2} },a^k,\dots,a^{n-1})\end{align}$$which is smooth.
> 2. We have that $U_{N}$ is open. Then, $\varphi_{N}(U_{N})=\mathbb{R}^n$ with the inverse defined as: $$\varphi ^{-1}_{N}(y)=\frac{(2y^0,\dots,2y^{n-1},\left\| y \right\| ^{2}-1)}{\left\| y \right\| ^{2}+1}$$Then, $$\varphi_{S}(\varphi_{N})^{-1}(y)=\varphi_{S}\left( \frac{(2y^0,\dots,2y^{n-1},\left\| y \right\| ^{2}-1)}{\left\| y \right\| ^{2}+1} \right) =\frac{y}{\left\| y \right\| ^{2}}$$which is smooth.
---
