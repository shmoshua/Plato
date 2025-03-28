#Series #Algorithms 

#### Problem 1.1

 Define $f:\mathbb{R}^n\to \mathbb{R},\beta\mapsto \frac{1}{2n}\left\| X\beta-y \right\|^{2}$. Then, $$\nabla f(\beta ^{*})=\frac{1}{n}X^\top\underbrace{ (X\beta ^{*}-y) }_{ =-w }=-\frac{1}{n}X^\top w$$Let $u:=\widehat{\beta}-\beta ^{*}$. Then, as $\left\| \beta ^{*} \right\|_{1}\leq R$, by the minimality $f(\beta ^{*})\geq f(\beta ^{*}+u)$. Hence, by Taylor:$$f(\beta ^{*})\geq f(\beta ^{*}+u)=f(\beta ^{*})-\frac{1}{n}u^\top X^\top w+\frac{1}{2n}\left\| Xu \right\| ^2_{2}$$It follows that $\left\| Xu \right\|^{2}_{2}\leq 2u^\top X^\top w$ and by Hölder,$$\frac{1}{2}\left\| Xu \right\| ^2_{2}\leq \braket{ u , X^\top w } \leq \|u\|_{1}\left\| X^\top w \right\| _{\infty}$$
 1. **Claim 1**: Let $x\sim \mathcal{N}(0,\Sigma)$ be a $d$-dimensional Gaussian vector where $\Sigma_{ii}\leq 1$ for all $i\in[d]$. Then, with probability at least $1-d^{-10}$, $\max_{i\in [d]} x_{i}^{2} \leq O(\log d)$. 
    
    Let $z:=\max_{i\in[d]} x_{i}^{2}$. We have that: $$\begin{align}\mathbb{P}(\exp(tz)\geq \lambda)=\mathbb{P}(\max_{i\in[d]}\exp(tx_{i}^{2})\geq \lambda)=\mathbb{P}(\exists i\in[d]: \exp(tx^2_{i})\geq \lambda)\leq \sum_{i\in[d]}\mathbb{P}(\exp(tx^2_{i})\geq \lambda)\end{align}$$by union bound. Then, for any $i\in[d]$,  we have that $y_{i}:=\frac{1}{\sqrt{ \Sigma_{ii} }}x_{i}\sim \mathcal{N}(0,1)$ and:$$\begin{align}\mathbb{P}(\exp(tx^2_{i})\geq \lambda)=\mathbb{P}\left( \left| x_{i} \right| \geq \sqrt{ \frac{\log \lambda}{t} } \right)=\mathbb{P}\left( \left| y_{i} \right| \geq \sqrt{ \frac{\log \lambda}{\Sigma_{ii}t} } \right)\leq 2e^{-\frac{\log \lambda}{2\Sigma_{ii}t}}\leq 2e^{-\frac{\log \lambda}{2t}}=2\lambda^{-1/2t}\end{align}$$
    
    
    Hence, by taking $t=24$, $$\mathbb{P}(\exp(tz) \geq d)\leq 2d^{-11}\leq d^{-10}$$
    Therefore, with probability at least $1-d^{-10}$, $z\leq O(\log d)$.

We define $w':= \frac{1}{2\sqrt{ n }}X^\top w$. Then, $w'$ is Gaussian as a sum of independent Gaussian variables. Further, $$\mathbb{E}\left[ \frac{1}{2\sqrt{ n }}X^\top w\right] =\frac{1}{2\sqrt{ n }}X^\top \mathbb{E}[w]=0,\quad\text{Var}\left( \frac{1}{2\sqrt{ n }}X_{i}^\top w \right)=\frac{\sigma^{2}}{4n}X_{i}^\top X_{i}=\frac{\sigma^{2}}{n}\left\| X_{i} \right\| ^2_{2}\leq 1$$Hence, by Claim 1 we get that with probability at least $1-d^{-10}$:$$\left(  \frac{1}{2\sqrt{ n }}\max_{i\in[d]}  X^\top_{i}w    \right)^{2} =\max_{i\in[d]} \left(  \frac{1}{2\sqrt{ n }} X^\top_{i}w    \right)^{2} \leq O(\log d)$$
For the rest, as we have that $\|u\|_{1}\leq\|\beta\|_{1}+\|\beta ^{*}\|_{1}\leq 2 R$, with the same probability we have:$$\frac{1}{n} \left\| X(\widehat{\beta}-\beta ^{*}) \right\| ^{2}_{2}  = \frac{1}{n}\left\| Xu \right\| ^{2}_{2} =\frac{1}{n}\|u\|_{1}\cdot \max_{i\in [d]}X_{i}^\top w  \leq \frac{R}{\sqrt{ n }}O(\sqrt{ \log d })$$

---
#### Problem 2.2

Let $j\in[d]$. Define the following matrix $A\in \mathbb{R}^{d,d}$ where: $$A_{k\ell}:=\begin{cases}1&k=\ell\\ b_{j}s_{\ell}&k=j, \ell\neq j\\0&\text{otherwise}\end{cases}$$Then, one sees that $Az=(z(1),\dots,z(j-1),w_{j},z(j+1),\dots,z(d))\sim \mathcal{N}(0,A(I_{d}-\theta ss^\top)A^\top)$. This shows that $w_{j}$ and $z^{\backslash j}$ are jointly Gaussian. 

Now, $$\begin{aligned}\text{Cov}(z^{\backslash j}, w_{j})=\mathbb{E}[w_{j}z^{\backslash j}]=\mathbb{E}[z_{j}z^{\backslash j}-z^{\backslash j}(z^{ \backslash j})^\top \beta ^{*}_{j}]=\text{Cov}(z^{\backslash  j},z_{j})-\text{Var}(z^{\backslash j})\beta ^{*}_{j}\end{aligned}$$as $\text{Cov}(z^{\backslash j},z_{j})=-\theta s_{j}s^{\backslash j}$ and $\text{Var}(z^{ \backslash j})=I_{d-1}-\theta s^{ \backslash j}(s^{ \backslash j})^\top$, we have that: $$\text{Cov}(z^{\backslash j}, w_{j})=-\theta s_{j}s^{\backslash j}+b_{j}s^{ \backslash j}-b_{j}\theta \left\| s^{\backslash j} \right\| ^{2}_{2}s^{\backslash j}=-\theta s_{j}s^{\backslash j}+b_{j}s^{ \backslash j}-b_{j}\theta (1-s_{j}^{2})s^{\backslash j}$$
However, as $s$ is $k$-sparse, we have that $\sum_{k\in[d]}^{}s_{k}^{2}=k\cdot \frac{1}{k}=1$. It follows that $\left\| s^{ \backslash j} \right\|^{2}_{2}=1-s_{j}^{2}$. Hence,  $$\text{Cov}(z^{ \backslash j}, w_{j})=-\theta s_{j}s^ {\backslash j}+b_{j}(1-\theta(1-s^{2}_{j}))s^{ \backslash j}=-\theta s_{j}s^ {\backslash j}+\theta s_{j}s^{ \backslash j}=0$$
We conclude that $w_{j},z^{ \backslash j}$ are independent as they are uncorrelated jointly Gaussian.

---
#### Problem 2.3
We have that: $$\text{Var}(w_{j})=\mathbb{E}[(z_{j}-(\beta ^{*}_{j})^\top z^{ \backslash j})^{2}]=\mathbb{E}[z_{j}^{2}]-2\mathbb{E}[z_{j}(z^{ \backslash j})^\top]\beta ^{*}_{j}+(\beta ^{*}_{j})^\top\mathbb{E}[z^{\backslash j}(z^{\backslash j})^\top]\beta ^{*}_{j}$$As $\mathbb{E}[z_{j}^{2}]=\text{Var}(z_{j})=1-s_{j}^{2}$, $\mathbb{E}[z_{j}(z^{ \backslash j})^\top]=\text{Cov}(z_{j},z^{ \backslash j})=-\theta s_{j}(s^{ \backslash j})^\top$ and $\mathbb{E}[z^{ \backslash j}(z^{\backslash j})]=\text{Var}(z^{ \backslash j})=I_{d-1}-\theta s^{ \backslash j}(s^{ \backslash j})^\top$. Hence, $$\text{Var}(w_{j})=(1-s_{j}^{2})
+2\theta s_{j}(s^{ \backslash j})^\top \beta ^{*}_{j}+\left\| \beta ^{*}_{j} \right\| ^{2}_{2}-\theta((s^{ \backslash j})^\top \beta_{j})^{2}$$Now, notice that $(s^{ \backslash j})^\top \beta ^{*}_{j}=-b_{j}\left\| s^{ \backslash j} \right\|^{2}_{2}=-b_{j}(1-s_{j}^{2})$ and $\left\| \beta ^{*}_{j} \right\|^{2}_{2}=b_{j}^{2}\left\| s^{ \backslash j} \right\|^{2}_{2}=  b ^{2}_{j}(1-s_{j}^{2})$. Therefore, by setting $\eta:=(1-s^{2}_{j})$, we have:$$\text{Var}(w_{j})=\eta-2\theta s_{j}b_{j}\eta+b ^{2}_{j}\eta-\theta  b_{j}^{2} \eta^{2}=\eta-2\theta s_{j}b_{j}\eta+b ^{2}_{j}(1-\theta \eta)\eta=\eta-2\theta s_{j}b_{j}\eta+b _{j}\theta s_{j}\eta=\eta-\theta s_{j}b_{j}\eta$$However, as $\theta=\frac{k}{k+1}$, we have that $\theta(1-s_{j}^{2})\leq 1$ and: $$\theta s_{j}b_{j}=\frac{\theta^{2}s_{j}^{2}}{1-\theta(1-s^{2}_{j})}\geq 0$$This proves that $\text{Var}(w_{j}),= (1-\theta s_{j}b_{j})\eta\leq \eta\leq 1$

---
#### Problem 2.4
Let $j\in [d]$. We denote the $j$-th column of $Z$ as $Z_{j}$. Then, $$\mathbb{P}(\left\| Z_{j} \right\|\leq 2\sqrt{ n } )=\mathbb{P}(\left\| Z_{j} \right\| ^{2}\leq 4n)=\mathbb{P}\left( \sum_{i\in[n]}^{}z_{i}(j)^{2}\leq 4n \right)$$Now, notice that $z_{1}(j),\dots,z_{n}(j)\sim \mathcal{N}(0,1-\theta s_{j}^{2})$ i.i.d. Hence, for $\sigma^{2}:= 1-\theta s^{2}$