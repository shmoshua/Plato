 #Project #Roadmap 

### 1. Background
#### 1. Glauber Dynamics
![[Glauber Dynamics#^77c48c]]

---
![[Glauber Dynamics#^a44026]]
![[Glauber Dynamics#^76ec7d|p]]

---
#### 2. Locally Stationary Distributions
##### 2.1 Total Variance and Dirichlet Form
![[Local Stationary Distributions#^6965b1]]

---
![[Local Stationary Distributions#^740eb0]]
![[Local Stationary Distributions#^f7cf08|p]]

---
![[Local Stationary Distributions#^7b987c]]

---
> [!lemma] Proposition 1 (Alternative definitions of Dirichlet Form)
> Let $(P,\pi)$ be a reversible Markov chain. For $f,g:\Omega\to \mathbb{R}$, $$\mathcal{E}(f,g)=\braket{ f , (I-P)g }_{\pi} :=\sum_{x\in \Omega}^{}\pi(x)f(x)(g(x)-(Pg)(x))$$

> [!proof]-
> We have that: $$\begin{aligned}2\mathcal{E}_{P}(f,g)&=\sum_{x,y}^{}\pi(x)P(x,y)(f(x)-f(y))(g(x)-g(y))\\&=\sum_{x,y}\pi(x)P(x,y)\left[ f(x)g(x)-f(x)g(y)-f(y)g(x)+f(y)g(y) \right]\\&=2\sum_{x,y}\pi(x)P(x,y)f(x)g(x)-2\sum_{x,y}\pi(x)P(x,y)f(x)g(y)\\&=2\sum_{x}\pi(x)f(x)g(x)-2\sum_{x,y}\pi(x)P(x,y)f(x)g(y)\\&=2\sum_{x}\pi(x)f(x)(g(x)-(Pg)(x))\\&=2\braket{ f , (I-P)g } _{\pi}\end{aligned}$$

---
![[Local Stationary Distributions#^773377]]
![[Local Stationary Distributions#^ec2483|p]]

---
##### 2.2 MLSI
> [!definition] Definition (Modified Log-Sobolev)
> A reversible Markov chain $(P,\pi)$ satisfies a ***modified log-Sobolev inequality (MLSI)*** with constant $C$, 
> 1. if for any $f:\Omega\to \mathbb{R}_{> 0}$, we have: $$\mathcal{E}_{P}(f,\log f)\geq C \cdot \text{Ent}(f)$$where $\text{Ent}(f):=\mathbb{E}_{\pi}[f \log f]-\mathbb{E}_{\pi}f \cdot\mathbb{E}_{\pi}\log f$. 
- **Related definition**: $C_{\text{MLSI}}$ is the largest such constant $C$.
---
> [!lemma] Proposition 1 (Subadditivity of Entropy)
> Let $f:\Omega\to \mathbb{R}_{> 0}$. If $\pi=\bigotimes_{i}\pi_{i}$, then: $$\text{Ent}(f)\leq \sum_{i\in[n]}^{}\mathbb{E}_{x_{-i}\sim \pi_{-i}}[\text{Ent}(f(\cdot ,x_{-i}))]$$

> [!proof]-
> We wlog assume that $\mathbb{E}_{\pi} f = 1$. Then, let $\mu\in \Delta(\Omega)$ s.t. $d\mu=f d\pi$. Observe that: $$D(\mu_{x_{i}|x_{-i}}\|\pi_{i})=\pi_{i}(x_{i})f(x)  \log f(x)+\pi_{i}(-x_{i})f(x^{\oplus  i})  \log f(^{\oplus  i})$$
> We have that: $$\text{Ent}_{\pi_{i}}(f(\cdot ,x_{-i}))=\int  \, dx $$
---
> [!h] Example 1
> Let $\pi$ be a distribution over $\{ \pm 1 \}^n$ with independent coordinates. Then,
> 1. $C_{\text{MLSI}}\geq \frac{1}{n}$.

> [!proof]-
> The Markov chain is given by: $$\mathbb{P}(x\to x^{\oplus  i})=\frac{1}{n}\cdot \pi_{i}(-x_{i})$$Then, let $f:\Omega\to \mathbb{R}_{> 0}$ be arbitrary. First, notice that: $$\begin{aligned}\text{Ent}_{i}(f(\cdot ,x_{-i}))&=\pi(x_{i})(f(x)\log f(x))+\pi(-x_{i})(f(x^{\oplus  i})\log f(x^{\oplus  i}))\\&\quad \quad -(\pi(x_{i})f(x)+\pi(-x_{i})f(x^{\oplus  i}))(\pi(x_{i})\log f(x)+\pi(-x_{i})\log f(x^{\oplus  i}))\\&=\pi(x_{i})\pi(-x_{i})f(x)\log f(x)+\pi(x_{i})\pi(-x_{i})f(x^{\oplus i})\log f(x^{\oplus i})\\&\quad\quad-\pi(x_{i})\pi(-x_{i})f(x)\log f(x^{\oplus  i})-\pi(x_{i})\pi(-x_{i}) f(x^{\oplus  i})\log f(x)\\&=\pi(x_{i})\pi(-x_{i})\left[ (f(x)-f(x^{\oplus i})) (\log f(x)-\log f(x^{\oplus i})) \right] \end{aligned}$$
> 
> We have: $$\begin{aligned}\mathcal{E}_{P}(f,\log f)&=\frac{1}{2}\mathbb{E}_{x\sim \pi}\left[ \frac{1}{n}\sum_{i\in[n]}^{} \pi_{i}(-x_{i})(f(x)-f(x^{\oplus i}))\log \frac{f(x)}{f(x^{\oplus  i})}\right]\\&=\frac{1}{2n}\sum_{i\in[n]} \mathbb{E}_{x\sim\pi}\left[ \pi_{i}(-x_{i})(f(x)-f(x^{\oplus  i})) \log \frac{f(x)}{f(x^{\oplus  i})}\right]\\&=\frac{1}{n}\sum_{i\in[n]} \mathbb{E}_{x_{-i}\sim \pi_{-i}}\left[  \pi(x_{i})  \pi_{i}(-x_{i})(f(x)-f(x^{\oplus  i})) \log \frac{f(x)}{f(x^{\oplus  i})}\right]\\&=\frac{1}{n}\sum_{i\in[n]} \mathbb{E}_{x_{-i}\sim \pi_{-i}}\left[  \text{Ent}_{i}(f(\cdot ,x_{-i}))\right]\\&\geq \frac{1}{n}\text{Ent}(f)\end{aligned} $$

---
> [!lemma] Theorem 1 (MLSI Concentration)
> Let $\mu$ be an arbitrary distribution over $\{ \pm 1 \}^n$ s.t. $C_{\text{MLSI}}\geq \alpha$. Then, 
> 1. for any $f:\{ \pm 1 \}^n\to \mathbb{R}$ that is $1$-Hamming-Lipschitz, $$\mathbb{P}_{x\sim \mu}(\left| f(x)-\mathbb{E}_{\mu}f \right| \geq t)\leq 2\exp \left( -\frac{\alpha t^{2}}{2} \right) $$
---
##### 2.3 Measure Decomposition
> [!definition]
> Let $\pi\in \Delta(\mathbb{R}^n)$. Let $\rho\in \Delta(\mathbb{R}^n)$ and $\{ \pi_{z} \}_{z\in \mathbb{R}^n}\subseteq \Delta(\mathbb{R}^n)$. 
> 1. We say $(\rho,\pi_{z})$ is a ***measure decomposition*** of $\pi$ if: $$\pi=\mathbb{E}_{z\sim\rho}\pi_{z}$$

---
> [!h] Example 1
> For any $\pi\in \Delta(\mathbb{R}^n)$, 
> 1. $(\pi,\delta_{z})$ is a measure decomposition of $\pi$.

##### 2.4 Symmetric KL
> [!definition] 
> We define: 
> 1. $\text{SKL}(\pi,\nu):=D(\nu\|\pi)+D(\pi\|\nu)$. 
---
> [!lemma] 
> Then, 
> $$\text{SKL}(\pi,\nu)=\frac{1}{2}\mathbb{E}_{x,y \sim \pi}\left[ (f(x)-f(y))\log \frac{f(x)}{f(y)} \right] $$

> [!proof]-
> We have that: $$\begin{aligned}\text{SKL}(\pi,\nu)&=\int f \log f \, d\pi+\int \frac{d\pi}{d\nu}\log \frac{d\pi}{d\nu} \, d\nu \\&=\int f \log f \, d\pi+\int \log \frac{d\pi}{d\nu} \, d\pi \\&=\mathbb{E}_{\pi}[(f-1)\log f] \end{aligned}$$Now, $$\begin{aligned}\mathbb{E}\left[ (f(x)-f(y))\log \frac{f(x)}{f(y)} \right]&=\mathbb{E}\left[ f(x)\log f(x)\right]+\mathbb{E}[f(y)\log f(y)]-\mathbb{E}[f(x)\log f(y)]-\mathbb{E}[f(y)\log f(x)]\\&=2\mathbb{E}\left[ f(x)\log f(x)\right]-2\mathbb{E}[\log f(x)]\\&=2\mathbb{E}_{\pi}[(f-1)\log f]\end{aligned}$$

---
> [!lemma] 
> For any distribution $\nu$ and Markov chain $(P,\pi)$ and $T> 0$, for $t \sim \text{Uni}[0,T]$, we have: $$\mathbb{E}_{t\sim [0,T]}\mathcal{E}_{P}(f_{t},\log f_{t})\leq \frac{D(\nu\|\pi)}{T}\leq \frac{\log \frac{1}{\pi_{\text{min}}}}{T}$$

> [!proof]-
> We have that: $$\begin{aligned}0&\leq D(\nu_{t}\|\pi)\\&=D(\nu\|\pi)-\int_{0}^{T} \mathcal{E}(f_{t},\log f_{t}) \, dt\\&=D(\nu\|\pi)- T\cdot \mathbb{E}_{t\sim [0,T]} \mathcal{E}(f_{t},\log f_{t}) \end{aligned}$$
---
> [!lemma] Theorem 1
> Let $(P,\pi)$ be a reversible Markov chain and $v_{0}\in \Delta(\Omega)$.
> 1. For $T:=\frac{1}{\delta \varepsilon} \log\left( \frac{1}{\pi_{\min}} \right)$ and $t\sim \text{Uni}([0,T])$, $v_{t}$ is $\varepsilon$-locally stationary with probability $1-\delta$.

> [!proof]-
> We have that: $$\mathbb{P}(\mathcal{E}_{P}(f_{t},\log f_{t})\geq \varepsilon)\leq \frac{\log  \frac{1}{\pi_{\min}}}{\varepsilon T}=\delta$$

---
> [!lemma] Theorem 2
> Let $(P,\pi)$ be a reversible Markov chain and $\nu\in \Delta(\Omega)$. Let $f:=\frac{ d\nu}{d\pi}$.
> $$\mathcal{E}_{P}(f,\log f)\geq 2 \cdot D(Pv\|v)\geq 4\left\| v-Pv \right\| ^{2}_{\text{TV}}$$

> [!proof]-
> We have that: $$\begin{aligned}\mathcal{E}_{P}(f,\log f)&=\mathbb{E}_{x\sim \pi}\mathbb{E}_{y\sim x}(f(x)-f(y))\log \frac{f(x)}{f(y)}\\&=\sum_{x,y\in \Omega}^{}\pi(x)P(x,y)f(x)\log \frac{f(x)}{f(y)}-\sum_{x,y\in \Omega}^{}\pi(y)P(y,x)f(y)\log \frac{f(x)}{f(y)}\\&=\sum_{x,y\in \Omega}^{}\pi(x)P(x,y)f(x)\log \frac{f(x)}{f(y)}+\sum_{x,y\in \Omega}^{}\pi(x)P(x,y)f(x)\log \frac{f(x)}{f(y)}\\&=2\mathbb{E}_{x\sim \pi}\mathbb{E}_{y \sim x}f(x)\log \frac{f(x)}{f(y)}\\&=2\mathbb{E}_{x\sim \nu}\mathbb{E}_{y \sim x}\log \frac{f(x)}{f(y)}\\&=2\mathbb{E}_{x\sim \nu}\log f(x)-2 \mathbb{E}_{y \sim P \nu} \log f(y)\\&=2\left[ \mathbb{E}_{\nu}\log f-\mathbb{E}_{P\nu}\log \frac{d(P\nu)}{d\pi}+\mathbb{E}_{P\nu}\log \frac{d(P\nu)}{d\pi}-\log f \right]\\&=2\left[ D(\nu\|\pi)-D(P\nu\|\pi)+D(P\nu\|\nu) \right]  \\&\geq 2D(P\nu\|\nu)\\&\geq 4 \|\nu-P\nu\|^{2}_{\text{TV}}\end{aligned}$$
---
> [!lemma] Corollary 3
> Let $\phi:\Omega\to \mathbb{R}$ be in $C_{b}(\Omega)$ and $\nu$ a $\varepsilon$-locally-stationary measure. Then, $$\left| \mathbb{E}_{\nu}\phi-\mathbb{E}_{P\nu}\phi \right| \leq \left\| \phi \right\| _{\infty}\sqrt{ \varepsilon }$$

> [!proof]-
> By total variance, $$\begin{aligned}\left| \mathbb{E}_{\nu}\phi-\mathbb{E}_{P\nu}\phi \right|& \leq 2\left\| \phi \right\| _{\infty}\left\| \nu-P\nu \right\| _{\text{TV}}\\&\leq \left\| \phi \right\| _{\infty}\sqrt{ \mathcal{E}_{p}(f,\log f) }\\&\leq \left\| \phi \right\| _{\infty} \sqrt{ \varepsilon }\end{aligned}$$

---
> [!lemma] Lemma
> For an $\varepsilon$-locally stationary distribution $\nu$ with relative density $f$, and for $x\sim \nu$ and $y\sim x$, with probability at least $1-\delta$, we have $\frac{f(x)}{f(y)}=1\pm O\left( \sqrt{ \frac{\varepsilon}{\delta} } \right)$ where $\delta\geq 2\varepsilon$

> [!proof]+
> We have: $$\mathbb{E}_{x\sim \nu}\mathbb{E}_{y \sim x}\left( 1-\frac{f(y)}{f(x)} \right)\log \frac{f(x)}{f(y)}=\mathbb{E}_{x\sim \pi}\mathbb{E}_{y \sim x}(f(x)-f(y))\log \frac{f(x)}{f(y)}<\varepsilon$$Now, $$\mathbb{P}\left( \left( 1-\frac{f(y)}{f(x)} \right)\log \frac{f(x)}{f(y)}\geq \frac{\varepsilon}{\delta} \right) <\delta$$Hence, $$ \left( 1-\frac{f(y)}{f(x)} \right)\log \frac{f(x)}{f(y)}< \frac{\varepsilon}{\delta}$$