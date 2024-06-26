#Definition #Analysis 

> [!definition]
> Let $f\in C^\infty(\mathbb{R}^m,\mathbb{R}^n)$ and $p,v\in \mathbb{R}^m$. Then, the ***directional derivative*** of $f$ at $p$ along $v$ is given by: $$D_{v}f(p)=d_{p}f(v)=df(p)(v)=\sum_{i=1}^{n}\sum_{j=1}^{m}\left. \frac{ \partial f^i }{ \partial x^j } \right| _{p}v^je_{i} $$
- **Related definition**: Let $X,Y$ be vector fields on $U\subseteq \mathbb{R}^n$ open. Then, $D_{X}Y(p):=D_{X(p)}Y(p)=d_{p}Y(X_{p})$ and $D_{X}Y$ is another vector field. 
- **Related definition**: Let $X,Y:M\to \mathbb{R}^n$ be smooth vector fields for $M\subseteq \mathbb{R}^n$. Then, there exists smooth extensions $\tilde{X},\tilde{Y}:U\to \mathbb{R}^n$ for open $U\supseteq M$. Then, for $p\in M$, $D_{X}Y(p)=D_{\tilde{X}}\tilde{Y}(p)$. 
---
##### Properties
> [!lemma] Proposition 1
> Let $X,Y:M\to \mathbb{R}^n$ be smooth vector fields. Then, 
> 1. $D_{X}Y$ is well-defined, i.e. it is independent of the extension $\tilde{X},\tilde{Y}$. 

> [!proof]-
> We have that $D_{X}Y(p)=D_{\tilde{X}}\tilde{Y}(p)$ only depends on $\tilde{X}(p)=X(p)$ and $\tilde{Y}$. We have that: $$D_{\tilde{X}}\tilde{Y}(p)=d_{p}Y({\tilde{X}_{p}})=\left. \frac{d}{dt} \right| _{t=0}\tilde{Y}(\gamma(t))$$for any $\gamma:I\to M$ with $\gamma(0)=p$ and $\dot{\gamma}(0)=\tilde{X}_{p}=X_{p}$. Therefore, it only depends on $\tilde{Y}|_{\gamma(I)}=Y|_{\gamma(I)}$. 
---
