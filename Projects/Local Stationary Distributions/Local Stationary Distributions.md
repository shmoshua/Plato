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
> 1. the ***Dirichlet form*** of $f,g$ w.r.t. $P$ is given by: $$\mathcal{E}_{P}(f,g):=\frac{1}{2}\mathbb{E}_{x\sim \pi}\mathbb{E}_{y\sim x}(f_{x}-f_{y})\cdot (g_{x}-g_{y})$$

^7b987c

- **Related definition**: We have that:
  $$\mathcal{E}_{P}(f,\log f)=\sum_{x,y\in \Omega}^{}\pi(x)P(x,y)(f(x)-f(y))\log \frac{f(x)}{f(y)}$$ ^c36365

---
> [!lemma] Proposition 1 (Derivative of KL Divergence)
> Let $(P,\pi)$ be an ergodic, reversible [[Markov chain]]. Then, $$\frac{d}{dt}D(v_{t}\|\pi)=-\mathcal{E}(f_{t},\log f_{t})$$

^773377

> [!proof]-
> First, notice that $P,-I$ commute. Hence,  $e^{t(P-I)}=e^{tP}e^{-t}$. Now, for $x,y\in \Omega$, we can write:
> 
> $$P_{t}(x,y)=e^{-t(I-P)}(x,y)=e^{-t}e^{tP}(x,y)=e^{-t}\sum_{n=0}^{\infty}\frac{t^n}{n!}P^n(x,y)$$
> 1. Now, we have: $$\begin{aligned}\pi(x)P^n(x,y)&=\pi(x)\sum_{z}^{}P(x,z)P^{(n-1)}(z,y)\\&=\sum_{z}^{}\pi(z)P(z,x)P^{(n-1)}(z,y)\\&=\sum_{z}^{}\pi(y)P^{n-1}(y,z)P(z,x)\\&=\pi(y)P^n(y,x)\end{aligned}$$By ergodicity we have that $P_{t}(x,y)>0$ whenever $t>0$. Since $$(P_{t}f_{0})(x)=\sum_{y}^{}P_{t}(x,y)\frac{dv_{0}(y)}{d\pi(y)}=f_{t}(y)$$and $\sum_{x}^{}f_{0}(x)=1$, we have that $f_{t}>0$ on $\Omega$.
> 2. Therefore, $$\begin{aligned}\frac{d}{dt}D(v_{t}\| \pi)&=\int \frac{d}{dt}f_{t}\log f_{t}  \, d\pi\\&=\int  \left( \frac{d}{dt}f_{t} \right)\log f_{t}+\left( \frac{d}{dt}f_{t} \right)  \, d\pi\\&=\int  L^{*}f_{t}(\log f_{t}+1) \, d\pi\\&=\int  f_{t}L(\log f_{t}) \, d\pi \\&=-\mathcal{E}_{P}(f_{t},\log f_{t})\end{aligned}$$

^ec2483

---
