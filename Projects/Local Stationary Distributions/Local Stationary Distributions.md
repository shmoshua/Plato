#Project 

If we have $$P_{t}=\exp(-t(I-P))=\sum_{k=0}^\infty \frac{(-t(I-P))^k}{k!}$$Then, $$$$

> [!definition] Defintion (Total Variance)
> Let $\pi,\nu\in \Delta(\Omega)$. Then, $$\|\pi-\nu\|_{\text{TV}}:=\sup_{f:\Omega \to[0,1]}\left| \mathbb{E}_{\pi}f-\mathbb{E}_{\nu}f \right| $$
---

> [!lemma] Lemma (Total Variance)
> Let $\pi,\nu\in \Delta(\Omega)$ and $f:\Omega\to \mathbb{R}$. Then, $$\left| \mathbb{E}_{\pi}f-\mathbb{E}_{\nu}f \right| \leq (f_{\max}-f_{\min})\cdot  \|\pi-\nu\|_{\text{TV}}$$

> [!proof]-
> If $f$ is constant, then both sides are 0 and the statement holds. 
> Otherwise, let $f:\Omega\to \mathbb{R}$. We define: $$g:\Omega\to[0,1],\quad x\mapsto \frac{f(x)-f_{\text{min}}}{f_{\text{max}}-f_{\min}}$$
> We have: $$\|\pi-\nu\|_{\text{TV}}\geq  \left| \mathbb{E}_{\pi}g-\mathbb{E}_{\nu}g \right| =\frac{1}{f_{\text{max}}-f_{\text{min}}}\left| \mathbb{E}_{\pi}f -\mathbb{E}_{\nu}f\right| $$