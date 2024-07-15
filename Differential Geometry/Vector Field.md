#Definition #DifferentialGeometry 
> [!definition]
> A (smooth) ***vector field*** $X$ on a [[smooth manifold]] $M$ is a (smooth) [[Vector Bundle|section]] $X:M\to \text{T}M$ of the [[tangent bundle]], i.e. for all $p\in M$, $X_{p}\in \text{T}_{p}M$.

- **Remark**: A vector field is a section of the tangent bundle and therefore, 
	1. $\Gamma(\text{T}M)$ denotes the space of all smooth vector fields.
- **Remark**: $\Gamma(\text{T}M)$ is also a $C^\infty(M)$-module, where $(fX)(p)=f(p)X_{p}$ for all $p\in M$.
- **Remark**: Let $(U,\varphi)$ be a chart of $M$ at $p\in U$. Then, any vector field $X$ can be represented as: $$X_{p}:=\sum_{i=1}^{m}X^i(p)\left.  \frac{ \partial  }{ \partial x^i } \right|_{p}  $$on $U$ with $X^i:U\to \mathbb{R}$. We also write: $X=\sum_{i=1}^{m}X^i\cdot \frac{ \partial  }{ \partial x^i }$.
- **Related definition**: Let $\varphi\in C^\infty(M,N)$. $X\in \Gamma(\text{T}M)$ and $Y\in \Gamma(\text{T}N)$ are ***$\varphi$-related*** if $d\varphi \circ X=Y\circ\varphi$ i.e. $Y_{\varphi(p)}=d_{p}\varphi(X_{p})$ for all $p\in M$.
- **Related definition**: Let $G$ be a [[Lie group]] and $M$ a smooth manifold with a smooth [[group action]] $G\times M\to M$, i.e. $L:G\to \text{Diffeo}(M)$. Then, $X\in \Gamma(\text{T}M)$ is ***$G$-invariant*** if for all $g\in G$, $(L_{g})_{*}X=X$ per Proposition 2.
---
##### Properties

> [!lemma] Proposition 1 
> Let $X$ be a vector field on $M$. Then, the following are equivalent:
> 1. $X$ is smooth.
> 2. For $(U,\varphi)$ chart at $p\in M$ with $x^1,\dots,x^m$ coordinate functions, $$X|_{U}=X^i\cdot \frac{ \partial  }{ \partial x^i } $$where $X^i\in C^\infty(U)$.
> 3. For $V\subseteq M$ open and $f\in C^\infty(V)$, $X(f)\in C^\infty(V)$.

> [!proof]-
> We have:
> 1. (1=>2): If $X$ is smooth, then $X|_{U}$ is smooth. Therefore, for any $p\in U$, $$dx^i(X_{p})=X^j(p) \left. \frac{ \partial x^i }{ \partial x^j } \right| _{p}=X^j(p)\delta_{j}^i=X^i(p) $$Hence, $dx^i\circ X|_{U}=X^i$ which is smooth.
> 2. (2=>3): Let $(U,\varphi)$ be a chart s.t. $U\subseteq V$. Then, $$X(f)|_{U}=X^i\cdot \frac{ \partial f }{ \partial x^i } $$Therefore, $X(f)|_{U}$ is a smooth function and $X(f)\in C^\infty(V)$.
> 3. (3=>1): It suffices to show that $X|_{U}$ is smooth for any chart $(U,\varphi)$ and $p\in U$,$$dx^i(X_{p})=(x^i(p),X_{p}(x^i))$$Therefore, $dx^i \circ X|_{U}=(x^i,X(x^i))$ which is smooth and $X|_{U}$ is smooth.
> 
---
![[Derivation#^5fac5a|hihi]]
![[Derivation#^c79513|p]]

---
> [!lemma] Proposition 2 (Vector fields are local)
> We have that:
> 1. $\Gamma(\text{T}M)\times C^\infty(M)\to C^\infty(M), (X,f)\mapsto Xf$ is [[Local Operator|local]] in each variable.
> 2. $\Gamma(\text{T}M)\times \Gamma(\text{T}M)\to \Gamma(\text{T}M), (X,Y)\mapsto [X,Y]$ is [[Local Operator|local]] in each variable.
> 3. For $X\in \Gamma(\text{T}M)$, $C^\infty(M)\to C^\infty(M),f\mapsto Xf$ is a [[differential operator]] of order $1$.

> [!proof]-
> We have:
> 1. For $U\subseteq M$ open and let $X,Y\in \Gamma(\text{T}M)$ s.t. $X|_{U}=Y|_{U}$. For $p\in U$ let $(V,\varphi)$ be a chart at $p$ s.t. $V\subseteq U$. Then, $X|_{V}=Y|_{V}$ and for any $f\in C^\infty(M)$, $X_{p}f=Y_{p}f$ for $p\in U$.
>    
>    Further, for $f,g\in C^\infty(M)$ with $f|_{U}=g|_{U}$, we have that for $p\in U$ a chart $(V,\varphi)$ with $V\subseteq U$ and: $$X_{p}f=\sum_{i=1}^{m}X^i_{p}\cdot \left. \frac{ \partial f }{ \partial x^i }  \right| _{p}=\sum_{i=1}^{m}X^i_{p}\cdot \left. \frac{ \partial g }{ \partial x^i }  \right| _{p}=X_{p}g$$
> 2. Let $X,Y\in \Gamma(\text{T}M)$ and $X|_{U}=Y|_{U}$ where $U\subseteq M$ open. Then, for $Z\in \Gamma(\text{T}M)$, $f\in C^\infty(M)$ and $p\in U$, $$[X,Z]_{p}f=X_{p}(Zf)-Z_{p}(Xf)=Y_{p}(Zf)-Z_{p}(Yf)=[Y,Z]_{p}f$$
> 3. Let $(U,\varphi)$ be a chart of $M$. Then, for $p\in U$, $$X_{p}f=\sum_{i=1}^{m}X^i(p)\left. \frac{ \partial f }{ \partial x^i }  \right| _{p}$$
---
> [!lemma] Theorem 3 (Straightening Vector Fields)
> Let $X\in \Gamma(\text{T}M)$ and $p\in M$. If $X_{p}\neq 0$, then 
> 1. there exists a chart $(U,\varphi)$ around $p$ s.t. $X|_{U}=\frac{ \partial  }{ \partial x^1 }$.

> [!proof]-
> Since $X_{p}\neq 0$, there exists a chart $(U,\varphi)$ at $p$ s.t. $X_{p}=\frac{ \partial  }{ \partial x^1 }|_{p}$. Modulo reducing $U$, there exists $\delta>0$ s.t. for the flow $\Phi_{X}:(-\delta,\delta)\times U\to M$: $$\Phi_{X}(t,q)=\varphi ^{-1}(\Phi^1(t,q),\dots,\Phi^m(t,q)),\quad \forall q\in U$$Let $N:=\{ q\in U :x^1(q)=0\}\ni p$. Then $N$ is a $m-1$ dimensional submanifold of $M$. We define: $\Psi:=\Phi|_{(-\delta,\delta)\times N}$.  Then, clearly $\Psi$ is smooth. Further, at $(0,p)$, $$d_{(0,p)}\Psi \left( \left. \frac{ \partial  }{ \partial t }  \right| _{(0,p)} \right)=\left. \frac{ \partial f\circ \Psi }{ \partial t }  \right|_{(0,p)}=\left. \frac{ \partial f\circ \Phi }{ \partial t } \right| _{(0,p)}=d_{p}f(\dot{\gamma}_{p}(0))=X(\gamma_{p}(0))(f)=X_{p}(f)=\left. \frac{ \partial  }{ \partial x^1 }  \right| _{p}f $$And for $i\geq 2$, 
> 
> $$\begin{align}d_{(0,p)}\Psi \left( \left. \frac{ \partial  }{ \partial x^i }  \right| _{(0,p)} \right)f &=\left. \frac{d}{dt} \right| _{t=0}f(\Psi((0,p)+t(0,\varphi ^{-1}(e_{i}))))\\&=\left. \frac{d}{dt} \right| _{t=0}f(\Phi(0,p+t\varphi ^{-1}(e_{i})))\\&=\left. \frac{d}{dt} \right| _{t=0}f(p+t\varphi ^{-1}(e_{i}))\\&=d_{p}f\left( \left. \frac{ \partial  }{ \partial x^i }  \right| _{p} \right)\\&= \left. \frac{ \partial  }{ \partial x^i }  \right| _{p} f \end{align}$$Therefore, $d_{(0,p)}\Psi$ is a bijection and by [[Local Diffeomorphism|inverse function theorem]],  there exists $(-\varepsilon,\varepsilon)\times V\ni (0,p)$ open in $(-\delta,\delta)\times N$ and $W\subseteq M$ open s.t. $$\Psi:(-\varepsilon,\varepsilon)\times V\to W$$ is a diffeomorphism. Therefore, on $W\subseteq M$, we can define a chart $(\text{id},\varphi ^{-1})\circ\Psi ^{-1}$.
> 
> Now, let $r:=\Psi(t,q)\in W$. Then, $$\begin{align}X_{r}=X(\Psi(t,q))=X(\Phi(t,q))=\left. \frac{ \partial \Phi }{ \partial t } \right| _{(q,t)}=\left. \frac{ \partial \Psi }{ \partial t } \right| _{(q,t)} =d_{(q,t)}\Psi \left(\left.  \frac{ \partial  }{ \partial t }  \right| _{(q,t)} \right)=\left. \frac{ \partial  }{ \partial x^1 }  \right| _{r} \end{align}$$

- **Remark**: This implies that any non-zero vector fields are locally invariant. 
---
> [!lemma] Lemma 4 (Pushforward Vector Fields)
> Let $\phi\in C^\infty(M,N)$ and $\psi^\infty(N,P)$. Then, for $X\in \Gamma(\text{T}M),Y\in \Gamma(\text{T}N)$,$Z\in \Gamma(\text{T}P)$,
> 1. $\phi ^{*}(\phi_*(X)f)=X(\phi ^{*}(f))$ 
> 2. $\phi ^{*}(Y)(\phi ^{*}(f))=\phi ^{*}(Yf)$
> 3. $\phi ^{*}(\phi_{*}(X))=X$
> 4. $\phi_{*}(\phi ^{*}(Y))=Y$
> 5. $(\psi \circ\phi)_{*}(X)=\psi_{*}(\phi_{*}(X))$
> 6. $(\psi \circ\phi)^{*}(Z)=\phi ^{*}(\psi ^{*}(Z))$
> 7. $(\phi ^{-1})_{*}(Y)=\phi ^{*}(Y)$
> 8. $(\phi ^{-1})^{*}(X)=\phi_{*}(X)$
> 9. $\phi_{*}(Xf)=\phi_{*}(X)\phi_{*}(f)$
> 10. $\phi ^{*}(Yg)=\phi ^{*}(Y)\phi ^{*}(g)$
> 11. $\phi_{*}([X_{1},X_{2}])=[\phi_{*}(X_{1}),\phi_{*}(X_{2})]$
> 12. $\phi ^{*}([Y_{1},Y_{2}])=[\phi ^{*}(Y_{1}),\phi ^{*}(Y_{2})]$

> [!proof]- 
> We have: 
> 1. $$\begin{align}\phi ^{*}(\phi_{*}(X)f)(p)=\phi_{*}(X)f(\phi(p))=d_{p}\phi(X_{p})f=X_{p}(f\circ \phi)=X_{p}(\phi ^{*}(f))\end{align}$$
> 2.  $$\phi ^{*}(Y)(\phi ^{*}(f))_{p}=(d_{p}\phi)^{-1}(Y_{\phi(p)})(f\circ\phi )=(d_{p}\phi)(d_{p}\phi)^{-1}(Y_{\phi(p)})f=Y_{\phi(p)}f$$
> 3. $$\phi ^{*}(\phi_{*}(X))_{p}=(d_{p}\phi)^{-1}(\phi_{*}(X)_{\phi(p)})=(d_{p}\phi)^{-1}(d_{p}\phi(X_{p}))=X_{p}$$
> 4. $$\phi_{*}(\phi ^{*}(Y))_{q}=d\phi(\phi ^{*}(Y)_{\phi ^{-1}(q)})=Y_{q}$$
> 5. We have: $$\begin{align}(\psi \circ \phi)_{*}(X)_{p}&=d_{(\psi \circ \phi)^{-1}(p)}(\psi \circ \phi)(X_{(\psi \circ \phi)^{-1}(p)})\\&=d_{\psi ^{-1}(p)}\psi \cdot d_{\phi ^{-1}(\psi ^{-1}(p))}\phi(X_{\phi ^{-1}(\psi ^{-1}(p))})=d_{\psi ^{-1}(p)}\psi(\phi_{*}(X)_{\psi ^{-1}(p)})=\psi_{*}(\phi_{*}(X))_{p}\end{align}$$
> 6. We have: $$\begin{align}(\psi \circ \phi)^{*}(X)_{p}&=(d_{p}(\psi \circ \phi))^{-1}(X_{\psi(\phi(p))})=(d_{p}\phi)^{-1}(d_{\phi(p)}\psi)^{-1}(X_{\psi(\phi(p))})\\&=(d_{p}\phi)^{-1}(\psi ^{*}(X)_{\phi(p)})=\phi ^{*}(\psi ^{*}(X))_{p}\end{align}$$
> 7. We have: $$(\phi ^{-1})_{*}(Y)_{q}=d_{\phi(q)}\phi ^{-1}(Y_{\phi(q)})=(d_{q}\phi)^{-1}(Y_{\phi(q)})=\phi ^{*}(Y)_{q}$$
> 8. $$(\phi ^{-1})^{*}(X)_{p}=(d_{p}\phi ^{-1})^{-1}(X_{\phi ^{-1}(p)})=d_{\phi ^{-1}(p)}\phi(X_{\phi ^{-1}(p)})=\phi _{*}(X)_{p}$$
> 9. We have: $$\phi_{*}(X)_{q}\phi_{*}(f)=d_{\phi ^{-1}(q)}\phi(X_{\phi ^{-1}(q)})(f\circ \phi ^{-1})=X_{\phi ^{-1}(q)}(f)=\phi_{*}(Xf)_{q}$$
> 10. and $$\phi ^{*}(Y)_{p}\phi ^{*}(g)=(d_{p}\phi)^{-1}(Y_{\phi(p)})(g\circ \phi)=Y_{\phi(p)}g=\phi ^{*}(Yg)$$
> 11. Analogous to 12.
> 12. Similarly, we have: $$\begin{align}\phi ^{*}([Y_{1},Y_{2}])f&=\phi ^{*}([Y_{1},Y_{2}])\phi ^{*}(g)\\&=\phi ^{*}([Y_{1},Y_{2}]g)\\&=\phi ^{*}(Y_{1}Y_{2}g-Y_{2}Y_{1}g)\\&=\phi ^{*}(Y_{1}Y_{2}g)-\phi ^{*}(Y_{2}Y_{1}g)\\&=\phi ^{*}(Y_{1})\phi ^{*}(Y_{2})f-\phi ^{*}(Y_{2})\phi ^{*}(Y_{1})f\\&=[\phi ^{*}(Y_{1}),\phi ^{*}(Y_{2})]f\end{align}$$
---
> [!lemma] Proposition 5 (Related Vector Fields)
> Let $\varphi\in C^\infty(M,N)$.
> 1. $X\in \Gamma(\text{T}M)$ and $Y\in \Gamma(\text{T}N)$ are $\varphi$-related if and only if the following diagram commutes: $$\begin{CD}C^\infty(N) @>\varphi ^{*}>>C^\infty(M)\\ @V YVV&@VV XV\\C^\infty(N) @>\varphi ^{*}>>C^\infty(M)\end{CD}$$
> 2. Let $X,Y\in \Gamma(\text{T}M)$ and $X',Y'\in \Gamma(\text{T}N)$ s.t. $X$ and $X'$ and $\varphi$-related and $Y$ and $Y'$ are $\varphi$-related. Then, $[X,Y]$ is $\varphi$-related to $[X',Y']$.
> 3. If $\varphi$ is a diffeomorphism, then $\varphi_{*}(X)\in \Gamma(\text{T}N)$ is the unique vector field $\varphi$-related to $X$. In this case, $\varphi ^{*}\circ\varphi_{*}(X)=X\circ\varphi ^{*}$.

> [!proof]-
> We have:
> 1. $\varphi ^{*}(1)=1$ and: $$\varphi ^{*}(fg)=fg\circ \varphi=(f\circ \varphi)(g\circ \varphi)=\varphi ^{*}(f)\varphi ^{*}(g)$$
> 3. if $X$ and $Y$ are $\varphi$-related, for $f\in C^\infty(N)$ and $p\in M$: $$\begin{align}\alpha X(\varphi ^{*}(f))(p)&=\alpha X(f\circ \varphi)(p)=X_{p}(f\circ \varphi)=d_{p}(f\circ \varphi)(X_{p})\\&=d_{\varphi(p)}f(d_{p}\varphi(X_{p}))=d_{\varphi(p)}f(Y_{\varphi(p)})=Y_{\varphi(p)}(f)=Y(f)(\varphi(p))=\varphi ^{*}(\alpha Y(f))(p)\end{align}$$
>    Conversely, if the diagram commutes, $$d_{p}\varphi(X_{p})(f)=X_{p}(f\circ \varphi)=\alpha X(\varphi ^{*}(f))(p)=\varphi ^{*}(\alpha Y(f))(p)=\alpha Y(f)(\varphi(p))=Y_{\varphi(p)}(f)$$
> 4. We have: $$\begin{align}\varphi ^{*}\circ  \alpha[X',Y']&=\varphi ^{*}\circ \alpha X'\circ \alpha Y'-\varphi ^{*}\circ \alpha Y'\circ \alpha X'\\&=\alpha X\circ \varphi ^{*}\circ \alpha Y'-\alpha Y\circ \varphi ^{*}\circ \alpha X'\\&=\alpha X\circ \alpha Y\circ \varphi ^{*}-\alpha Y\circ \alpha X\circ \varphi ^{*}\\&=\alpha[X,Y]\circ \varphi ^{*}\end{align}$$Therefore, they are $\varphi$-related by 2. 
> 5. If $\varphi$ is a diffeomorphism, $\varphi ^{-1}\in C^\infty(N,M)$ and $(\varphi ^{-1})^{*}:C^\infty(M)\to C^\infty(N)$ s.t. $$\varphi ^{*}\circ (\varphi ^{-1})^{*}=\text{id}_{C^\infty(M)}$$The rest is immediate by 2. 
- **Corollary**: For a diffeomorphism $\varphi\in C^\infty(M,N)$, $\varphi_{*}:\Gamma(\text{T}M)\to\Gamma(\text{T}N)$ is a Lie algebra homomorphism by 3. 
---
![[Flow#^0d5b4f]]
![[Flow#^35997d|p]]

---
> [!lemma] Theorem 6 (Straightening Vector Fields II)
> Let $X_{1},\dots,X_{m}\in \Gamma(\text{T}M)$ pairwisely commute, i.e. $[X_{i},X_{j}]=0$ for all $i,j\in [m]$. For $p\in M$,
> 1. if $X_{1}(p),\dots,X_{m}(p)$ are linearly independent, there exists a chart $(U,\varphi)$ s.t. $$X_{i}|_{U}=\frac{ \partial  }{ \partial x^i },\quad \forall i\in[m] $$

> [!proof]-
> Fix $p\in M$ and we define: $$\Psi:V\subseteq \mathbb{R}^m\to M,\quad(t_{1},\dots,t_{m})\mapsto(\Phi^{t_{1}}_{X_{1}}\circ \Phi^{t_{2}}_{X_{2}}\circ \dots \circ \Phi^{t_{m}}_{X_{m}})(p)$$which is smooth, where $V$ is the open set where the local flows are defined. Then, we have that: 
> 	$$\begin{align}d\Psi \left( \left. \frac{ \partial  }{ \partial t^i }  \right| _{t} \right)f &= \left. \frac{ \partial  }{ \partial t^i }  \right| _{t}f(\Psi(t^1,\dots,t^m))\\&= \left. \frac{ \partial  }{ \partial t^i }  \right| _{t}f((\Phi^{t_{1}}_{X_{1}}\circ \Phi^{t_{2}}_{X_{2}}\circ \dots \circ \Phi^{t_{m}}_{X_{m}})(p))\\&=X_{i}((\Phi^{t_{1}}_{X_{1}}\circ \Phi^{t_{2}}_{X_{2}}\circ \dots \circ \Phi^{t_{m}}_{X_{m}})(p))f\end{align}$$Therefore, we have that: $d_{0}\Psi\left(\left.  \frac{ \partial  }{ \partial t^i } \right|_{0} \right)=X_{i}(p)$ and $d_{0}\Psi$ is invertible. Hence, by the inverse function theorem, there exists $W\subseteq V$ open and $U\subseteq M$ open with $p\in U$ s.t. $\Psi|_{W}:W\to U$ is a diffeomorphism. It follows that $(U,(\Phi|_{W})^{-1})$ is a chart.
> 	
> 	Then, $$\Psi_{*}\left( \frac{ \partial  }{ \partial t^i }  \right)_{q}=d\Psi \left(\left.  \frac{ \partial  }{ \partial t^i } \right| _{\Psi ^{-1}(q)}  \right)=X_{i}(\Psi(\Psi ^{-1}(q)))=X_{i}(q) $$This proves the statement.
> 	
---
###### Vector Fields in Rn
> [!lemma] Proposition 1
> Let $M\subseteq \mathbb{R}^n$. Then, 
> 1. $X:M\to \mathbb{R}^3$ is a vector field along $M$. 
> 2. $X:M\to \text{T}M$ is a vector field on $M$.
> 3. $X:M\to \text{T}M\subseteq \mathbb{R}^3$ is smooth if there exists $U\supseteq M$ open s.t. $X$ extends to a smooth function $\tilde{X}:U\to \mathbb{R}^3$. 
---
##### Examples
> [!h] Example 1 (Pushforward and Pullback Vector Fields)
> Let $M,N$ be smooth manifolds with $X\in \Gamma(\text{T}M)$ and $Y\in \Gamma(\text{T}N)$.
> 1. For a diffeomorphism $\phi:M\to N$, the ***pushforward vector field*** is  $\phi_{*}:\Gamma(\text{T}M)\to\Gamma(\text{T}N)$ s.t. $$\phi_{*}(X)_{q}=d\phi(X_{\phi ^{-1}(q)})$$
> 2. For a local diffeomorphism $\phi:M\to N$, the ***pullback*** is $\phi ^{*}:\Gamma(\text{T}N)\to\Gamma(\text{T}M)$ s.t. $$\phi ^{*}(Y)_{p}=(d_{p}\phi) ^{-1}(Y_{\phi(p)})$$
---