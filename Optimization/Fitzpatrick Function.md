#Definition #Optimization 

> [!definition]
> Let $A:X\to 2^{X^{*}}$. The ***$n$-th order Fitzpatrick function*** of $A$ is given as: $$\begin{array}{rccl}F_{A,n}:&X\times X^{*}&\to &\mathbb{R} \cup \{ \infty \},\\&\quad (x,x^{*})&\mapsto&\sup_{\{ (a_{i},a_{i}^{*}) \}_{i\in[n-1]}\subseteq \text{graph}(A)}\braket{ x-a_{n-1} , a_{n-1}^{*} } + \sum_{i=1}^{n-2} \braket{ a_{i+1}-a_{i} , a_{i}^{*} } +\braket{ a_{1},  x^{*}}\end{array}$$

- **Remark**: For $n=2$, $F_{A,2}(x,x^{*})=\sup_{{(a,a^{*})}\in \text{gra }A}\braket{ x,a^{*} }+\braket{ a , x^{*} }-\braket{ a , a^{*} }$
---
##### Properties
> [!lemma] Proposition 1 
> Let $A:X\to 2^X$. Then, TFAE:
> 1. $A$ is $n$-cyclically monotone.
> 2. $F_{A,n}\leq \braket{ \cdot , \cdot }$ on $\text{graph}(A)$.
> 3. $F_{A,n}= \braket{ \cdot , \cdot }$ on $\text{graph}(A)$.

---
##### Examples
> [!h] Example 1 (Indicator Function)
> Let $X$ be a real Hilbert space and $C\subseteq X$ is a non-empty, closed, convex set. For $f:= \iota _C$:
> 1. $F_{\partial f,2}(x,x^{*})=\iota_{C}(x)+\iota_{C}^{*}(x^{*})$.

> [!proof]-
> We have that: 
> $$\partial f(x)=\begin{cases}\{ v\in X:\braket{ v , z-x } \leq 0,\forall z\in C \}&x\in C\\\varnothing&x\notin C\end{cases}$$Then, let $(y,y^{*})\in X\times X$.  We have that: $$\begin{aligned}F_{\partial f,2}(y,y^{*})&=\sup_{a\in C,a^{*}\in \partial f(a)}\braket{ y , a^{*} } +\braket{ a , y^{*} } -\braket{ a , a^{*} } \end{aligned}$$
> 1. If $y\in C$, then for any $a\in C$ and $a^{*}\in \partial f(a)$, we have $\braket{ y-a , a^{*} }\leq 0$. As $0\in \partial f(a)$, we have that $\sup_{a^{*}\in \partial f(a)}\braket{ y-a , a^{*} }=0$. Hence, $$F_{\partial f,2}(y,y^{*})=\sup_{a\in C}\braket{ a , y^{*} }=\iota_{C}(y)+\iota^*_{C}(y^{*}) $$
> 2. If $y\notin C$, then $y-P_{C}(y)\in \partial f(P_{C}(y))$ and as $\alpha(y-P_{C}(y))\in \partial f(P_{C}(y))$ for all $\alpha> 0$, we have that: $F_{\partial f,2}(y,y^{*})=+\infty$. This proves the statement.

---
> [!h] Example 2
> Let $X$ be a real Hilbert space. For $f:=\left\| \cdot \right\|$:
> 1. $F_{\partial f,2}(y,y^{*})=\begin{cases}\left\| y \right\|&\text{if }\left\| y^{*} \right\|\leq 1\\+\infty&\text{otherwise}\end{cases}$

> [!proof]-
> We have that:
> 1. We have that $g:= f^{*}$ is given by: $$g(x^{*})=\sup_{x\in X}\braket{ x , x^{*} } -\|x\|=\iota_{B_{\leq 1}(0)}(x^{*})$$Indeed, if $\left\| x^{*} \right\|_{*}\leq 1$, then $\braket{ x , x^{*} }\leq \|x\|$ and $g(x^{*})=\sup\braket{ x , x^{*} }-\|x\|\leq 0$ where the supremum is admitted by $x=0$.
> 2. If $\left\| x^{*} \right\|>1$, by definition of dual norm, there exists $u$ with $\|u\|\leq 1$ s.t. $\braket{ u , x^{*} }=\|x^{*}\|_{*}$. Now, $$g(x^{*})\geq t\braket{ u , x^{*} }-t\| u\|\geq t(\|x^{*}\|_{*}-1),\quad \forall t>0 $$Hence, $g(x^{*})=+\infty$.
> 
> Therefore, $$\begin{aligned}F_{\partial f,2}(y,y^{*})&=(F_{(\partial f)^{-1},2}\circ R)(y,y^{*})=F_{\partial g ,2}(y^{*},y)=g(y^{*})+g^{*}(y)=f(y)+f^{*}(y^{*})\end{aligned}$$

---
> [!h] Example 3
> Consider the negative entropy function: $$f:\mathbb{R}\to \mathbb{R}\cup \{ +\infty \},\quad \rho\mapsto \begin{cases}+\infty&\rho<0\\0&\rho=0\\\rho \ln(\rho)-\rho&\rho>0\end{cases}$$ 
> Then, $$F_{\partial f,2}(x,x^{*})=\begin{cases}+\infty&x<0\\ \exp(x^{*}-1)&x=0\\ xx^{*}+x\left( W(\kappa)+\frac{1}{W(\kappa)}-2 \right)&x>0\text{ where }\kappa:=xe^{1-x^{*}} \end{cases}$$

> [!proof]-
> We have that: $$f^{*}(x^{*})=\sup_{\rho\geq 0}\rho x^{*}-f(\rho)$$Then, we have that: $$\frac{d}{d\rho}\left( \rho x^{*}-\rho \ln \rho + \rho \right) =x^{*}-\ln \rho = 0$$Hence, $\ln \rho = x^{*}$ and $\rho = \exp(x^{*})$ and: $$f^{*}(x^{*})=\exp(x^{*})x^{*} - \exp(x^{*})x^{*}+\exp(x^{*})=\exp(x^{*})$$
> Now, we have that: 
> 1. for $\rho\leq0$: $\partial f(\rho)=\varnothing$.
> 2. for $\rho>0$: $\partial f(\rho)=\{ \ln \rho \}$.
> 
> Therefore, for $(x,x^{*})\in \mathbb{R}\times \mathbb{R}$: $$F_{\partial f,2}(x,x^{*})=\sup_{\rho> 0}(x\ln\rho +\rho x^{*}-\rho \ln \rho)$$
> 1. if $x=0$, then: $$F_{\partial f,2}(0,x^{*})=\sup_{\rho>0}(\rho x^{*}-\rho \ln\rho)=\sup_{\rho>0}(\rho (x^{*}-1)-f(\rho))=f^{*}(x^{*}-1)=\exp(x^{*}-1)$$
> 2. if $x>0$, then: $$\frac{d}{d\rho}\left( x\ln \rho + \rho x^{*}-\rho \ln \rho \right)=\frac{x}{\rho}+x^{*}-\ln \rho -1 = 0 $$Let $\xi:=\exp(x ^{*}-1+W(x e^{1-x ^{*}}))$. Then, $$\begin{aligned}\ln \xi&=x ^{*}-1+W(x e^{1-x ^{*}})\\&=x ^{*}-1+\frac{x e^{1-x ^{*}}}{e^{W(x e^{1-x ^{*}})}}\\&=x ^{*}-1+\frac{x }{\xi }\end{aligned}$$Hence, $\xi$ is the maximizer of $F_{\partial f,2}(x,x^{*})$ and we have for $\kappa:=xe^{1-x^{*}}$:$$\xi=\frac{e^{x^{*}-1}}{W(\kappa)}W(\kappa)e^{W(\kappa)}=\frac{e^{x^{*}-1}}{W(\kappa)}\kappa=\frac{x}{W(\kappa)}$$ Therefore, $$\begin{aligned}F_{\partial f,2}(x,x^{*})&=x(x^{*}-1+W(\kappa))+\frac{xx^{*}}{W(\kappa)}-\frac{x}{W(\kappa)}(x^{*}-1+W(\kappa))\\&=x(x^{*}-1+W(\kappa))+\frac{x}{W(\kappa)}(1-W(\kappa))\\&=xx^{*}+x\left( W(\kappa)+\frac{1}{W(\kappa)}-2 \right)\end{aligned}$$


$$f(x,y)=\sup_{a,b>0}((x-b)\ln b+(b-a)\ln a+ay)$$


$$f(x,y)=\sup_{a>0}((x-a)\ln a+ay)$$

1. Let $x=0$. Then, define $g(b):=-b\ln b+(b-a)\ln a+ay$. Then, $$g'(b)=-\ln b-1+\ln a = 0$$and $b = a /e$ and $g\left( \frac{a}{e} \right)=- \frac{a}{e}(\ln a -1)+\left( \frac{1}{e}-1 \right)a\ln a +ay=\frac{a}{e}-a\ln a+ay$. Then, $$h'(a)=\frac{1}{e}-\ln a-1+y=0$$and $a=e^{y - 1+1/e}$. Hence, $$h(a)=e^{y -1 + 1/e}$$
	Therefore, $$F_{\partial f,3}(0,x^{*})=\exp\left( x^{*}-1+\frac{1}{e} \right)$$
2. Let $x>0$. Then, $$g'(b)=\frac{x}{b}-1-\ln b+\ln a = 0$$Let $b^{*}:=a\exp\left( W\left( \frac{xe}{a} \right) -1\right)$. Then, $$\begin{aligned}\ln(b^{*})&=\ln(a)+W\left( \frac{xe}{a} \right)-1\\&=\ln(a)+\frac{xe}{ae^{W(xe/a)}}-1\\&=\ln(a)+\frac{x}{b^{*}}-1\end{aligned}$$Then, let $w:= W(xe /a)$. Then, $we^w = xe / a$ and $x=awe^{w-1}$ and $b^{*}=ae^{w-1}$. Further, $\ln b^{*}=\ln a+w-1$Hence, $$g(b^{*})=ae^{w-1}(w-1)(\ln a+w-1)+a(e^{w-1}-1)\ln a+ay$$


$$f(x,y)=\sup_{a,b,c>0}((x-c)\ln c+(c-b)\ln b+(b-a)\ln a+ay)$$



$$z \log z \geq (g+1)z$$

$$\left(x-\frac{x}{w}\right)\ln \frac{x}{w}+\frac{x}{w}(e^{w-1}+x^*-2)+e^{e^{w-1}+x^*-1}$$

$$w\exp\left( \sum_{k=1}^{n-1}T_{k}(w)\right)$$