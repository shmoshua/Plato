#Definition #Analysis #FunctionalAnalysis 

> [!definition]
> Let $\Omega \subseteq \mathbb{R}^n$ be an open set. For $1\leq p<+\infty$ and $k\geq 0$, the ***Sobolev space*** $W^{p,k}(\Omega)$ is defined as: $$W^{p,k}(\Omega):=\{ f:\Omega\to \mathbb{C}|D_{w}^\alpha f\text{ exists for all }\left| \alpha \right|\leq k, D_{w}^\alpha f,f\in L^p(\Omega)  \}$$ with the norm: $$\left\| f \right\| _{p,k}:=\sum_{\left| \alpha \right| \leq k}^{}\left\| D^\alpha_{w}f \right\|_{p} $$where $D^\alpha_{w}f$ denotes the [[Analysis/Weak Derivative|weak derivative]] of $f$. 
- **Remark**: $W^{2,k}(\Omega)$ is a [[Hilbert Space|Hilbert space]]: for $f_{1},f_{2}\in W^{2,k}(\Omega)$, $$\braket{ f_{1} , f_{2} } :=\sum_{\left| \alpha \right| \leq k}^{}\braket{ D_{w}^\alpha f_{1} ,D_{w}^\alpha f_{2}  } $$which induces the norm: $$\left\| f \right\| =\left( \sum_{\left| \alpha \right| \leq k}^{} \left\| D_{w}^\alpha f \right\| ^2_{2}\right)^{1/2}=\left\| f \right\| _{2,k}$$
- **Related definition**: $C_{p,k}^\infty(\Omega):=\{ f\in C^\infty(\Omega):\left\| D^\alpha f \right\|_{p}<+\infty, \forall \left| \alpha \right|\leq k \}=C^\infty(\Omega)\cap W^{p,k}(\Omega)$
---
##### Properties
> [!lemma] Proposition 1
> $W^{p,k}(\Omega)$ is a [[Banach space]]. 

> [!proof]-
> Let $(f_{k})_{k}\subseteq W^{p,k}(\Omega)$ be a Cauchy sequence. Then, for all $\alpha$ with $\left| \alpha \right|\leq k$, $$(D^\alpha_{w}f_{k})_{k\geq 1}$$is a Cauchy sequence in $L^p(\Omega)$ and hence has a limit $f^\alpha\in L^p(\Omega)$. Let $f:=f^\alpha$ with $\alpha=(0,\dots,0)$. $$f\in L^p(\Omega)\subseteq L^p_{\text{loc}}(\Omega)\subseteq L^1_{\text{loc}}(\Omega)$$By definition, we have for all $\alpha$, $\left| \alpha \right|\leq k$ and $\varphi\in C_{00}^\infty(\Omega)$: $$\int_{\Omega}^{}  f_{k}D^\alpha \varphi\, dm=(-1)^{\left| \alpha \right| }\int_{\Omega}^{} D^\alpha_{w}f_{k}\varphi \, dm  $$But as $D_{w}^\alpha f_{k}\to f^\alpha$ in $L^p(\Omega)$ and $\varphi\in L^1(\Omega)$ by [[Lp Space|Hölder's inequality]],$$\left| \int_{\Omega}^{} (D^\alpha_{w}f_{k}-f^\alpha)\varphi \, dm  \right| \leq \left\| D^\alpha_{w}f_{k}-f^\alpha \right\| _{p}\left\| \varphi \right\| _{1}$$ Similarly, as $D^0_{w}f_{k}=f_{k}\to f$ in $L^p(\Omega)$ and $D^\alpha\varphi\in C^\infty_{00}(\Omega)\subseteq L^1(\Omega)$, $$\left|  \int_{\Omega}^{} (f_{k}-f)D^\alpha\varphi \, dm \right|\leq \left\| f_{k}-f \right\| _{p}\left\| D^\alpha\varphi \right\|_{1}  $$
> Therefore, $$\begin{align}\int_{\Omega}^{}  fD^\alpha \varphi\, dm=\lim_{ k \to \infty } \int_{\Omega}^{}  f_{k}D^\alpha \varphi\, dm=(-1)^{\left| \alpha \right| }\lim_{ k \to \infty } \int_{\Omega}^{} D^\alpha_{w}f_{k}\varphi \, dm =(-1)^{\left| \alpha \right| } \int_{\Omega}^{} f^\alpha\varphi \, dm \end{align}$$
> Hence, $D^\alpha_{w}f=f^\alpha$ and: $$\left\| f_{k}-f \right\| _{p,k}=\sum_{\left| \alpha \right| \leq k}^{}\left\| D^\alpha_{w}f_{k}-f^\alpha \right\|_{p} $$
---
> [!lemma] Lemma 2
> We have:
> 1. if $f\in W^{p,k}(\Omega)$ and $\left| \alpha \right|+\left| \beta \right|\leq k$, then $D_{w}^\alpha(D_{w}^\beta f)=D_{w}^{\alpha+\beta}f$
> 2. if $f\in W^{p,k}(\Omega)$ and $\varphi\in C_{00}^\infty(\Omega)$, then $\varphi \cdot f\in W^{p,k}(\Omega)$.
> 3. if $f\in W^{p,k}(\mathbb{R}^n)$ and $\varphi\in C_{00}^\infty(\mathbb{R}^n)$, then $\varphi * f\in C_{p,k}^\infty(\mathbb{R}^n)$ and $$D^\alpha(\varphi * f)=\varphi*D^\alpha_{w}f,\quad \forall \left| \alpha \right| \leq k$$

> [!proof]-
> We have: 
> 1. for all $\varphi\in C_{00}^\infty(\Omega)$, $$\begin{align}\int_{\Omega}^{} D_{w}^\alpha(D_{w}^\beta f)\varphi \, dm&=(-1)^{\left| \alpha \right| }\int_{\Omega}^{} D^\beta_{w}f\cdot D^\alpha\varphi \, dm \\&=(-1)^{\left| \alpha \right|+\left| \beta \right|  }\int_{\Omega}^{} f\cdot D^{\alpha+\beta}\varphi \, dm \\&=\int_{\Omega}^{} D_{w}^{\alpha+\beta}f\cdot \varphi \, dm \end{align}$$By [[Analysis/Weak Derivative|uniqueness of weak derivatives]], $$D_{w}^\alpha(D_{w}^\beta f)=D_{w}^{\alpha+\beta}f$$
> 2. If $k=0$, $W^{p,0}(\Omega)=L^p(\Omega)$ and the statement holds. Therefore, we may assume that $k\geq 1$. Let $\psi\in C_{00}^\infty(\Omega)$.$$\begin{align}\int(\varphi \cdot f)\partial_{j}\psi \ dm&=\int f[\partial_{j}(\varphi \cdot \psi)-\psi\partial_{j}\varphi]\ dm\\&=\int f\partial_{j}(\varphi \cdot \psi)dm-\int f\psi\partial_{j}\varphi \ dm\\&=-\int (\partial_{j}^wf)\varphi \cdot \psi\ dm-\int f\psi\partial_{j}\varphi\ dm\\&=-\int[(\partial^w_{j}f)\varphi-f(\partial_{j}\varphi)] \psi\ dm\end{align}$$Since $\partial^w_{j}f\in L^p(\Omega)$ and $f\in L^p(\Omega)$, so is $(\partial^w_{j}f)\varphi-f(\partial_{j}\varphi)$. Hence, $\partial^w_{j}(\varphi \cdot f)$ exists and is in $L^p(\Omega)$, defined as:
> 	$$\partial^w_{j}(\varphi \cdot f)=(\partial^w_{j}f)\varphi-f(\partial_{j}\varphi)$$for all $1\leq j\leq n$. Using recurrence, we get that: $$D^\alpha_{w}(\varphi \cdot f)=\sum_{0\leq\beta\leq\alpha}^{}{\alpha\choose \beta}D^\beta_{w}\varphi \cdot D^{\alpha-\beta}_{w}f$$
> 3. We know that by [[Convolution|Proposition 4]], $\varphi*f\in C^\infty(\mathbb{R}^n)$. Further, $\varphi*D^\alpha_{w}f\in L^p$ for all $|\alpha|\leq k$. Therefore, it suffices to show that: $$D^\alpha_{w}(\varphi*f)=\varphi*D^\alpha_{w}f$$As we have for all $\psi\in C^{\infty}_{00}(\mathbb{R}^n)$: $$\begin{align}\int_{\mathbb{R}^n}^{} (\varphi*D^\alpha_{w}f)\psi \ dm&=\int_{\mathbb{R}^n}^{} \int_{\mathbb{R}^n} \varphi(x-t)D^\alpha_{w}f(t)\psi(x)  \, dm(t) dm(x) \\&=\int_{\mathbb{R}^n}^{} \int_{\mathbb{R}^n} \hat{\varphi}(t-x)D^\alpha_{w}f(t)\psi(x)  \, dm(t) dm(x) \\&=\int (D^\alpha_{w}f)(\hat{\varphi}*\psi)\ dm \\&= (-1)^{\left| \alpha \right| }\int fD^\alpha(\hat{\varphi}*\psi)\ dm\\&= (-1)^{\left| \alpha \right| }\int f(\hat{\varphi}*D^\alpha\psi)\ dm   \\&= (-1)^{\left| \alpha \right| }\int (\varphi*f)D^\alpha\psi \ dm\\&=\int D^\alpha_{w}(\varphi*f)\psi  \end{align} $$where $\hat{\varphi}(t)=\varphi(-t)$ and uniqueness
---
> [!lemma] Proposition 3
> For $1\leq p<+\infty$, $C^\infty_{p,k}(\mathbb{R}^n)$ is dense in $W^{p,k}(\mathbb{R}^n)$. 

> [!proof]-
> For an [[approximate identity]] $\delta$ and let $f\in W^{p,k}(\mathbb{R}^n)$. By Lemma 2, $\delta_{\varepsilon}*f\in C^\infty_{p,k}(\Omega)$ for all $\varepsilon>0$ and $$D^\alpha(\delta_{\varepsilon}*f)=\delta_{\varepsilon}*D^\alpha_{w}f$$for all $\left| \alpha \right|\leq k$. By [[Approximate Identity|Proposition 2]], $$\delta_{\varepsilon}*D^\alpha_{w}f\xrightarrow{\varepsilon\to 0}D^\alpha_{w}f$$in $L^p(\mathbb{R}^n)$ and $D^\alpha(\delta_{\varepsilon}*f)\to D^\alpha_{w}f$ in $L^p(\mathbb{R}^n)$.
---
> [!lemma] Theorem 4 (Sobolev Embedding Theorem)
> If $f\in W^{2,k}(\mathbb{R}^n)$ and $k>r + n / 2$, then $f\in C^r_{b}(\mathbb{R}^n)$, i.e. there exists a function $g\in C^r_{b}(\mathbb{R}^n)$ s.t. $f=g$ $m$-a.e. Moreover, the inclusion $$W^{2,k}(\mathbb{R}^n)\hookrightarrow C^r_{b}(\mathbb{R}^n)$$ is a bounded operator.

> [!proof]+
> By [[Fourier Transform|Lemma 8]], $\xi^\alpha \hat{f}\in L^2(\mathbb{R}^n)$ for all $\left| \alpha \right|\leq k$. To show that $f\in C^r_{b}(\mathbb{R}^n)$, it suffices to show that $$\xi^\alpha \hat{f}\in L^1(\mathbb{R}^n)$$for all $\left| \alpha \right|\leq r$. We can write: $$\xi^\alpha \hat{f}=h_{1}\cdot h_{2,\alpha}$$ where:
> 1. $h_{1}:=(1+\left\| \xi \right\|^k)\hat{f}$
> 2. $h_2:= \frac{\xi^\alpha}{1+\left\| \xi \right\|^k}$
> 
> Now, let's show that $h_{1}, h_{2,\alpha}\in L^2(\mathbb{R}^n)$. 