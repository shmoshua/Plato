#Project 

> [!definition] Defintion (Total Variance)
> Let $\pi,\nu\in \Delta(\Omega)$. Then, $$\|\pi-\nu\|_{\text{TV}}:=\sup_{f:\Omega \to[0,1]}\left| \mathbb{E}_{\pi}f-\mathbb{E}_{\nu}f \right| $$
---

> [!lemma] Lemma (Total Variance)
> Let $\pi,\nu\in \Delta(\Omega)$ and $f:\Omega\to \mathbb{R}$. Then, $$\left| \mathbb{E}_{\pi}f-\mathbb{E}_{\nu}f \right| \leq (f_{\max}-f_{\min})\cdot  \|\pi-\nu\|_{\text{TV}}$$

> [!proof]-
> If $f$ is constant, then both sides are 0 and the statement holds. 
> Otherwise, let $f:\Omega\to \mathbb{R}$. We define: $$g:\Omega\to[0,1],\quad x\mapsto \frac{f(x)-f_{\text{min}}}{f_{\text{max}}-f_{\min}}$$
> We have: $$\|\pi-\nu\|_{\text{TV}}\geq  \left| \mathbb{E}_{\pi}g-\mathbb{E}_{\nu}g \right| =\frac{1}{f_{\text{max}}-f_{\text{min}}}\left| \mathbb{E}_{\pi}f -\mathbb{E}_{\nu}f\right| $$

---
> [!definition] Definition (Dirichlet Form)
> For $f,g:\Omega\to \mathbb{R}$, 
> 1. the ***Dirichlet form*** of $f,g$ w.r.t. $P$ is given by: $$\mathcal{E}_{P}(f,g):=\mathbb{E}_{x\sim \pi}\mathbb{E}_{y\sim x}(f_{x}-f_{y})\cdot (g_{x}-g_{y})$$
> 	where $\pi$ is the stationary distribution of $P$.

---
> [!lemma] 
> Let $(P,\pi)$ be a Markov chain. Then, $$\frac{d}{dt}\text{KL}(v_{t}\|\pi)=-\mathcal{E}(f_{t},\log f_{t})$$

> [!proof]+
> We have that: $$\text{KL}(v_{t}\|\pi)=\mathbb{E}_{x\sim v_{t}}\frac{\log v_{t}(x)}{\log \pi(x)}$$