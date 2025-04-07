#### 1. Characterization

Let $F_{C}(x)=\begin{cases}0&x<1\\ \frac{1}{4}(x-1)^{2}&1\leq x\leq 3\\1&\text{ otherwise}\end{cases}$ and $f_{C}(x)=\frac{1}{2}(x-1)\cdot \mathbb{1}_{x\in [1,3]}$.

Find $f_{R}$ where $R=C^{2}$.

We have: $$f_{R}(t)=\mathbb{P}(C^{2}\leq t)=\mathbb{P}(C\leq \sqrt{ t } )=F_{C}(\sqrt{ t })=\frac{1}{2}(\sqrt{ t }-1)\cdot \mathbb{1}_{\sqrt{ t }\in[1,3]}=\frac{1}{2}(\sqrt{ t }-1)\cdot \mathbb{1}_{t\in[1,9]}$$


And $$\mathbb{E}[\phi(R)]=\mathbb{E}[\psi(C)]= \frac{1}{2}\int_{1}^{3} \phi(c^2) (c-1) \, dc= \frac{1}{4}\int_{1}^{9} \phi(r)\left( 1-\frac{1}{\sqrt{ r }} \right)\, dr $$Hence, $f_{R}(r)= \frac{1}{4}\left( 1-\frac{1}{\sqrt{ r }} \right)\cdot \mathbb{1}_{r\in [1,9]}$.

---
$f_{X}(x)=4x^{-5}\cdot \mathbb{1}_{x\geq 1}$. Then, for $Y:= \log(X)$, $$\mathbb{P}(\log(X)\leq t)=\mathbb{P}(X\leq e^t)=\int_{1}^{e^t} 4x^{-5} \, dx=[-x^{-4}]^{e^t}_{1}=1-e^{-4t} $$Hence, $f_{Y}(t)=4e^{-4t}\cdot \mathbb{1}_{t\geq 0}$.

Otherwise, $$\mathbb{E}[\phi(Y)]=\mathbb{E}[\psi(X)]=\int_{1}^{\infty} \phi(\log x) 4x^{-5} \, dx=\int_{0}^{\infty} \phi(y) 4e^{-4y}\, dy  $$

---
hihi
1. **Change of variables**: Let $U,V\subseteq \mathbb{R}^n$ be two open sets. Let $\Phi:U\to V$ be a differentiable bijection. Then, for a differentiable function $f:U\to \mathbb{R}$, $$\int_{U}f(x) \, dx=\int_{V} f(\Phi(x))\left| \det(\text{D}\Phi(x)) \right|   \, dx  $$
   
2. **Leibniz rule**
   $$\frac{d}{dt} \int_{a(t)}^{b(t)} f(x,t) \, dx= f(b(t),t) \frac{d}{dt}b(t)-f(a(t),t) \frac{d}{dt}a(t) +\int_{a(t)}^{b(t)} \frac{ \partial  }{ \partial t } f(x,t) \, dx $$



3. Find the density of $X:=Z_{1}+Z_{2}$ where $Z_{1},Z_{2}\sim \text{Exp}(\lambda)$ i.i.d.
	
	Let $\phi:\mathbb{R}\to \mathbb{R}$ be a piecewise continuous bounded function. Then, we define $\psi:\mathbb{R}^{2}\to \mathbb{R}$ s.t. $\psi(z_{1},z_{2})=\phi(z_{1}+z_{2})$. Then, $$\begin{aligned}\mathbb{E}[\phi(X)]=\mathbb{E}[\psi(Z_{1},Z_{2})]&=\int_{0}^{\infty} \int_{0}^{\infty} \psi(z_{1},z_{2})\lambda^{2} e^{-\lambda(z_{1}+z_{2})} \, dz_{1}  \, dz_{2} \\&=\lambda^{2} \int_{0}^{\infty} \int_{0}^{x} \psi(z_{1},x-z_{1})e^{-\lambda x} \, dz_{1}  \, dx \\&=\lambda^{2}\int_{0}^{\infty}\int_{0}^{x} \phi(x) e^{-\lambda x} \, dz_{1} \, dx  \\&=\int_{0}^{\infty}  \phi(x)\lambda^{2} xe^{-\lambda x}\, dx   \end{aligned}$$
3. Method 2: $$\begin{aligned}F_{X}(t)=\mathbb{P}(Z_{1}+Z_{2}\leq t)&=\int_{0}^{t}\mathbb{P}(Z_{1}+Z_{2}\leq t|Z_{2}=x) f_{Z_{2}}(x) \, dx\\&=\int_{0}^{t}\mathbb{P}(Z_{1}\leq t-x)\lambda e^{-\lambda x}\, dx 
   \\&=\lambda \int_{0}^{t}(1-e^{-\lambda(t-x)})e^{-\lambda x}\, dx\\&=\lambda \int_{0}^{t}e^{-\lambda x}-e^{-\lambda t}\, dx \\&=\lambda \int_{0}^{t}e^{-\lambda x}\, dx -\lambda te^{-\lambda t}\\&= 1-e^{-\lambda t} -\lambda te^{-\lambda t}\end{aligned} $$and $\lambda e^{-\lambda t}-\lambda e^{-\lambda t}+\lambda^{2}t e^{-\lambda t}$.
   
   By Leibniz, we have that: $$f_{X}(t)=\frac{d}{dt}F_{X}(t)=\lambda \int_{0}^{t} \lambda e^{-\lambda t} \, dx =\lambda^{2}te^{-\lambda t}$$


---
#### 2. Inequalities
1. Monotonicity
2. Markov
3. Jensen

Let $f_{X}(t)=\frac{1}{2}\cdot \mathbb{1}_{t\in[-1,1]}$ and $f_{Y}(t)=\frac{1}{4}\cdot \mathbb{1}_{t\in[0,4]}$. Show that $0\leq \mathbb{E}[Z]\leq \sqrt{ 17 / 3 }$