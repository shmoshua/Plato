#Series #Algorithms 

#### Problem 1
We have that:
1. Let $v,w\in V$. 
	1. if $v=w$, then: $$D_{vv}-A_{vv}=w(v)=\sum_{(u,v)\in E} \frac{1}{r(u,v)}=\sum_{(u,v)\in E}^{}\frac{B^{2}_{v(u,v)}}{r(e)}=\sum_{e\in E}^{}\frac{B^2_{ve}}{r(e)}=\sum_{e,e'\in E}^{}B_{ve}R^{-1}_{ee'}B_{ve'}=(BR^{-1}B)_{vv}$$
	2. if $v\neq w$ with $(v,w)\in E$, then: $$D_{vw}-A_{vw}=-\frac{1}{r(v,w)}=\sum_{e\in E}^{}\frac{B_{ve}B_{we}}{r(e)}=(BR^{-1}B)_{vw}$$
	3. if $v\neq w$ with $(v,w)\notin E$, then $D_{vw}-A_{vw}=0=(BR^{-1}B)_{vw}$.
2. We have: $$x^\top Lx=\sum_{u,v\in V}^{}x(u)x(v)(D_{uv}-A_{uv})$$
	1. if $u=v$, then $x(u)x(v)(D_{uv}-A_{uv})=x(v)^{2}\sum_{(w,v)}^{} \frac{1}{r(w,v)}$.
	2. if $u\neq v$ and $(u,v)\notin E$, then $x(u)x(v)(D_{uv}-A_{uv})=0$.
	3. if $u\neq v$ and $(u,v)\in E$, then $x(u)x(v)(D_{uv}-A_{uv})=-\frac{x(u)x(v)}{r(u,v)}$.
 
Hence, $$\begin{align}x^\top Lx&=2\sum_{(u,v)\in E}^{}\frac{x(v)^{2} }{r(u,v)}-\sum_{(u,v)\in E}^{}\frac{x(u)x(v)}{r(u,v)}\\&=2\sum_{v\in V}^{} \sum_{(u,v)\in E}^{} \frac{x(v)^{2}}{r(u,v)}-\sum_{(u,v)\in E}^{}\frac{x(u)x(v)}{r(u,v)}\end{align}$$

---
#### Problem 2
1. Let $V$ be a finite-dim Hilbert space (which we assume this question is based on) and assume $A:V\to V$. We first show a couple of trivial properties about the orthogonal complement:
	1. **Claim 1**: for any vector subspace $W\subseteq V$, $W^{\bot\bot}=W$. 
		For $x\in W$ and $y\in W^{\bot}$, $\braket{ x , y }=0$. Hence, $x\in W^{\bot\bot}$ and $W\subseteq W^{\bot{\bot}}$. Now, $$\text{dim}(W^{\bot\bot})=\text{dim}(V)-\text{dim}(W^{\bot})=\text{dim}(V)-\text{dim}(V)+\text{dim}(W)=\text{dim}(W)$$Hence, $W=W^{\bot\bot}$.
	2. **Claim 2**: for any two vector subspaces $U,W\subseteq V$, $U\subseteq V$ then $V^{\bot}\subseteq U^{\bot}$.
		Let $w\in V^{\bot}$. Then, for any $u\in U\subseteq V$, we have that $\braket{ w,u }=0$. 
   
   Let $y\in \text{im }A$ with $y=Az$. Then, for any $x\in \text{ker }A^\top$, we have that: $$\braket{ x , y } =\braket{ x , Az } =\braket{ A^\top x , z } =\braket{ 0 , z } =0$$Hence, $\text{im }A\subseteq (\text{ker }A^\top)^{\bot}$.
   
   For the converse, it suffices to show that $(\text{im }A)^{\bot}\subseteq \text{ker }A^\top$. Indeed, then by Claim 1 and 2, it follows that $(\text{ker }A^\top)^{\bot}\subseteq(\text{im }A)^{\bot\bot}=\text{im }A$. Let $x\in (\text{im }A)^{\bot}$. Then, for all $z\in V$, $$0=\braket{ x , Az } =\braket{ A^\top x , z } $$Hence, it holds that $A^\top x=0$. This concludes the proof.

2. 