#Definition #Analysis #FunctionalAnalysis 

> [!definition]
> Let $\Omega \subseteq \mathbb{R}^n$ be an open set. Let $f,h\in L^{1}_{\text{loc}}(\Omega)$, then $h$ is the ***weak $\alpha$-partial derivative*** of $f$, denoted as $D^\alpha_{w}f$ on $\Omega$ if $$\int_{\Omega}^{} f\cdot D^\alpha\varphi \, dm=(-1)^{\left| \alpha \right| }\int_{\Omega}^{}  D^\alpha_{w}f\cdot \varphi\, dm,\quad \forall\varphi\in C_{00}^\infty(\Omega)  $$
- **Remark**: As $\varphi$ and $D^\alpha\varphi$ have compact support, both these integrals make sense. 
- **Remark**: Notice the similarity given by integration by parts. For $f\in C^{\infty}(\Omega)$ and $\varphi\in C^{\infty}_{00}(\Omega)$, $$\int_{\Omega}^{} f(x)\cdot D^\alpha\varphi(x) \, dm(x)=(-1)^{\left| \alpha \right| }\int_{\Omega}^{}  D^\alpha f(x)\cdot \varphi(x)\, dm(x) $$
---
##### Properties
> [!lemma] Lemma 1 (Uniqueness of weak derivatives)
> Let $h\in L^1_{\text{loc}}(\Omega)$. If for all $\varphi\in C^{\infty}_{00}(\Omega)$, $$\int_{\Omega}^{} h\cdot \varphi\, dm =0$$then $h=0$ $m$-a.e.

> [!proof]+
> Let $x\in \Omega$ be arbitrary and let $r>0$, $\varepsilon>0$ s.t. $B_{\leq r+\varepsilon}(x)\subseteq\Omega$. Then for $\chi:=\chi_{B_{\leq r+\varepsilon}(x)}$, $$\chi \cdot h\in L^1(\Omega)$$
> Choose an [[Approximate Identity]] $\delta_{\varepsilon}$ where $\text{supp }\delta \subseteq B_{<1}(0)$ and $\delta(t)=\delta(-t)$. Then, for every $\varphi\in C_{00}^\infty(\mathbb{R}^n)$: $$\begin{align}\int_{\Omega}(\delta_{\varepsilon}*\chi \cdot h)\varphi  \, dm &=\int_{\Omega}\int_{\Omega} \delta_{\varepsilon}(t-x)\chi(t)h(t) \varphi(x)  \, dm(x)\, dm(t) \\&=\int_{\Omega}\chi(t)h(t)(\delta_{\varepsilon}*\varphi)(t)\, dm(t) \end{align} $$If additionally $\text{supp }\varphi \subseteq B_{< r}(x)$, then: $$\begin{align}\int_{\Omega}(\delta_{\varepsilon}*\chi \cdot h)\varphi \, dm &=\int _{\Omega}\chi \cdot h\cdot (\delta_{\varepsilon}*\varphi)\, dm\\&=\int_{\Omega}h\cdot (\delta_{\varepsilon}*\varphi)\, dm
> \\&=0\end{align} $$since $\text{supp}(\delta_{\varepsilon}*\varphi)\subseteq B_{<r+\varepsilon}(x)\subseteq B_{\leq r+\varepsilon}(x)$.
> 
> By [[Convolution|Proposition 4]], $\delta_{\varepsilon}*(\chi \cdot h)\in C^{\infty}(\Omega)$ and it follows that $(\delta_{\varepsilon}*\chi \cdot h)|_{B_{<r}(x)}\in L^2(B_{<r}(x))$. Since $C_{00}^\infty(B_{<r}(x))$ is dense in $L^2(B_{<r}(x))$ by [[Smooth Function with Compact Support|Proposition 1]], $\delta_{\varepsilon}*\chi \cdot h=0$ in $B_{<r}(x)$. 
---
##### Examples
1. For $\alpha>0$, $f(t):=\left| t \right|^\alpha$ has a weak derivative $\frac{d}{dt}_{w}f(x)=\alpha \text{sgn}(x)\left| x \right|^{\alpha-1}$
---