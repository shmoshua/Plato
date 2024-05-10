#Definition #Analysis 

> [!definition]
> For $f\in L^2((-\pi,\pi),\mathbb{C})$ and $k\in \mathbb{Z}$, the ***$k$-th Fourier coefficient*** is the linear functional $c_{k}\in L^2((-\pi,\pi))^{*}$ where $$c_{k}(f):= \frac{1}{2\pi}\int_{-\pi}^{\pi} f(x)e^{-ikx} \, dx $$
- **Related definition**: For $N\in \mathbb{N}$, the $N$-th ***Fourier partial sum*** if a function: $$\begin{array}{cccc} {S_{N}(f):}&{(-\pi,\pi)}&\to&{\mathbb{C}}\\&{x} &\mapsto & {\sum_{k=-N}^{N}c_{k}(f)e^{ikx}} \end{array}{}$$
---
##### Properties
> [!lemma] Proposition 1
> For the Fourier coefficients,
> 1. $c_{k}(f)$ are well-defined if $f\in L^2((-\pi,\pi))$
> 2. $c_{k}(f)$ are well-defined if $f\in L^1((-\pi,\pi))$

> [!proof]-
> We have that: 
> 1. if $f\in L^2$:$$\int_{-\pi}^{\pi} \left| e^{-2ikx} \right|  \, dx=2\pi $$Therefore, $x\mapsto e^{-ikx}\in L^2((-\pi,\pi))$ and by [[Lp Space|Hölder]], $x\mapsto f(x)e^{-ikx}\in L^1((-\pi,\pi))$.  
> 2. if $f\in L^1$: $$\int_{-\pi}^{\pi} \left| f(x)e^{-ikx} \right|  \, dx=\int_{-\pi}^{\pi} \left| f(x) \right|  \, dx=\|f\|_{1}<+\infty  $$
---
