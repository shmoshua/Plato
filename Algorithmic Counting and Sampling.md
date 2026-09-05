#Roadmap 

##### Spectral Methods, Conductance and Canonical Paths

> [!lemma] Lemma 1.4
> Let $\mu,\nu$ be two distributions on $\Omega$. Then, for $f:= d\nu / d\mu$, we have that: $$\left\| \nu-\mu \right\| _{\text{TV}}^{2}\leq \frac{1}{4}\text{Var}_{\mu}(f)$$

> [!proof]-
> We have that: 
> $$\begin{aligned}\left\| \nu-\mu \right\|_{\text{TV}}&=\frac{1}{2}\sum_{x}\mu(x)\left| f(x)-1 \right|\leq \frac{1}{2}\sqrt{ \sum_{x} \mu(x)\left( f(x)-1 \right) ^{2} } \sqrt{ \sum_{x}\mu(x) }=\frac{1}{2}\sqrt{ \text{Var}_{\mu}(f) } \end{aligned}$$as $\mathbb{E}_{\mu}[f]=\sum_{x}^{}\mu(x)f(x)=\sum_{x}\nu(x)=1$.

We have that the Dirichlet form is given by: $$\begin{aligned}\mathcal{E}_{P}(f,g):=\braket{ f , (I-P)g } _{\mu}
&=\sum_{x}\mu(x)f(x)(g(x)-(Pg)(x))\\
&=\sum_{x,y}\mu(x)P(x,y)(f(x)g(x)-f(x)g(y))\end{aligned}$$Similarly, $$\mathcal{E}_{P}(f,g)=\sum_{y,x}\mu(x)P(x,y)(f(y)g(y)-f(y)g(x))$$Hence, $$\mathcal{E}_{P}(f,g)=\frac{1}{2}\sum_{x,y}\mu(x)P(x,y)(f(x)-f(y))(g(x)-g(y))$$

We have that: $$\text{Var}_{\mu}(f)=\braket{ f , f } _{\mu}-\braket{ f , 1 } ^{2}_{\mu}=\sum_{x,y}\mu(x)\mu(y)(f(x)^{2}-f(x)f(y))=\frac{1}{2}\sum_{x,y}^{}\mu(x)\mu(y)(f(x)-f(y))^{2}$$

---
> [!lemma] Proposition 1.5
> Let $P$ be a reversible Markov chain. We have that: $$1-\lambda_{2}(P)=\text{inf}_{f} \frac{\mathcal{E}_{P}(f,f)}{\text{Var}_{\mu}(f)}$$where the infimum is over all functions with non-zero variance.

> [!proof]-
> By the spectral theorem, let $\phi_{1},\dots,\phi_{n}$ be the ONB with eigenvalues $\lambda_{1},\dots,\lambda_{n}$ respectively. Then, $\phi_{1}=1$ and $\braket{ f , \phi_{1} }_{\mu}=\mathbb{E}_{\mu}[f]$. Therefore, $$\text{Var}_{\mu}(f)=\left\| f-\mathbb{E}_{\mu}[f]1 \right\| ^2_{\mu}=\left\| \sum_{i=2}^{n}\braket{ f , \phi_{i} } _{\mu}\phi_{i} \right\| ^{2}_{\mu}=\sum_{i=2}^{n}\braket{ f , \phi_{i} } _{\mu} ^{2}$$
> Further, $(I-P)f = \sum_{i=1}^{n}(1-\lambda_{i})\braket{ f , \phi_{i} }_{\mu} \phi_{i}$ and: $$\mathcal{E}_{P}(f,f)=\braket{ f , (I-P)f } _{\mu}=\sum_{i=1}^{n}(1-\lambda_{i})\braket{ f , \phi_{i} } _{\mu}=\sum_{i=2}^{n}(1-\lambda_{i})\braket{ f , \phi_{i} } _{\mu}^2\ge (1-\lambda_{2})\sum_{i=2}^{n}\braket{ f , \phi_{i} } _{\mu}^2$$Therefore, $$\frac{\mathcal{E}_{P}(f,f)}{\text{Var}_{\mu}(f)}\ge \frac{(1-\lambda_{2})\text{Var}_{\mu}(f)}{\text{Var}_{\mu}(f)}=1-\lambda_{2}$$
> For the converse, we have that: $$\frac{\mathcal{E}_{P}(\phi_{2},\phi_{2})}{\text{Var}_{\mu}(\phi_{2})}=1-\lambda_{2}$$

---
> [!definition]
> We have that: $$\text{T}_{mix}(\varepsilon;\mu_{0},P):=\min \{ t\geq 0:\left\| \mu_{0}P^t - \mu \right\| _{\text{TV}}\leq \varepsilon \}$$
---
> [!lemma] Theorem 1.6 (Spectral Gap implies Rapid Mixing)
> Let $P$ be an ergodic Markov chain on $\Omega$ which is reversible w.r.t. $\mu$. Then, for every $x\in \Omega$ and $\varepsilon>0$, $$\text{T}_{mix}(\varepsilon;\delta_{x},P)\le \frac{1}{\gamma_{*}}\log \left( \frac{1}{2\varepsilon \sqrt{ \mu(x) }} \right) $$

> [!proof]+
> We first claim that: $$\text{Var}_{\mu}\left( \frac{d(\delta_{x}P^t)}{d\mu} \right)\le \lambda_{*}^{2t}\frac{1-\mu(x)}{\mu(x)}$$We have $\frac{d(\nu P)}{d\mu}(x)=\frac{(\nu P)(x)}{\mu(x)}=\frac{\sum_{y}^{}\nu(y)P(y,x)}{\mu(x)}=\frac{\sum_{y}^{}\nu(y)P(y,x)}{\mu(x)}=\frac{\sum_{y}^{}\nu(y)P(x,y)}{\mu(y)}=\left( P\cdot \frac{d\nu}{d\mu} \right)(x)$. Hence, $$\begin{aligned}\text{Var}_{\mu}\left( \frac{d\nu}{d\mu} \right)-\text{Var}_{\mu}\left( \frac{d(\nu P)}{d\mu} \right)&=\left\langle \frac{d\nu}{d\mu},\frac{d\nu}{d\mu}\right\rangle_{\mu}-\left\langle \frac{d\nu}{d\mu},1\right\rangle_{\mu}^{2}-\left\langle \frac{d\nu}{d\mu},P^{2}\frac{d\nu}{d\mu}\right\rangle_{\mu}+\left\langle  \frac{d\nu}{d\mu},1\right\rangle_{\mu}^{2} \\&=\left\langle  \frac{d\nu}{d\mu},(I-P^{2})\frac{d\nu}{d\mu}\right\rangle_{\mu}\\&=\mathcal{E}_{P^{2}}\left( \frac{d\nu}{d\mu},\frac{d\nu}{d\mu} \right)\\&\ge (1-\lambda_{*}^{2})\text{Var}_{\mu}\left( \frac{d\nu}{d\mu} \right)\end{aligned}$$Therefore, $\lambda^{2}_{*}\text{Var}\left( \frac{d\nu}{d\mu} \right) \geq \text{Var}\left( \frac{d(\nu P)}{d\mu} \right)$. Hence, for any $t$, $$\text{Var}\left( \frac{d(\delta_{*}P^t)}{d\mu} \right)\le \lambda^{2t}_{*}\text{Var}_{\mu}\left( \frac{d \delta_{x}}{d\mu} \right)=\lambda_{*}^{2t}\left( \frac{1-\mu(x)}{\mu(x)} \right) $$Therefore, for $t \geq \frac{1}{\gamma_{*}}\log (\frac{1}{2\varepsilon \sqrt{ \mu(x) }})$, we have that: $$\left\| \delta_{x}P^t-\mu \right\| _{\text{TV}}\leq \frac{\lambda_{*}^{t}}{2} \frac{1}{\sqrt{ \mu(x) }}$$