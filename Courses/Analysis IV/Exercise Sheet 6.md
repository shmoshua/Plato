#Series #Analysis 

> [!def] Problem 6.2
> Let $f:\mathbb{R}\to \mathbb{C}$ be a $2\pi$-periodic function such that $f\in L^1((-\pi,\pi),\mathbb{C})$ and let $\tau\in \mathbb{R}$. Define $f_{\tau}(t):=f(t-\tau)$. Determine the Fourier coefficients of $f_{\tau}|_{(-\pi,\pi)}$ as a function of the Fourier coefficients of $f|_{(-\pi,\pi)}$. 

We have for every $k\in \mathbb{Z}$: $$\begin{align}c_{k}(f_{\tau})&=\frac{1}{2\pi}\int_{-\pi}^{\pi} f_{\tau}(x)e^{-ikx} \, dx\\&=\frac{1}{2\pi}\int_{-\pi}^{\pi} f(x-\tau)e^{-ikx} \, dx\\&=\frac{1}{2\pi}\int_{-\pi-\tau}^{\pi-\tau} f(y)e^{-ik(y+\tau)} \, dy\\&=\frac{1}{2\pi}e^{-ik\tau}\int_{-\pi-\tau}^{\pi-\tau} f(y)e^{-iky} \, dy \\&=\frac{1}{2\pi}e^{-ik\tau}\int_{-\pi}^{\pi} f(y)e^{-iky} \, dy \\&=e^{-ikr}c_{k}(f)\end{align}$$

---