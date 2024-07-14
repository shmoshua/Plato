#Definition #Analysis 

> [!definition]
> Let $X,Y\in \Gamma(\text{T}M)$ be [[Vector Field|smooth vector fields]]. The ***Lie derivative*** of $Y$ with respect to $X$ is $L_{X}Y\in \Gamma(\text{T}M)$ s.t.: $$(L_{X}Y)_{p}:=\left. \frac{d}{dt} \right| _{t=0}(\Phi^t_{X})^{*}(Y)_{p}=\lim_{ t \to 0 } \frac{(\Phi^t_{X})^{*}(Y)_{p}-Y_{p}}{t}\in \text{T}_{p}M$$
>where $\Phi_{X}^t$ denotes the [[flow]].
- **Remark**: $L_{X}Y$ is independent of the choice of flow, because all local flows coincide in the common domain of definition.
- **Remark**: Recall that $\Phi_{X}^{-t}:M\to M$. Therefore, $d_{\Phi^t_{X}(p)}\Phi^{-t}_{X}:\text{T}_{\Phi^t_{X}(p)}M\to \text{T}_{p}M$.
---
##### Properties
> [!lemma] Lemma 1
> For $X,Y,Z\in \Gamma(\text{T}M)$
> 1. $L_{X}Y=[X,Y]$
> 2. $L_{X}Y=-L_{Y}X$ and $L_{X}Y$ is linear in $X$ and $Y$.
> 3. $L_{X}X=0$.
> 4. $L_{fX}(gY)=fgL_{X}Y+f\cdot Xg\cdot Y-g\cdot Yf\cdot X$.
> 5. $L_{X}[Y,Z]=[L_{X}Y,Z]+[Y,L_{X}Z]$
> 6. $L_{[X,Y]}Z=L_{X}L_{Y}Z-L_{Y}L_{X}Z$
> 7. for $f\in C^\infty(M)$, $L_{X}(fY)=(X(f))Y+fL_{X}Y$
> 8. for a diffeomorphism $\varphi:M\to N$, $\varphi_{*}(L_{X}Y)=L_{\varphi_{*}X}(\varphi_{*}Y)$
> 9. for a local diffeomorphism $\varphi:M\to N$, $\varphi ^{*}(L_{X}Y)=L_{\varphi ^{*}(X)}(\varphi ^{*}(Y))$
> 10. $(X,Y)\mapsto L_{X}Y$ is [[Local Operator|local]], i.e. for $X_{1},X_{2},Y_{1},Y_{2}\in \Gamma(\text{T}M)$ s.t. $X_{1}=X_{2}$ and $Y_{1}=Y_{2}$ on some open $U \subseteq M$, $L_{X_{1}}Y_{1}=L_{X_{2}}Y_{2}$ on $U$.

> [!proof]+
> We have:
> 1. We present two proofs: 
> 	1. **Proof using test functions:**
> 	   As $\Gamma(\text{T}M)\cong\text{Der }C^\infty(M)$, we only have to check that for all $f\in C^\infty(M)$, $(L_{X}Y)(f)=[X,Y]f$. Let $p\in M$. Then, $$\begin{align}(L_{X}Y)_{p}(f)&=\lim_{ t \to 0 } \frac{1}{t}\left( d\Phi^{-t}_{X}(Y_{\Phi_{X}^t(p)})-Y_{p} \right)(f)\\&=\lim_{ t \to 0 } \frac{Y_{\Phi^t_{X}(p)}(f\circ \Phi_{X}^{-t})-Y_{p}(f)}{t}\end{align}$$
> 	   By defining $h(t)=f(\Phi_{X}^t(p))$, we have per [[Smooth Function|Hadamard]]: $$h(t)=h(0)+t\underbrace{ \int_{0}^{1} \left. \frac{ \partial h }{ \partial s }  \right| _{s=t\tau}\, d\tau }_{ =:g(t,p) } $$where $$g(0,p)=\left. \frac{ \partial  }{ \partial t }  \right| _{t=0}f(\Phi_{X}^t(p))=d_{p}f\left( \left. \frac{ \partial  }{ \partial t }  \right| _{t=0}\Phi^t_{X}(p) \right)=d_{p}f(X_{p})=X_{p}f$$ Hence, $(f\circ\Phi ^{-t}_{X})(p)=h(-t)=f(p)-t\cdot g(-t,p)$.
>    
> 	   Therefore, $$\begin{align}(L_{X}Y)_{p}(f)&=\lim_{ t \to 0 } \frac{Y_{\Phi^t_{X}(p)}(f\circ \Phi_{X}^{-t})-Y_{p}(f)}{t}\\&=\lim_{ t \to 0 } \frac{Y_{\Phi^t_{X}(p)}(f)-Y_{p}(f)}{t}-Y_{\Phi^t_{X}(p)}(g(-t,\cdot ))\\&=\lim_{ t \to 0 } \frac{Y_{\Phi^t_{X}(p)}(f)-Y_{p}(f)}{t}-Y_{p}(Xf)\\&=\left. \frac{ \partial  }{ \partial t }  \right| _{t=0}Y_{\Phi^t_{X}(p)}(f)-Y_{p}(Xf)\\&=X_{p}(Yf)-Y_{p}(Xf)\\&=[X,Y]_{p}(f)\end{align}$$
> 	2. **Proof using coordinates:**
> 	   Let $Z:=L_{X}Y$. Then, by using coordinates, $$\begin{align}Z^i(p)&=\left. \frac{d}{dt} \right| _{t=0}((d_{p}\Phi^t_{X})^{-1})^i_{j}Y^j(\Phi^t_{X}(x))\\&=\left. \frac{d}{dt} \right| _{t=0}((d_{p}\Phi^t_{X})^{-1})^i_{j}Y^j(\Phi^t_{X}(x))\end{align}$$
> 1. $L_{X}Y=[X,Y]=-[Y,X]=-L_{Y}X$.
> 2. $L_{X}[Y,Z]=[X,[Y,Z]]=-[[Y,Z],X]=[[X,Y],Z]+[[Z,X],Y]=[L_{X}Y,Z]+[Y,L_{X}Z]$.
> 3. $L_{[X,Y]}Z=[[X,Y],Z]=-[[Y,Z],X]-[[Z,X],Y]=-[L_{Y}Z,X]+[L_{X}Z,Y]=L_{X}L_{Y}Z-L_{Y}L_{X}Z$.
> 4. for $f\in C^\infty(M)$, $$\begin{align}L_{X}(fY)_{p}(g)&=[X,fY]_{p}(g)\\&=X_{p}(f\cdot Y(g))-f(p)Y_{p}(X(g))\\&=X_{p}(f)Y_{p}(g)+f(p)X_{p}(Y(g))-f(p)Y_{p}(X(g))\\&=X_{p}(f)Y_{p}(g)+f(p)(L_{X}Y)_{p}(g)\end{align}$$
> 5. We have: $$\varphi_{*}(L_{X}Y)=\varphi_{*}[X,Y]=[\varphi_{*}X,\varphi_{*}Y]=L_{\varphi_{*}X}(\varphi_{*}Y)$$per [[Vector Field|Proposition 2]].

---
##### Examples
> [!h] Example 1
> Let $M:=\mathbb{R}^{2}$ and $X,Y\in \Gamma(\text{T}M)$ s.t. $X_{x}=x^1\frac{ \partial  }{ \partial x^1 }+x^2\frac{ \partial  }{ \partial x^2 }$ and $Y_{x}=\frac{ \partial  }{ \partial x^1 }$. Then, 
> 1. $L_{X}Y=-\frac{ \partial  }{ \partial x^1 }$.
> 2. $L_{Y}X=\frac{ \partial  }{ \partial x^1 }$.

> [!proof]-
> We have that:
> 1. Firstly, $\Phi^t_{X}(x)=\gamma_{x}(t)$ where: $\dot{\gamma}_{x}(t)=X_{\gamma_{x}(t)}=\gamma_{x}(t)$ and $\gamma_{x}(0)=x$. Therefore, $$\Phi^t_{X}(x)=\gamma_{x}(t)=\exp(t)x$$Then, $$(\Phi ^{t}_{X})^{*}(Y)_{x}=(d_{x}\Phi^t_{X})^{-1}(Y_{\Phi^t_{X}(x)})=(d_{x}\Phi^t_{X})^{-1}\left( \frac{ \partial  }{ \partial x^1 }  \right)=\exp(-t)\frac{ \partial  }{ \partial x^1 } $$Therefore, $$(L_{X}Y)_{x}=\left. \frac{d}{dt} \right| _{t=0}\exp(-t)\left( \frac{ \partial  }{ \partial x^1 }  \right) =-\left. \frac{ \partial  }{ \partial x^1 } \right| _{x} $$
> 2. On the other hand, $$\Phi^t_{Y}(x)=x+t\frac{ \partial  }{ \partial x^1 } =(x^1+t,x^2)$$Then, $$(\Phi^t_{Y})^{*}(X)_{x}=(d_{x}\Phi^t_{Y})^{-1}(X_{\Phi^t_{Y}(x)})=X_{\Phi^t_{Y}(x)}=\Phi^t_{Y}(x)$$Therefore, $$(L_{Y}X)_{x}=\left. \frac{d}{dt} \right| _{t=0}\Phi^t_{Y}(x)=Y_{\Phi^0_{Y}(x)}=\left. \frac{ \partial  }{ \partial x^1 } \right| _{x} $$