#### Example Questions
Let $X,Y$ be independent and $X\sim \text{Poisson}(\lambda)$ and $Y\sim \text{Poisson}(\mu)$ where $\lambda,\mu>0$. 
1. Show that $X+Y\sim \text{Poisson}(\lambda+\mu)$. $$\begin{aligned}\mathbb{P}(X+Y=k)&=\sum_{\ell=0}^{k}\mathbb{P}(X+Y=k|Y=\ell)\mathbb{P}(Y=\ell)\\&=\sum_{\ell=0}^{k}\mathbb{P}(X=k-\ell)\mathbb{P}(Y=\ell)\\&=\sum_{\ell=0}^{k}\frac{\lambda^{k-\ell}}{(k-\ell)!}  \frac{\mu^{\ell}}{\ell!}e^{-(\lambda+\mu)}\\&=\frac{1}{k!}\left( \sum_{\ell=0}^{k}{k \choose \ell}\lambda^{k-\ell}\mu^{\ell} \right)e^{-(\lambda+\mu)}\\&=\frac{1}{k!}(\lambda+\mu)^k e^{-(\lambda+\mu)}\end{aligned}$$
2. Show that $X|X+Y=n\sim \text{Bin}\left( n, \frac{\lambda}{\lambda+\mu} \right)$. We have that: $$\begin{aligned}\mathbb{P}(X=k|X+Y=n)&=\frac{\mathbb{P}(X=k,X+Y=n)}{\mathbb{P}(X+Y=n)}=\frac{\mathbb{P}(X=k,Y=n-k)}{\mathbb{P}(X+Y=n)}\\&=\frac{1}{k!}\lambda^ke^{-\lambda}\cdot \frac{1}{(n-k)!}\mu^{n-k}e^{-\mu}\cdot  n! \frac{1}{(\lambda+\mu)^ne^{-\lambda-\mu}}\\&={n \choose k}\lambda^k\mu^{n-k}\frac{1}{(\lambda+\mu)^n}\end{aligned}$$
3. We have: $$\mathbb{P}(X+Y=n|Y=\ell)=\frac{\mathbb{P}(X+Y=n,Y=\ell)}{\mathbb{P}(Y=\ell)}=\mathbb{P}(X=n-\ell)$$

Let $Y\sim \text{Geom}(p)$ with $p=0.05$.
1. $\mathbb{P}(Y>10)=0.95^{10}$
2. Show that memoryless property. and converse.

#### Continuous Random Variables


#### Example Questions
1. We have density $f:\mathbb{R}\to \mathbb{R}_{+}$, where: $$f(x):=\begin{cases}4x^{-5}&x\geq 1\\0&x<1\end{cases}$$
	1. Verify that $f$ is a density.
	2. Compute the distribution function $F_{X}$.
	3. Compute $\mathbb{P}(\left| X \right|\leq 1 /2)$ and $\mathbb{P}(X\geq 2)$.
	4. Compute the distribution of $F_{Y}$ of $Y:= 2X^{2}$.
2. We have that: $$F_{X}(a):=\begin{cases}0&a<-\pi /2\\\frac{1+\sin(a)}{2}&-\pi/2 \leq a \leq \pi /2\\1&\pi /2<a\end{cases}$$
	1. Show that $X$ is a continuous random variable and compute the density of $X$.
	2. Compute $\mathbb{P}(X=e^{-\pi})$ and $\mathbb{P}(0\leq X\leq \pi /4)$. 