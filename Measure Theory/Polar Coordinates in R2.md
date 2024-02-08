#Definition #MeasureTheory 

---
We have that
1. $x=\rho \cos\sigma$
2. $y=\rho \sin \sigma$

Therefore, we can define a [[Diffeomorphsim|$C^1$-diffeomorphism]] $\Phi:(0,+\infty)\times(-\pi,\pi)\to \mathbb{R}^2 \backslash\{ (x,y): x\leq 0,y=0 \}$ as follows: $$\Phi(\rho,\sigma)=(\rho \cos\sigma,\rho \sin\sigma)$$where: $$\left| \det(D\Phi) \right| =\left| \det \left( \begin{bmatrix}\cos\sigma&-\rho \sin\sigma\\ \sin\sigma&\rho \cos\sigma\end{bmatrix} \right)  \right|=\rho $$
Therefore, by [[Lebesgue Measure|Change of variable formula]]: for any $\mathcal{L}^2$-summable function $f:A\subseteq \mathbb{R}^2\to \mathbb{R}^2$, $$\int_{A}^{} f \, d\mathcal{L}^2=\int_{\varphi ^{-1}[A]}^{} f(\rho \cos\sigma,\rho \sin\sigma)\rho \, d\mathcal{L}^2(\rho,\sigma)  $$

---
##### Examples
> [!claim] Exercise 1
> Compute the Gaussian integral: $$\int_{-\infty}^{\infty}e^{-x^2}  \, dx $$

> [!proof]-
> We first show that $e^{-x^2}$ is $\mathcal{L}^1$-summable. We have: $$\begin{align}\int_{-\infty}^{\infty} e^{-x^2} \, dx &=2\int_{0}^{\infty} e^{-x^2} \, dx\\&=2\left( \int_{0}^{1} e^{-x^2} \, dx+ \int_{1}^{\infty} e^{-x^2} \, dx \right)\\&\leq2\left( 1+ \int_{1}^{\infty} xe^{-x^2} \, dx \right)\\&\leq2\left( 1+\frac{1}{2e}\right)\\&=2+\frac{1}{e}<+\infty\end{align}$$Now, using Tonelli: $$\begin{align}\int_{\mathbb{R}^2}^{} e^{-x^2-y^2} \, dxdy&=\int_{-\infty}^{\infty} \left( \int_{-\infty}^{\infty} e^{-x^2-y^2} \, dy  \right)  \, dx=\left( \int_{-\infty}^{\infty} e^{-x^2} \, dx  \right)^{2}\end{align} $$However, $$\begin{align}\int_{\mathbb{R}^2}^{} e^{-x^2-y^2} \, dxdy=\int_{-\pi}^{\pi} \int_{0}^{\infty} e^{-\rho^{2}}\rho \, d\rho  \, d\sigma=\frac{1}{2}\int_{-\pi}^{\pi} 1 \, d\sigma= \pi \end{align}$$Therefore, the Gaussian integral is $\int_{-\infty}^{\infty}e^{-x^2}  \, dx =\sqrt{ \pi }$.
---