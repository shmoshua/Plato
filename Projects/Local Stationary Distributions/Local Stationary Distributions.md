#Project 

> [!definition] Defintion (Total Variance)
> Let $\pi,\nu\in \Delta(\Omega)$. Then, $$\|\pi-\nu\|_{\text{TV}}:=\sup_{f:\Omega \to[0,1]}\left| \mathbb{E}_{\pi}f-\mathbb{E}_{\nu}f \right| $$

^6965b1

---

> [!lemma] Lemma (Total Variance)
> Let $\pi,\nu\in \Delta(\Omega)$ and $f:\Omega\to \mathbb{R}$. Then, $$\left| \mathbb{E}_{\pi}f-\mathbb{E}_{\nu}f \right| \leq (f_{\max}-f_{\min})\cdot  \|\pi-\nu\|_{\text{TV}}$$

^740eb0

> [!proof]-
> If $f$ is constant, then both sides are 0 and the statement holds. 
> Otherwise, let $f:\Omega\to \mathbb{R}$. We define: $$g:\Omega\to[0,1],\quad x\mapsto \frac{f(x)-f_{\text{min}}}{f_{\text{max}}-f_{\min}}$$
> We have: $$\|\pi-\nu\|_{\text{TV}}\geq  \left| \mathbb{E}_{\pi}g-\mathbb{E}_{\nu}g \right| =\frac{1}{f_{\text{max}}-f_{\text{min}}}\left| \mathbb{E}_{\pi}f -\mathbb{E}_{\nu}f\right| $$

^f7cf08

---
> [!definition] Definition (Dirichlet Form)
> Let $(P,\pi)$ be a reversible [[Markov chain]]. For $f,g:\Omega\to \mathbb{R}$, 
> 1. the ***Dirichlet form*** of $f,g$ w.r.t. $P$ is given by: $$\mathcal{E}_{P}(f,g):=\mathbb{E}_{x\sim \pi}\mathbb{E}_{y\sim x}(f_{x}-f_{y})\cdot (g_{x}-g_{y})$$

^7b987c

- **Related definition**: We have that:
  $$\mathcal{E}_{P}(f,\log f)=\sum_{x,y\in \Omega}^{}\pi(x)P(x,y)(f(x)-f(y))\log \frac{f(x)}{f(y)}$$ ^c36365

---
> [!lemma] 
> Let $(M,P,\pi)$ be an ergodic, reversible Markov chain. Then, $$\frac{d}{dt}\text{KL}(v_{t}\|\pi)=-\mathcal{E}(f_{t},\log f_{t})$$

^773377

> [!proof]-
> First, notice that $P,-I$ commute. Hence,  $e^{t(P-I)}=e^{tP}e^{-t}$. Now, for $x,y\in \Omega$, we can write:
> 
> $$P_{t}(x,y)=e^{-t(I-P)}(x,y)=e^{-t}e^{tP}(x,y)=e^{-t}\sum_{n=0}^{\infty}\frac{t^n}{n!}P^n(x,y)$$
> 1. Now, we have: $$\begin{aligned}\pi(x)P^n(x,y)&=\pi(x)\sum_{z}^{}P(x,z)P^{(n-1)}(z,y)\\&=\sum_{z}^{}\pi(z)P(z,x)P^{(n-1)}(z,y)\\&=\sum_{z}^{}\pi(y)P^{n-1}(y,z)P(z,x)\\&=\pi(y)P^n(y,x)\end{aligned}$$By ergodicity we have that $P_{t}(x,y)>0$ whenever $t>0$. Since $$(P_{t}f_{0})(x)=\sum_{y}^{}P_{t}(x,y)\frac{dv_{0}(y)}{d\pi(y)}=f_{t}(y)$$and $\sum_{x}^{}f_{0}(x)=1$, we have that $f_{t}>0$ on $\Omega$.
> 2. Therefore, $$\begin{aligned}\frac{d}{dt}\text{KL}(v_{t}\mid \pi)=\int \frac{d}{dt}f_{t}\log f_{t}  \, dx \end{aligned}$$

> [!proof]-
> Notice that: $$-\mathcal{E}(f_{t},\log f_{t})=-\mathbb{E}_{x \sim \pi}\mathbb{E}_{y \sim x}(f_{t}(x)-f_{t}(y)) \frac{\log f_{t}(x)}{\log f_{t}(y)}$$
> We have that: $$\frac{d}{dt}\text{KL}(v_{t}\|\pi)=\frac{d}{dt}\int_{\Omega} \frac{\log v_{t}(x)}{\log \pi(x)} \, dv_{t}= \mathbb{E}_{x\sim v_{t}}\frac{\log v_{t}(x)}{\log \pi(x)}$$
> $$\text{KL}(v_{t}\|\pi)=\int \log \left( \frac{dv_{t}}{d\pi} \right)  \, dv_{t}=\int f_{t}\log f_{t} \, d\pi  $$Notice that $\int \frac{d}{dt}f_{t}\, d\pi=\frac{d}{dt}\int f_{t}  \, d\pi=\frac{d}{dt}\int_{}^{}  1\, dv_{t}=0$.$$\begin{aligned}\frac{d}{dt}\text{KL}(v_{t}\|\pi)&=\int \frac{d}{dt}f_{t}\log f_{t} \, d\pi\\&=\int  \dot{f}_{t}(\log f_{t}+1)d\pi\\&=\int  \dot{f}_{t}(\log f_{t})d\pi\\&=\mathbb{E}_{x\sim \pi}\left[ \left( \frac{d}{dt}f_{t}(x) \right)\cdot  \log f_{t}(x) \right] \end{aligned}$$
> $$\mathbb{E}_{y-x}\left[ \frac{f_{t}(x)-f_{t}(y)}{\log f_{t}(y)} \right] =\sum_{y} P(x,y)\frac{f_{t}(x)-f_{t}(y)}{\log f_{t}(y)}$$

---
> [!definition] Definition (Modified Log-Sobolev)
> A Markov chain $(P,\pi)$ satisfies a ***modified log-Sobolev inequality (MLSI)*** with constant $C$, if for any $f:\Omega\to \mathbb{R}_{> 0}$, we have: $$\mathcal{E}_{P}(f,\log f)\geq C \cdot \text{Ent}(f)$$where $\text{Ent}(f):=\mathbb{E}_{\pi}[f \log f]-\mathbb{E}_{\pi}f \cdot\mathbb{E}_{\pi}\log f$. 
- **Related definition**: $C_{\text{MLSI}}$ is the best such constant $C$.
---
> [!lemma] Lemma
> Let $\pi$ be a distribution over $\{ \pm 1 \}^n$ with independent coordinates. Then,
> 1. $C_{\text{MLSI}}\geq \frac{1}{n}$.

> [!proof]-
> The Markov chain is given by: $$\mathbb{P}(x\to x^{\oplus  i})=\frac{1}{n}\cdot \pi_{i}(-x_{i})$$Then, let $f:\Omega\to \mathbb{R}_{> 0}$ be arbitrary. 
> First, notice that: $$\begin{aligned}\text{Ent}_{i}(f(\cdot ,x_{-i}))&=\pi(x_{i})(f(x)\log f(x))+\pi(-x_{i})(f(x^{\oplus  i})\log f(x^{\oplus  i}))\\&\quad \quad -(\pi(x_{i})f(x)+\pi(-x_{i})f(x^{\oplus  i}))(\pi(x_{i})\log f(x)+\pi(-x_{i})\log f(x^{\oplus  i}))\\&=\pi(x_{i})\pi(-x_{i})f(x)\log f(x)+\pi(x_{i})\pi(-x_{i})f(x^{\oplus i})\log f(x^{\oplus i})\\&\quad\quad-\pi(x_{i})\pi(-x_{i})f(x)\log f(x^{\oplus  i})-\pi(x_{i})\pi(-x_{i}) f(x^{\oplus  i})\log f(x)\\&=\pi(x_{i})\pi(-x_{i})\left[ (f(x)-f(x^{\oplus i})) (\log f(x)-\log f(x^{\oplus i})) \right] \end{aligned}$$
> 
> We have: $$\begin{aligned}\mathcal{E}_{P}(f,\log f)&=\mathbb{E}_{x\sim \pi}\left[ \frac{1}{n}\sum_{i\in[n]}^{} \pi_{i}(-x_{i})(f(x)-f(x^{\oplus i}))\log \frac{f(x)}{f(x^{\oplus  i})}\right]\\&=\frac{1}{n}\sum_{i\in[n]} \mathbb{E}_{x\sim\pi}\left[ \pi_{i}(-x_{i})(f(x)-f(x^{\oplus  i})) \log \frac{f(x)}{f(x^{\oplus  i})}\right]\\&=\frac{2}{n}\sum_{i\in[n]} \mathbb{E}_{x_{-i}\sim \pi_{-i}}\left[  \pi(x_{i})  \pi_{i}(-x_{i})(f(x)-f(x^{\oplus  i})) \log \frac{f(x)}{f(x^{\oplus  i})}\right]\\&=\frac{2}{n}\sum_{i\in[n]} \mathbb{E}_{x_{-i}\sim \pi_{-i}}\left[  \text{Ent}_{i}(f(\cdot ,x_{-i}))\right]\\&\geq \frac{2}{n}\text{Ent}(f)\end{aligned} $$

---
> [!lemma] 
> Let $\mu$ be an arbitrary distribution over $\{ \pm 1 \}^n$ s.t. $C_{\text{MLSI}}\geq \alpha$. Then, 
> 1. for any $f:\{ \pm 1 \}^n\to \mathbb{R}$ that is $1$-Lipschitz, $$\mathbb{P}_{x\sim \mu}(\left| f(x)-\mathbb{E}_{\mu}f \right| \geq t)\leq 2\exp \left( -\frac{\alpha t^{2}}{2} \right) $$
---
##### Symmetric KL
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