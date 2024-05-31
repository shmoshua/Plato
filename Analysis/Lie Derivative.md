#Definition #Analysis 

> [!definition]
> Let $X,Y\in \Gamma(\text{T}M)$ be [[Integral Curve|complete]] [[Vector Field|smooth vector fields]]. The ***Lie derivative*** of $Y$ with respect to $X$ is $L_{X}Y\in \Gamma(\text{T}M)$ s.t.: $$(L_{X}Y)_{p}=\lim_{ t \to 0 }  \frac{1}{t}\left( d\Phi^{-t}_{X}(Y_{\Phi_{X}^t(p)})-Y_{p} \right)=\left. \frac{d}{dt} \right| _{t=0}d\Phi_{X}^{-t}(Y_{\Phi^t_{X}(p)}) \in \text{T}_{p}M$$where $\Phi_{X}^t$ denotes the [[flow]].
- **Remark**: Recall that $\Phi_{X}^{-t}:M\to M$. Therefore, $d_{\Phi^t_{X}(p)}\Phi^{-t}_{X}:\text{T}_{\Phi^t_{X}(p)}M\to \text{T}_{p}M$.
---
##### Properties
> [!lemma] Proposition 1
> For $X,Y\in \Gamma(\text{T}M)$
> 1. $L_{X}Y=[X,Y]$

> [!proof]+
> As $\Gamma(\text{T}M)\cong\text{Der }C^\infty(M)$, we only have to check that for all $f\in C^\infty(M)$, $(L_{X}Y)(f)=[X,Y]f$. Let $p\in M$. Then, $$\begin{align}(L_{X}Y)_{p}(f)&=\lim_{ t \to 0 } \frac{1}{t}\left( d\Phi^{-t}_{X}(Y_{\Phi_{X}^t(p)})-Y_{p} \right)(f)\\&=\left. \frac{d}{dt} \right|_{t=0}d\Phi_{X}^{-t}(Y_{\Phi^t_{X}(p)})(f) \\&=\left. \frac{d}{dt} \right|_{t=0}Y_{\Phi^t_{X}(p)}(f\circ \Phi_{X}^{-t}) \end{align}$$
> 
> By considering $\Phi^t_{X}(p)=\Phi_{X}(t,p)$ and treating $h(t)=f(\Phi_{X}(t,p))$, we have: $$f(\Phi_{X}(t,p))=f(p)+t\cdot g(t,p)$$where $g$
> 