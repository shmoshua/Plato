#Definition #Analysis 

> [!definition]
> Let $X,Y\in \Gamma(\text{T}M)$ be [[Vector Field|smooth vector fields]]. The ***Lie derivative*** of $Y$ with respect to $X$ is $L_{X}Y\in \Gamma(\text{T}M)$ s.t.: $$(L_{X}Y)_{p}:=\left. \frac{d}{dt} \right| _{t=0}(\Phi^t_{X})^{*}(Y)_{p}=\lim_{ t \to 0 } \frac{(\Phi^t_{X})^{*}(Y)_{p}-Y_{p}}{t}\in \text{T}_{p}M$$
>where $\Phi_{X}^t$ denotes the [[flow]].
- **Remark**: $L_{X}Y$ is independent of the choice of flow, because all local flows coincide in the common domain of definition.
- **Remark**: Recall that $\Phi_{X}^{-t}:M\to M$. Therefore, $d_{\Phi^t_{X}(p)}\Phi^{-t}_{X}:\text{T}_{\Phi^t_{X}(p)}M\to \text{T}_{p}M$.
---
##### Properties
> [!lemma] Proposition 1
> For $X,Y,Z\in \Gamma(\text{T}M)$
> 1. $L_{X}Y=[X,Y]$
> 2. $L_{X}Y=-L_{Y}X$
> 3. $L_{X}[Y,Z]=[L_{X}Y,Z]+[Y,L_{X}Z]$
> 4. $L_{[X,Y]}Z=L_{X}L_{Y}Z-L_{Y}L_{X}Z$
> 5. for $f\in C^\infty(M)$, $L_{X}(fY)=(X(f))Y+fL_{X}Y$
> 6. for a diffeomorphism $\varphi:M\to N$, $\varphi_{*}(L_{X}Y)=L_{\varphi_{*}X}(\varphi_{*}Y)$

> [!proof]-
> We have:
> 1. As $\Gamma(\text{T}M)\cong\text{Der }C^\infty(M)$, we only have to check that for all $f\in C^\infty(M)$, $(L_{X}Y)(f)=[X,Y]f$. Let $p\in M$. Then, $$\begin{align}(L_{X}Y)_{p}(f)&=\lim_{ t \to 0 } \frac{1}{t}\left( d\Phi^{-t}_{X}(Y_{\Phi_{X}^t(p)})-Y_{p} \right)(f)\\&=\lim_{ t \to 0 } \frac{Y_{\Phi^t_{X}(p)}(f\circ \Phi_{X}^{-t})-Y_{p}(f)}{t}\end{align}$$
>    By considering $\Phi^t_{X}(p)=\Phi_{X}(t,p)$ and treating $h(t)=f(\Phi_{X}(t,p))$, we have per [[Smooth Function|Hadamard]]: $$f(\Phi_{X}(t,p))=f(p)+t\cdot g(t,p)$$where $g(0,p)=\left. \frac{ \partial  }{ \partial t } \right|_{t=0}f(\Phi_{X}(t,p))=\left. \frac{ \partial  }{ \partial t } \right|_{t=0}f(\Phi_{X}^t(p))=\left. \frac{ \partial  }{ \partial t } \right|_{t=0}f(\gamma_{p}(t))=d_{p}f(X_{p})=X_{p}f$. Hence, $$h(-t)=f-t\cdot g(-t,p)$$
>    
>    Therefore, $$\begin{align}(L_{X}Y)_{p}(f)&=\lim_{ t \to 0 } \frac{Y_{\Phi^t_{X}(p)}(f\circ \Phi_{X}^{-t})-Y_{p}(f)}{t}\\&=\lim_{ t \to 0 } \frac{Y_{\Phi^t_{X}(p)}(f)-Y_{p}(f)}{t}-Y_{\Phi^t_{X}(p)}(g(-t,\cdot ))\\&=\lim_{ t \to 0 } \frac{Y_{\Phi^t_{X}(p)}(f)-Y_{p}(f)}{t}-Y_{p}(Xf)\\&=\left. \frac{ \partial  }{ \partial t }  \right| _{t=0}Y_{\Phi^t_{X}(p)}(f)-Y_{p}(Xf)\\&=X_{p}(Yf)-Y_{p}(Xf)\\&=[X,Y]_{p}(f)\end{align}$$
> 2. $L_{X}Y=[X,Y]=-[Y,X]=-L_{Y}X$.
> 3. $L_{X}[Y,Z]=[X,[Y,Z]]=-[[Y,Z],X]=[[X,Y],Z]+[[Z,X],Y]=[L_{X}Y,Z]+[Y,L_{X}Z]$.
> 4. $L_{[X,Y]}Z=[[X,Y],Z]=-[[Y,Z],X]-[[Z,X],Y]=-[L_{Y}Z,X]+[L_{X}Z,Y]=L_{X}L_{Y}Z-L_{Y}L_{X}Z$.
> 5. for $f\in C^\infty(M)$, $$\begin{align}L_{X}(fY)_{p}(g)&=[X,fY]_{p}(g)\\&=X_{p}(f\cdot Y(g))-f(p)Y_{p}(X(g))\\&=X_{p}(f)Y_{p}(g)+f(p)X_{p}(Y(g))-f(p)Y_{p}(X(g))\\&=X_{p}(f)Y_{p}(g)+f(p)(L_{X}Y)_{p}(g)\end{align}$$
> 6. We have: $$\varphi_{*}(L_{X}Y)=\varphi_{*}[X,Y]=[\varphi_{*}X,\varphi_{*}Y]=L_{\varphi_{*}X}(\varphi_{*}Y)$$per [[Vector Field|Proposition 2]].

---
##### Examples
> [!h] Example 1
> Let $M:=\mathbb{R}^{2}$ and $X,Y\in \Gamma(\text{T}M)$ s.t. $X_{x}=x^1\frac{ \partial  }{ \partial x^1 }+x^2\frac{ \partial  }{ \partial x^2 }$ and $Y_{x}=\frac{ \partial  }{ \partial x^1 }$. Then, 
> 1. $L_{X}Y$

> [!proof]+
> We have that:
> 1. Firstly, $\Phi^t_{X}(x)=\gamma_{x}(t)$ where: $\dot{\gamma}_{x}(t)=X_{\gamma_{x}(t)}=\gamma_{x}(t)$ and $\gamma_{x}(0)=x$. Therefore, $$\Phi^t_{X}(x)=\gamma_{x}(t)=\exp(t)x$$