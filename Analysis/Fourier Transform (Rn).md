#Definition #FunctionalAnalysis 

> [!definition]
> For $f\in L^1(\mathbb{R}^n,m)$, the ***Fourier transform*** of $f$, denoted as $\mathcal{F}f$ or $\hat{f}$, is defined as: $$\begin{array}{cccc} {\hat{f}:}&{\mathbb{R}^n}&\to&{\mathbb{C}}\\&{\xi} &\mapsto & {\int_{\mathbb{R}^n}^{}f(x)e^{-i\braket{ x , \xi } }  \, dm(x) } \end{array}{}$$where $m=(2\pi)^{-n/2}\mathcal{L}^n$ with $\mathcal{L}^n$ being the [[Lebesgue Measure]]. Similarly, we define the ***inverse Fourier transform*** of $f$, denoted as $\mathcal{F^{*}}f$ or $\tilde{f}$:
> $$\begin{array}{cccc} {\tilde{f}:}&{\mathbb{R}^n}&\to&{\mathbb{C}}\\&{x} &\mapsto & {\int_{\mathbb{R}^n}^{} f(\xi)e^{i\braket{ x,\xi } } \, dm(\xi) } \end{array}{}$$
- **Remark**: For a function $f$ is holds that: $$\tilde{f} = \overline{\widehat{\overline{f}}}$$ as: $$\overline{\widehat{\overline{f}}}(x)=\overline{\int_{\mathbb{R}^n}^{} \overline{f(\xi)}e^{-i\braket{ x , \xi } } \, dm(\xi) }=\int_{\mathbb{R}^n}^{} f(\xi)e^{i\braket{ x , \xi } } \, dm(\xi) $$
---
##### Properties
> [!lemma] Lemma 1
> Let $1\leq p <+\infty$ and $f\in L^p(\mathbb{R}^n)$. We define $(\lambda(x)f)(y)=f(y-x)$ the shift operator. Then, $$\begin{array}{cccc} &{\mathbb{R}^n}&\to&{L^p(\mathbb{R}^n)}\\&{x} &\mapsto & {\lambda(x)f} \end{array}{}$$is continuous.

> [!proof]-
> Notice that $\lambda(x)$ is isometric with respect to the $p$-norm. Therefore, $$\left\| \lambda(x)f-\lambda(y)f \right\|_{p}=\left\| \lambda(x-y)f-f \right\| _{p} $$and we only need to show the continuity at $x=0$. 
> 
> Let $\varphi\in C_{c}(\mathbb{R}^n)$, i.e. $f$ is continuous with compact support. Then, $\text{supp }\varphi \subseteq B_{\leq R}(0)$ for some $R>0$. Let $x\in B_{\leq 1}(0)$. Then, $$\begin{align}\left\| \lambda(x)\varphi-\varphi \right\|^p_{p}&=\int _{\mathbb{R}^n}\left| \varphi(y-x)-\varphi(y) \right| ^p \, dm(y)\\&= \int _{B_{\leq R+1}(0)}\left| \varphi(y-x)-\varphi(y) \right| ^p \, dm(y) \\&\leq \sup_{y\in B_{\leq R+1}(0)}\left| \varphi(y-x)-\varphi(y) \right| ^p\cdot m(B_{\leq R+1}(0))\xrightarrow{x\to 0} 0\end{align}$$as $\varphi$ is uniformly continuous. 
> 
> Now let $f\in L^p(\mathbb{R}^n)$ and $\varepsilon>0$. Then, there exists $\varphi\in C_{00}(\mathbb{R}^n)$ with $\left\| f-\varphi \right\|_{p}<\varepsilon$. (as $C_{c}(\mathbb{R}^n)$) is dense in $L^p(\mathbb{R}^n)$). Then, we also have $\delta>0$ s.t. for all $x\in B_{<\delta}(0)$, $\left\| \lambda(x)\varphi-\varphi \right\|_{p}<\varepsilon$. Therefore, $$\begin{align}\left\| \lambda(x)f-f \right\|_{p}&\leq \left\| \lambda(x)f-\lambda(x)\varphi \right\|_{p}+\left\| \lambda(x)\varphi-\varphi \right\| _{p}+\left\| f-\varphi \right\| _{p}\\&= \left\| f-\varphi\right\|_{p}+\left\| \lambda(x)\varphi-\varphi \right\| _{p}+\left\| f-\varphi \right\| _{p}\\&<3\varepsilon\end{align} $$which proves the statement.
---
> [!lemma] Lemma 2 (Riemann-Lebesgue)
> If $f\in L^1(\mathbb{R}^n)$, then 
> 1. $\hat{f}\in C_{0}(\mathbb{R}^n)$
> 2. the Fourier transform $\mathcal{F}:L^1(\mathbb{R}^n)\to C_{0}(\mathbb{R}^n)$ has $\left\| \mathcal{F} \right\|\leq 1$.

> [!proof]-
> We have:
> 1. **Showing $\hat{f}\in C_{0}(\mathbb{R}^n)$**:
> We have that: $$\hat{f}(\xi+h)-\hat{f}(\xi)=\int_{\mathbb{R}^n}^{}f(x)e^{-i\braket{ x , \xi } }(e^{-i\braket{ x , h } }-1)  \, dm(x) $$Let $\varepsilon>0$ and from [[Summable Function|modulus of integrability ]] let $R>0$ s.t. $\int_{\mathbb{R}^n \backslash B_{\leq R}(0)}^{}\left| f \right|   \, dm<\varepsilon$ Then, $$\begin{align}|\hat{f}(\xi+h)-\hat{f}(\xi)|&\leq\int_{B_{{\leq R}}(0)}^{}\left|f(x)e^{-i\braket{ x , \xi } }(e^{-i\braket{ x , h } }-1) \right| \, dm(x) +\varepsilon\\&\leq\|f\|_{1}\sup_{x\in B_{\leq R}(0)}\left|e^{-i\braket{ x , \xi } }(e^{-i\braket{ x , h } }-1) \right|+\varepsilon\end{align}$$Indeed for a fixed $R$, $e^{-i\braket{ x , h }}-1$ converges uniformly to zero on $B_{\leq R}(0)$ as $h\to {0}$. This shows the continuity. 
> 
>    Furthermore, for all $\xi\in \mathbb{R}^n$,
> $$\left| \hat{f}(\xi) \right| \leq \int_{\mathbb{R}^n}^{} \left| f(x) \right|  \, dm(x)=\left\| f \right\| _{1} $$Therefore, $\left\| \mathcal{F} \right\|\leq 1$. To show that $\lim_{ \|\xi\| \to \infty }\left| f(\xi) \right|=0$, we define the change of variable $x\mapsto x- \frac{\pi\xi}{\|\xi\|^2}$. Then, $$\hat{f}(\xi )=\int_{\mathbb{R}^n}^{} \left[ \lambda\left( \frac{\pi \xi}{\left\| \xi \right\| ^{2}} \right)f \right] (x)e^{-i\braket{ x , \xi } }e^{i\pi} \, dm(x)=-\int_{\mathbb{R}^n}^{} \left[ \lambda\left( \frac{\pi \xi}{\left\| \xi \right\| ^{2}} \right)f \right] (x)e^{-i\braket{ x , \xi } }\, dm(x) $$and $$2\hat{f}(\xi )=\int_{\mathbb{R}^n}^{} \left[f- \lambda\left( \frac{\pi \xi}{\left\| \xi \right\| ^{2}} \right)f \right] (x)e^{-i\braket{ x , \xi } }\, dm(x)$$Therefore, $$2\left| \hat{f}(\xi) \right|\leq \left\| f- \lambda\left( \frac{\pi \xi}{\left\| \xi \right\| ^{2}}\right) f\right\|_{1} $$As $\|\xi\|\to \infty$, $\frac{\pi\xi}{\|\xi\|^{2}}\to{0}$ and by Lemma 1 with $p=1$, we have that $\lim_{ \|\xi\| \to \infty }\left| f(\xi) \right|=0$.
---
> [!lemma] Proposition 3
> We have that:
> 1. for $f\in C_{00}^1(\mathbb{R}^n)$: $$\widehat{\frac{ \partial f }{ \partial x_{j} } }(\xi)=i\xi_{j}\hat{f}(\xi)$$
> 2. for $f\in C_{00}^k(\mathbb{R}^n)$: $$( \widehat{D^\alpha f})(\xi)=i^{|\alpha|}\xi^{\alpha}\hat{f}(\xi)$$
> 3. for $f\in C_{00}^\infty(\mathbb{R}^n)$ and $1\leq p\leq\infty$: $$\hat{f}\in C_{0}(\mathbb{R}^n)\cap L^p(\mathbb{R}^n)$$
> 
> where $\left| \alpha \right|=\alpha_{1}+\dots+\alpha_{n}$, $\xi^\alpha:=\xi_{1}^{\alpha_{1}}\cdot\dots \cdot \xi_{n}^{\alpha_{n}}$ and $D^\alpha f:=\frac{ \partial^{\left| \alpha \right|} f }{ \partial^{\alpha_{1}} x_{1}\dots\partial^{\alpha_{n}}x_{n} }$.

> [!proof]-
> We see that: 
> 1. for $f\in C_{00}^1(\mathbb{R}^n)$:$$\begin{align}\widehat{\frac{ \partial f }{ \partial x_{j} } }(\xi)&=\int_{\mathbb{R}^n}^{} \frac{ \partial f }{ \partial x_{j} }(x)e^{-i\braket{ x , \xi } }  \, dm(x) \\&=-\int_{\mathbb{R}^n}^{} f(x)\frac{ \partial(e^{-i\braket{ x , \xi } }) }{ \partial x_{j} }  \, dm(x)\\\\&=i\xi_{j}\int_{\mathbb{R}^n}^{} f(x)e^{-i\braket{ x , \xi } } \, dm(x)\\&=i\xi_{j}\hat{f}(\xi) \end{align}$$
> 2. Can be shown using recursion. 
> 3. From 2, we get that $\xi^\alpha \hat{f}(\xi)$ is bounded for all $\alpha$ and hence so is: $$\prod_{j\in[n]}^{}(1+\xi_{j}^{2})\hat{f}(\xi)$$However, as $\frac{1}{\prod_{j=1}^{n}(1+\xi^2_{j})}\in L^p(\mathbb{R}^n)$ for all $1\leq p\leq +\infty$.
---
> [!lemma] Lemma 4
> For $f\in L^1(\mathbb{R}^n)$, 
> 1. $(\widehat{\lambda(x)f})(\xi )=e^{-i\braket{ x , \xi }}\hat{f}(\xi)$
> 2. $\lambda(x)\hat{f}(\xi)=\widehat{(e^{i\braket{  x,\cdot }}f)}(\xi)$
> 3. $(\widehat{S_{a}f})(\xi)=a^n S_{1/a}\hat{f}(\xi)$
> 4. $(S_{a}\hat{f})(\xi)=a^n(\widehat{S_{1 / a}f})(\xi)$
> 5. $(\widehat{f*g})(\xi)=(\widehat{f}\cdot\widehat{g})(\xi)$
> 
> where $(S_{a}f)(x)=f(x / a)$ for all $a\neq 0$. 

> [!proof]-
> We have that:
> 1. for $f\in L^1(\mathbb{R}^n)$:$$\begin{align}(\widehat{\lambda(x)f})(\xi)&=\int_{\mathbb{R}^n}^{}f(y-x)e^{-i\braket{ y , \xi } }  \, dm(y)\\&=e^{-i\braket{ x , \xi } }\int_{\mathbb{R}^n}^{}f(y-x)e^{-i\braket{ y-x , \xi } }  \, dm(y) \\&=e^{-i\braket{ x , \xi } }\hat{f}(\xi) \end{align}$$
> 2. for $f\in L^1(\mathbb{R}^n)$:$$\begin{align}(\lambda(x)\hat{f})(\xi)&=\int_{\mathbb{R}^n}^{}f(y)e^{-i\braket{ y , \xi-x } }  \, dm(y) =(\widehat{e^{i\braket{ \cdot,x  } }f})(\xi)\end{align}$$
> 3. for $f\in L^1(\mathbb{R}^n)$:$$\begin{align}(\widehat{S_{a}f})(\xi)&=\int_{\mathbb{R}^n}^{}f(x / a)e^{-i\braket{ x , \xi } }  \, dm(x)\\&=\int_{\mathbb{R}^n}^{}f(y)e^{-i\braket{ ay , \xi } }  \, a^ndm(y)\\&=a^n\int_{\mathbb{R}^n}^{}f(y)e^{-i\braket{ y , a\xi } }  \, dm(y)\\&=a^n\hat{f}(a\xi)\\&=a^nS_{1 / a}\hat{f}(\xi)\end{align}$$
> 4. from 3.
> 5. We have: $$\begin{align}\mathcal{F}(f*g)(\xi)&=\int_{\mathbb{R}^n}^{} \int_{\mathbb{R}^n}f(x-t)g(t) \, dm(t)e^{-i\braket{ x , \xi } }  \, dm(x) \\&=\int_{\mathbb{R}^n}^{} \int_{\mathbb{R}^n}f(x-t)e^{-i\braket{ x , \xi } }\, dm(x) g(t)  \, dm(t) \\&=\int_{\mathbb{R}^n}^{}\mathcal{F}(\lambda(t)f)(\xi) g(t)  \, dm(t)\\&=\mathcal{F}(f)(\xi)\int_{\mathbb{R}^n}^{}e^{-i\braket{ t , \xi } } g(t)  \, dm(t)\\&=\mathcal{F}(f)(\xi)\cdot \mathcal{F}(g)(\xi)\end{align}$$
---
> [!lemma] Lemma 5 (Inverse FT is adjoint)
> For $f,h\in L^1(\mathbb{R}^n)$, we have: $$\braket{ \mathcal{F}f , h } =\braket{ f , \mathcal{F^{*}h} } $$

> [!proof]-
> We have: $$\begin{align}\braket{ \mathcal{F}f , h } &=\int_{\mathbb{R}^n}^{} \hat{f}(\xi)\overline{h(\xi)} \, dm(\xi) \\&=\int_{\mathbb{R}^n}^{} \int_{\mathbb{R}^n}^{} f(x)e^{-i\braket{ x , \xi } } \, dm(x)\overline{h(\xi)} \, dm(\xi)\\&=\int_{\mathbb{R}^n}^{}f(x) \int_{\mathbb{R}^n}^{} \overline{h(\xi)} e^{-i\braket{ x , \xi } }\, dm(\xi)  \, dm(x) \\&=\int_{\mathbb{R}^n}^{}f(x) \overline{\int_{\mathbb{R}^n}^{} h(\xi) e^{i\braket{ x , \xi } }\, dm(\xi) } \, dm(x)\\&=\int_{\mathbb{R}^n}^{}f(x) \overline{\mathcal{F}^{*}h(x) } \, dm(x) \\&=\braket{ f , \mathcal{F}^{*}h }  \end{align}$$
---
> [!lemma] Theorem 6
> For $f\in C_{00}^{\infty}(\mathbb{R}^n)$, then $\mathcal{F^{*}\mathcal{F}f}=f$

> [!proof]-
> Recall that from Proposition 3, $\hat{f}\in L^1(\mathbb{R}^n)$ and the inverse Fourier transform is well defined. Then, we have:
> 1. **Showing $\mathcal{F^{*}F}f(0)=f(0)$**:
> $$\mathcal{F^{*}\mathcal{F}}f(0)=\int_{\mathbb{R}^n}^{} (\mathcal{F}f)(\xi) \, dm(\xi)=\braket{ \mathcal{Ff} , \mathbf{1} }  $$Now, consider $\varphi(x)=e^{-\|x\|^{2} / 2}$. Then, $\varphi\in C^{\infty}(\mathbb{R}^n)$ and $\varphi=\hat{\varphi}\in L^1(\mathbb{R}^n)$ from Example 1. Therefore, for any $a>0$, $(S_{a}\varphi)(x)=\varphi(x / a)$ and $S_{a}\varphi\xrightarrow{a\to \infty}\varphi(0)=\mathbf{1}$ uniformly on compact sets. As $0\leq S_{a}\varphi\leq 1$, $\braket{ \mathcal{Ff} ,  S_{a}\varphi}\to\braket{ \mathcal{Ff} ,  \mathbf{1}}$. However, $$\begin{align}\braket{ \mathcal{F}f , S_{a}\varphi } =\braket{ f , \mathcal{F^{*}}S_{a}\varphi } =\braket{ f , a^n S_{1/a} \mathcal{F}^{*}\varphi}=\braket{ f , a^n S_{1/a} \varphi}&=\int_{\mathbb{R}^n}^{} f(x)a^n \overline{\varphi(ax)} \, dm(x)\\&=\int_{\mathbb{R}^n}^{} f(x / a) \overline{\varphi(x)} \, dm(x)\\&=\braket{ S_{a}f , \varphi } \to f(0)\braket{\mathbf{1} , \varphi }=f(0) \end{align}  $$Therefore, $(\mathcal{F^{*}}\mathcal{Ff})(0)=\braket{ \mathcal{F}f , \mathbf{1} }=f(0)$.
> 2. **Showing for $x\in \mathbb{R}^n$**:
>	for any $x\in \mathbb{R}^n$:
> $$\begin{align}f(x)&=(\lambda(-x)f)(0)\\&=\mathcal{F^{*}}(\mathcal{F}(\lambda(-x)f)(0))\\&=\mathcal{F}^{*}(e^{i\braket{ x , \cdot  } }(\mathcal{F}f)(0))\\&=\lambda(-x)\mathcal{F}^{*}\mathcal{F}f(0)\\&=\mathcal{F^{*}F}f(x)\end{align}$$
- **Corollary**: For $f,g\in C^\infty_{00}(\mathbb{R}^n)$, $\braket{ \mathcal{F}f , \mathcal{F}g }=\braket{ f , \mathcal{F}^{*}\mathcal{F}g }=\braket{ f , g }$, i.e. the Fourier transform preserves the $L^2$-norm.
---
> [!lemma] Theorem 7 (Plancherel)
> The map $\mathcal{F}:L^1(\mathbb{R}^n)\cap L^2(\mathbb{R}^n)\to C_{0}(\mathbb{R}^n)$ extends uniquely to a unitary operator $$\mathcal{F}:L^2(\mathbb{R}^n)\to L^2(\mathbb{R}^n)$$

> [!proof]-
> We have:
> 1. **Using BLT Theorem for $\mathcal{F}_{\text{ext}}:L^2(\mathbb{R}^n)\to L^2(\mathbb{R}^n)$**:
> 	From Proposition 3, we have $\mathcal{F}:C_{00}^\infty(\mathbb{R}^n)\to L^2(\mathbb{R}^n)$ and as $C_{00}^\infty(\mathbb{R}^n)$ is dense in $L^2(\mathbb{R}^n)$, there exists a unique extension: $$\mathcal{F}_{\text{ext}}:L^2(\mathbb{R}^n)\to L^2(\mathbb{R}^n)$$for which it also holds that $\left\| \mathcal{F}_{\text{ext}}f \right\|_{2}=\left\| f \right\|_{2}$.
> 2. **Showing the extension is extends $\mathcal{F}:L^1(\mathbb{R}^n)\cap L^2(\mathbb{R}^n)\to C_{0}(\mathbb{R}^n)$**:
>For $f\in L^1(\mathbb{R}^n)\cap L^2(\mathbb{R}^n)$, there exists a sequence $(\varphi_{k})\subseteq C_{00}^\infty(\mathbb{R}^n)$ s.t. $\varphi_{k}\to f$ in both $L^1$ and $L^2$. Then, 
>    1. $\lim_{ k \to \infty }\mathcal{F}\varphi_{k}=\lim_{ k \to \infty }\mathcal{F_{\text{ext}}}(\varphi_{k})=\mathcal{F_{\text{ext}}}(f)$ in $L^2$ by definition. 
>    2. $\lim_{ k \to \infty }\mathcal{F}\varphi_{k}=\mathcal{F}f$ in sup-norm as $\|\mathcal{F}g\|_{b}\leq \left\| g \right\|_{1}$ for $g\in L^1$.
>     
>    Therefore, there exists a subsequence of $\mathcal{F}\varphi_{k}$ that converges to $\mathcal{F}_{\text{ext}}(f)$ $m$-a.e. However, as $\mathcal{F}\varphi_{k}$ converges to $\mathcal{F}f$ uniformly, we have that $\mathcal{F}_{\text{ext}}(f)=\mathcal{F}f$ $m$-a.e.
> 3. **Showing surjectivity of $\mathcal{F}_{\text{ext}}$**:
> We first show that $C_{00}^\infty(\mathbb{R}^n)\subseteq\mathcal{F}[L^1(\mathbb{R}^n)\cap L^2(\mathbb{R}^n)]$. Indeed, for $h\in C_{00}^\infty(\mathbb{R}^n)$, $\mathcal{F^{*}}h\in L^1(\mathbb{R}^n)\cap L^2(\mathbb{R}^n)$ and therefore, $$h=\mathcal{F}\mathcal{F}^{*}h$$
> Now as $\mathcal{F}_{\text{ext}}[L^2(\mathbb{R}^n)]$ is an image of a Hilbert space of an isometry which is always closed. Therefore, $L^2(\mathbb{R}^n)\subseteq \mathcal{F}_{\text{ext}}[L^2(\mathbb{R}^n)]$ as $C_{00}^\infty(\mathbb{R}^n)$ is dense in $L^2(\mathbb{R}^n)$.
---
> [!lemma] Lemma 8
> Let $f\in W^{2,k}(\mathbb{R}^n)$, the [[Sobolev Space]], then for all $\left| \alpha \right|\leq k$, $$\mathcal{F}(D^\alpha_{w}f)(\xi)=i^{\left| \alpha \right|}\xi^\alpha \mathcal{F}(f)(\xi)$$In particular, $\xi^\alpha \hat{f}\in L^2(\mathbb{R}^n)$. 

> [!proof]-
> We will show this using induction on $k$. First, we show for $k=1$. For $\varphi\in C_{00}^\infty(\mathbb{R}^n)$, we have $\partial_{j}^wf\in L^2(\mathbb{R}^n)$ we have, by Plancherel: $$\begin{align}\braket{ \mathcal{F}(\partial^w_{j}f) , \mathcal{F}(\varphi) }&=\braket{ \partial^w_{j}f , \varphi } \\&=-\braket{ f , \partial_{j}\varphi }  \\&=-\braket{ \mathcal{F}(f) , \mathcal{F}(\partial_{j}\varphi) } \\&=-\int_{\mathbb{R}^n}^{} \hat{f}\overline{\mathcal{F}(\partial_{j}\varphi)} \, dm \\&=\int_{\mathbb{R}^n}^{} \hat{f}(\xi)i\xi_{j}\overline{\hat{\varphi}(\xi)} \, dm(\xi)\\&=\braket{ i\xi_{j}\mathcal{F}f, \mathcal{F\varphi} } \end{align}$$As $\{ \mathcal{F}\varphi:\varphi\in C^\infty_{00}(\mathbb{R}^n) \}$ is dense in $L^2(\mathbb{R}^n)$, we get: $$\mathcal{F}(\partial_{j}^wf)=i\xi_{j}\mathcal{F}f$$The rest follows from recursion.
---
> [!lemma] Lemma 9
> Let $r\in \mathbb{N}$. Further, let $h,\xi^\alpha h\in L^1(\mathbb{R}^n)$ for all $\left| \alpha \right|\leq r$. Then, $\mathcal{F^{*}}(h)\in C^r_{b}(\mathbb{R}^n)$ and:
> $$D^\alpha(\mathcal{F^{*}h})(x)=i^{\left| \alpha \right| }\mathcal{F^{*}}(\xi^\alpha h)(x)$$

> [!proof]-
> We will show this using induction on $r$. First, we show for $r=1$. Use Lemma in [[Convolution (Rn)|Proposition 4]] on:
> 1. $X = \mathbb{R}^n$, $D=\mathbb{R}^n$
> 1. $f(x,\xi)=h(\xi)e^{i\braket{ x , \xi }}$ where $f(\cdot,\xi)\in C^1(\mathbb{R}^n)$ and $f(x,\cdot)\in L^1(\mathbb{R}^n)$
> 2. $\partial_{j}f(x,\xi)=h(\xi)i\xi_{j}e^{i\braket{ x , \xi }}=i\xi_{j}f(x,\xi)$, so $\partial_{j}f(x,\cdot)\in L^1(\mathbb{R}^n)$
> 3. $G_{j}(x)=\int_{\mathbb{R}^n}^{} h(\xi)i\xi_{j}e^{i\braket{ x , \xi }} \, dm(\xi)=i\mathcal{F}^{*}(h\cdot_{j})(x)$, therefore it is continuous.
> 
> Hence, we can conclude that $\partial_{j}\int_{\mathbb{R}^n}^{} h(\xi)e^{i\braket{ x , \xi }} \, dm(\xi)=\partial_{j}\mathcal{F}^{*}h(x)=G_{j}(x)$.
> 
---
> [!lemma] Lemma 10
> Let $r\geq 0$. Assume $f\in L^2(\mathbb{R}^n)$ and $\xi^\alpha \hat{f}\in L^1(\mathbb{R}^n)$ for all $\left| \alpha \right|\leq r$. Then, $f\in C^r_{b}(\mathbb{R}^n)$ and $$D^\alpha f=i^{\left| \alpha \right| }\mathcal{F^{*}}(\xi^\alpha \hat{f})$$

> [!proof]-
> Apply Lemma 9 on $h=\hat{f}$.
> 
---

##### Examples
> [!lemma] Proposition 1
> Let $\varphi(x)=e^{-\|x\|^{2} / 2}$. Then, $\hat{\varphi}=\varphi$.

> [!proof]- Proof
> We have: $$\begin{align}\hat{\varphi}(\xi)&=\int_{\mathbb{R}^n}^{} e^{-\|x\|^2/2} e^{-i\braket{ x , \xi } }\, dm(x) \\&=\int_{\mathbb{R}^n}^{} \prod_{i=1}^{n}e^{-x_{i}^2/2} e^{-ix_{i}\xi_{i} }\, dm(x)\\&=\prod_{i=1}^{n}\int_{\mathbb{R}}^{} e^{-x_{i}^2/2} e^{-ix_{i}\xi_{i} }\, dm(x)  \\&=\prod_{i=1}^{n}e^{-\xi_{i}^{2}/2}\\&=e^{-\|\xi\|^{2}/2}\\&=\varphi(\xi)\end{align}$$
---
