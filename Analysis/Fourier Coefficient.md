#Definition #Analysis 

> [!definition]
> For $f\in L^2((-\pi,\pi),\mathbb{C})$ and $k\in \mathbb{Z}$, the ***$k$-th Fourier coefficient*** of $f$ is the complex number: $$c_{k}(f):= \frac{1}{2\pi}\int_{-\pi}^{\pi} f(x)e^{-ikx} \, dx $$
---
##### Properties
> [!lemma] Proposition 1
> The Fourier coefficients $c_{k}(f)$ are well-defined.

> [!proof]+
> We have that: $$\int_{-\pi}^{\pi} \left| e^{-2ikx} \right|  \, dx=2\pi $$Therefore, $x\mapsto e^{-ikx}\in L^2((-\pi,\pi))$ and by [[Lp Space|Hölder]], $x\mapsto f(x)e^{-ikx}\in L^1((-\pi,\pi))$.  