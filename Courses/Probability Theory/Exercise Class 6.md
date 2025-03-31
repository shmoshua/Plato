
#### 1. Three Kinds of Continuous Distributions
1. Uniform
2. Normal/Gaussian
3. Exponential

Problems
1. Let $X\sim \text{Exp}(\lambda)$ and $Y\sim \text{Exp}(\mu)$. What is $F_{\min \{ X,Y \}}$? $$F_{\min \{ X,Y \}}(z)=(1-e^{-(\lambda+\gamma)z})\cdot \mathbb{1}_{z\geq 0}$$ and $\text{min}(X,Y)\sim \text{Exp}(\lambda+\gamma)$.
2. Density of $M:= max(U_{1},U_{2})$ where $U_{1},U_{2}\sim \mathcal{U}([0,1])$ iid.
3. Density of $M:= max(U_{1},U_{2},U_{3})$ where $U_{1},U_{2},U_{3}\sim \mathcal{U}([0,1])$ iid.
4. Find $\mathbb{P}(U_{1}\leq x|\max\{ U_{1},U_{2} \}\geq y)$ for some $y\in(0,1)$. 

5. Find $F_{ 1 / X}$ for $X>0$ Then, $$F_{Y}(y)=\mathbb{P}(Y\leq y)= \mathbb{P}\left( \frac{1}{y}\leq X \right)=1-F_{X}(1 / y)$$Further, $$F'_{Y}(y)=-f_{X}\left( \frac{1}{y} \right)\cdot \left( - \frac{1}{y^{2}} \right)$$
---
#### 2. Expectation
1. Discrete and Continuous expectation
2. $\mathbb{E}[\phi(X)]=\int_{-\infty}^{\infty} \phi(x)f(x) \, dx$
3. Linearity
4. 
5. Tailsum formula:
	1. If $X$ is a positive random variable: $$\mathbb{E}[X]=\mathbb{E}\left[ \int_{0}^{\infty} \mathbb{1}_{\{ X\geq x \}} \, dx  \right]$$
	
	We have that: $$X=\int_{0}^{X}1 dx= \int_{0}^{\infty}\{ X\geq x \} \, dx $$
4. Similarly $X=\sum_{k=1}^{\infty}\{ X\geq k \}$. 
---
#### 3. Gaussian Integrals
1. $\int_{-\infty}^{\infty} e^{-x^{2}} \, dx = \sqrt{ \pi }$$$\int_{-\infty}^{\infty} e^{-a(x+b)^{2}} \, dx =\sqrt{ \frac{\pi}{a} }$$$$\int_{-\infty}^{\infty} e^{-a(x+b)^{2}} \, dx=\int_{-\infty}^{\infty} e^{-ay^{2}} \, dx ,\quad \forall a>0$$
2. $$\int_{0}^{\infty} xe^{-x^{2}} \, dx = -\frac{1}{2}\int_{0}^{\infty} (-2x e^{-x^{2}}) \, dx =-\frac{1}{2}[e^{-x^{2}}]^\infty_{0}=-\frac{1}{2}(0-1)=\frac{1}{2} $$
3. 
4. Let $Z\sim \mathcal{N}(0,\sigma^{2})$. Then, $$\begin{aligned}\mathbb{E}[\left| Z \right| ]&=\frac{1}{\sqrt{ 2\pi\sigma^{2} } }\int_{-\infty}^{\infty} \left| z \right| e^{-\frac{z^{2}}{2\sigma^{2}}} \, dz \\&=\frac{2}{\sqrt{ 2\pi\sigma^{2} } }\int_{0}^{\infty}ze^{-\frac{z^{2}}{2\sigma^{2}}} \, dz \\&=\frac{2\sqrt{ 2\sigma^{2} }}{\sqrt{ \pi } }\int_{0}^{\infty}xe^{-x^{2}} \, dx \\&=\sigma\sqrt{ \frac{2}{\pi} }\end{aligned}$$where $x= z / \sqrt{ 2\sigma^{2} }$.  
---

#### 3. Problems
1. $\mathbb{E}[U^4]$ for $U\sim \mathcal{U}([0,2])$ = 16/5.
2. 