#Series #Algorithms 

#### Problem 1
We have that:
1. Let $v,w\in V$. Then: $$(BR^{-1}B)_{vw}=\sum_{e,e'\in E}^{}B_{ve}R^{-1}_{ee' }B_{we'}=\sum_{e\in E}^{}\frac{B_{ve}B_{we}}{r(e)}$$
	1. if $v\neq w$, then: $$(BR^{-1}B)_{vw}=-\frac{\mathbb{1}_{(v,w)\in E}}{r_{vw}}=0-\frac{\mathbb{1}_{(v,w)\in E}}{r_{vw}}=D_{vw}-A_{vw}$$
	2. if $v=w$, then: $$(BR^{-1}B)_{vv}=\sum_{e\in E}^{}\frac{B_{ve}^{2}}{r(e)}=\sum_{u:(u,v)\in E} \frac{1}{r(u,v)}=w(v)=D_{vv}-A_{vv}$$
2. We have: $$\begin{align}x^\top Lx&=\sum_{u,v\in V}^{}x_{u}x_{v}(D_{uv}-A_{uv})\\&=\sum_{v\in V}x_{v}^{2}\sum_{u:(u,v)\in E}^{} \frac{1}{r_{uv}}-2\sum_{(u,v)\in E}\frac{x_{u}x_{v}}{r_{uv}}\\\\&=\sum_{(u,v)\in E}\frac{x_{u}^{2}+x_{v}^{2}}{r_{uv}}-2\sum_{(u,v)\in E}\frac{x_{u}x_{v}}{r_{uv}}\\&=\sum_{(u,v)\in E}^{}\frac{(x_{u}-x_{v})^{2}}{r_{uv}}\end{align}$$
	Hence, for any $x\in \mathbb{R}^V$, $x^\top Lx\geq 0$ as $r\geq 0$ and $L$ is positive semi-definite.

3. From 2, we see that $x^\top Lx=0$ if and only if $x\in \braket{ \mathbb{1}_{C_{1}} , \mathbb{1}_{C_{2}},\dots,\mathbb{1}_{C_{k}} }$, i.e. the subspace spanned by the characteristic functions of the connected components $C_{1},\dots,C_{k}$ of $G$. Now, as $L$ is positive semi-definite, $\text{ker }L=\{ x\in \mathbb{R}^V : x^\top L x=0 \}=\braket{ \mathbb{1}_{C_{1}} , \mathbb{1}_{C_{2}},\dots,\mathbb{1}_{C_{k}}}$.
	

---
#### Problem 2
1. Let $V$ be a finite-dim Hilbert space (which we assume this question is based on) and assume $A:V\to V$. We first show a couple of trivial properties about the orthogonal complement:
	1. **Claim 1**: for any vector subspace $W\subseteq V$, $W^{\bot\bot}=W$. 
		For $x\in W$ and $y\in W^{\bot}$, $\braket{ x , y }=0$. Hence, $x\in W^{\bot\bot}$ and $W\subseteq W^{\bot{\bot}}$. Now, $$\text{dim}(W^{\bot\bot})=\text{dim}(V)-\text{dim}(W^{\bot})=\text{dim}(V)-\text{dim}(V)+\text{dim}(W)=\text{dim}(W)$$Hence, $W=W^{\bot\bot}$.
	2. **Claim 2**: for any two vector subspaces $U,W\subseteq V$, $U\subseteq V$ then $V^{\bot}\subseteq U^{\bot}$.
		Let $w\in V^{\bot}$. Then, for any $u\in U\subseteq V$, we have that $\braket{ w,u }=0$. 
   
   Let $y\in \text{im }A$ with $y=Az$. Then, for any $x\in \text{ker }A^\top$, we have that: $$\braket{ x , y } =\braket{ x , Az } =\braket{ A^\top x , z } =\braket{ 0 , z } =0$$Hence, $\text{im }A\subseteq (\text{ker }A^\top)^{\bot}$.
   
   For the converse, it suffices to show that $(\text{im }A)^{\bot}\subseteq \text{ker }A^\top$. Indeed, then by Claim 1 and 2, it follows that $(\text{ker }A^\top)^{\bot}\subseteq(\text{im }A)^{\bot\bot}=\text{im }A$. Let $x\in (\text{im }A)^{\bot}$. Then, for all $z\in V$, $$0=\braket{ x , Az } =\braket{ A^\top x , z } $$Hence, it holds that $A^\top x=0$. This concludes the proof.

2. We show that if $G$ is connected, $\text{ker }B^\top=\braket{ 1  }$, i.e. it is spanned by $1$. Firstly, notice that $$(B^\top 1)_{e}=\sum_{v\in V}^{}B_{v,e}=1-1=0$$and by linearity, $\braket{ 1  }\subseteq \text{ker }B^\top$. Conversely, if $\lambda\in \text{ker }B^\top$, then: $$0=(B^\top\lambda)_{e}=\sum_{v\in V}^{}B_{v,e}\lambda_{v}=\lambda_{u}-\lambda_{w},\quad \forall e=(u,w)\in E$$This means, for any $u,v\in V$, if there is a $(u,v)$-path, then $\lambda_{u}=\lambda_{v}$. Hence, as $G$ is connected, $\lambda\in \braket{ 1  }$. 
   
   Therefore, $$\exists f: Bf=d \iff d\in \text{im }B=(\text{ker }B^\top)^{\bot}=\braket{ 1  }^{\bot} \iff 1^\top d =0 $$

---
#### Problem 3
We first find the gradient of $c$. 
$$(\nabla_{x}c)_{v}=x_{v}L_{vv}+\sum_{v':v'\neq v}x_{v'}L_{vv'}-d_{v}=\sum_{v'}^{}x_{v'}L_{vv'}-d_{v}=(L x-d)_{v}$$
Therefore, $Lx=d$ if and only if $\nabla_{x}c=0$.

---
#### Problem 4
1. We have that: $$x^\top Bf=\sum_{v\in V}^{}\sum_{e\in E}^{}x_{v}B_{v,e}f_{e}=\sum_{e\in E}^{}\sum_{v\in V}^{}x_{v}B_{v,e}f_{e}=\sum_{(u,w)\in E}^{}(x_{w}-x_{u})f_{(u,w)}$$Hence, as $x^\top(Bf-d)=0$, $$\frac{1}{2}\sum_{e}^{}r(e)f(e)^{2}=\frac{1}{2}\sum_{(u,v)\in E}^{}r_{uv}f_{uv}^{2}-x^\top(Bf-d)=x^\top d-\sum_{(u,v)\in E}^{}\left( (x_{v}-x_{u})f_{uv}-\frac{1}{2}r_{uv}f^{2}_{uv} \right)$$
2. We have that: $$(x_{v}-x_{u}-r_{uv}f_{uv})^{2}=(x_{v}-x_{u})^{2}-2(x_{v}-x_{u})r_{uv}f_{uv}+r_{uv}^{2}f_{uv}^{2}\geq 0$$Hence, by dividing both sides by $2r_{uv}$, $$(x_{v}-x_{u})f_{uv}-\frac{1}{2}r_{uv}f_{uv}^{2}\leq \frac{1}{2}\frac{(x_{v}-x_{u})^{2}}{r_{uv}}$$
3. By exercise 1.2, we have that: $$\begin{align}x^\top d-\frac{1}{2}x^\top Lx&=x^\top d-\frac{1}{2}\sum_{(u,v)\in E}^{}\frac{(x_{u}-x_{v})^{2}}{r_{uv}}\\&\leq x^\top d-\sum_{(u,v)\in E}^{}\left( (x_{v}-x_{u})f_{uv}-\frac{1}{2}r_{uv}f^{2}_{uv} \right)\\&=\frac{1}{2}\sum_{e}^{}r_{e}f_{e}^{2}\\&=\frac{1}{2}f^\top Rf\end{align}$$
4. We have that $B\tilde{f}=BR^{-1}B^\top \tilde{x}=L\tilde{x}=d$. Further, $$\tilde{x}^\top d-\frac{1}{2}\tilde{x}^\top L\tilde{x}=\frac{1}{2}\tilde{x}^\top d=\frac{1}{2}\tilde{x}^\top B\tilde{f}=\frac{1}{2}\tilde{f}^\top R \tilde{f}$$
5. We have that by iii) $$\tilde{x}^\top d-\frac{1}{2}\tilde{x}^\top L\tilde{x}=\frac{1}{2}\tilde{f} ^\top R\tilde{f}\geq {x}^\top d-\frac{1}{2}{x}^\top L{x},\quad \forall x\in \mathbb{R}^V$$Further, we have $B\tilde{f}=d$ and:$$\frac{1}{2}\tilde{f}^\top R \tilde{f}=\tilde{x}^\top d-\frac{1}{2}\tilde{x}^\top L\tilde{x}\leq \frac{1}{2}f^\top Rf,\quad \forall f\in \mathbb{R}^E,Bf=d$$

---
#### Problem 5
1. Let $f$ be convex. Let $\alpha\in \mathbb{R}$ and $x,y\in S_{\alpha}$. Then, for any $t\in[0,1]$, $$f(tx+(1-t)y)\leq tf(x)+(1-t)f(y)\leq t\alpha+(1-t)\alpha=\alpha$$Hence, $tx+(1-t)y\in S_{\alpha}$ for all $t\in[0,1]$ and $S_{\alpha}$ is convex. 
2. No, consider $f:\mathbb{R}\to \mathbb{R},x\mapsto x+\sin x$. Then, $f$ is monotonously increasing and for all $\alpha\in \mathbb{R}$, $S_{\alpha}$ is given by an interval, which is convex. However, $f$ is not convex as: $$f\left( \frac{\pi}{2} \right)=\frac{\pi}{2}+1> 0+\frac{\pi}{2}=\frac{f(0)}{2}+\frac{f(\pi)}{2}$$

---
#### Problem 6
By Boundedness theorem, $f$ is bounded on $\mathcal{F}$ and: $$m:=\inf_{x\in \mathcal{F}}f(x)>-\infty$$Now, we have to show that there exists $x^{*}\in \mathcal{F}$ s.t. $f(x^{*})=m$. Now, by the definition of infimum, there exists $x_{n}\in \mathcal{F}$ s.t. $f(x_{n})\leq m + \frac{1}{n}$. Now, $(x_{n})\subseteq \mathcal{F}$ is a bounded sequence as $\mathcal{F}$ is bounded. Hence, by Bolzano-Weierstrass, there is a convergent subsequence $(x_{n_{k}})_{k}\subseteq \mathcal{F}$ s.t. $x_{n_{k}}\to x^{*}$. However, by closedness of $\mathcal{F}$, we have that $x^{*}\in \mathcal{F}$. Hence, $$m\leq f(x^{*})=f(\lim_{k \to \infty } x_{n_{k}})=\lim_{ k \to \infty } f(x_{n_{k}})\leq m+\lim_{ k \to \infty } \frac{1}{n_{k}}=m$$This shows that, $f(x^{*})=m$. 

---
#### Problem 7
Let $X$ be the domain and $x,y\in X$. Then, for $t\in[0,1]$, there exists $i\in[k]$ s.t. $$f(tx+(1-t)y)=f_{i}(tx+(1-t)y)\leq tf_{i}(x)+(1-t)f_{i}(y)\leq tf(x)+(1-t)f(y)$$
and $f$ is convex.

---
#### Problem 8
Let $x,x'\in X$ and $t\in[0,1]$. Then by definition of infimum, for any $\varepsilon>0$ there exists $y,y'\in S$ s.t. $f(x,y)\leq g(x) + \varepsilon$ and $f(x',y')\leq g(x')+\varepsilon$. As convexity of $S$, we have $ty+(1-t)y'\in S$. Hence, 

$$\begin{align}g(tx+(1-t)x')&=\inf_{z\in S}f(tx+(1-t)x',z)\\&\leq f(t(x,y)+(1-t)(x',y'))\\&\leq tf(x,y)+(1-t)f(x',y')\\&\leq tg(x)+(1-t)g(x')+\varepsilon \end{align}$$By sending $\varepsilon \to 0$, we have that $g(tx+(1-t)x')\leq tg(x)+(1-t)g(x')$ and $g$ is convex.

---
#### Problem 9
We have:
1. $f(x)=\left| x \right|^6=x^6$. Hence, $\nabla^2_{x}f=30x^4\geq 0$. Therefore, $f$ is convex.
2. $\nabla^{2}_{x}\exp=\exp(x)\geq 0$ for $x\in (0,\infty)$. Hence, $f$ is convex.
3. Let $(x,y):=\left( \frac{1}{4}, \frac{1}{4} \right)$ and $(x',y'):=\left( \frac{3}{4}, \frac{3}{4} \right)$ Then, for $t=\frac{1}{2}$,$$\sqrt{\frac{1}{2}+\frac{1}{2} }=1> \frac{1}{2}\sqrt{ \frac{1}{2} }+\frac{1}{2}\sqrt{ \frac{3}{2} }$$as $\left( \sqrt{ \frac{1}{2} }+\sqrt{ \frac{3}{2} } \right)^{2}=2+\sqrt{ 3 }<4$. Hence, $f$ is not convex.
4. Let $(x,y):= (\frac{1}{2},0)$ and $(x',y'):=\left( 0, \frac{1}{2} \right)$. Then, for $t=\frac{1}{2}$, $$f(t(x,y)+(1-t)(x',y'))=\frac{1}{16}>0=tf(x,y)+(1-t)f(x',y')$$Hence, $f$ is non-convex.

---
#### Problem 10
1. We show this via induction over $n$. 
	1. If $n=2$, then this follows from the definition of convexity. 
	2. Let $n\geq 3$, then notice that by convexity of $S$, $\frac{\theta_{1}}{1-\theta_{n}}x_{1}+\dots+\frac{\theta_{n-1}}{1-\theta_{n}}x_{n-1}\in S$. Hence, $$\begin{align}f(\theta_{1}x_{1}+\dots+\theta_{n}x_{n})&=f\left( (1-\theta_{n})\left( \frac{\theta_{1}}{1-\theta_{n}}x_{1}+\dots+\frac{\theta_{n-1}}{1-\theta_{n}}x_{n-1} \right) +\theta_{n}x_{n}\right)\\&\leq (1-\theta _{n})f\left( \frac{\theta_{1}}{1-\theta_{n}}x_{1}+\dots+\frac{\theta_{n-1}}{1-\theta_{n}}x_{n-1} \right) +\theta _{n}f(x_{n})\\&\leq \theta_{1}f(x_{1})+\dots+\theta_{n-1}f(x_{n-1})+\theta_{n}f(x_{n})\end{align}$$as $\frac{1}{1-\theta_{n}}\sum_{i=1}^{n-1}\theta_{i}=1$.
2. We have that $f:x\mapsto-\log x$ is a convex function on $(0,\infty)$ as: $$\nabla^{2}_{x}f=\frac{1}{x^{2}}\geq 0$$Hence, $$-\log\left( \frac{1}{n}\sum_{i=1}^{n}x_{i} \right)\leq -\frac{1}{n}\sum_{i=1}^{n}\log(x_{i})=-\log\left( \prod_{i=1}^{n}x_{i} \right)^{1 / n}$$Therefore, $\left( \prod_{i=1}^{n}x_{i} \right)^{1/n}\leq \frac{1}{n}\sum_{i=1}^n x_{i}$.
3. We have that: $$\frac{1}{\left( \prod_{i=1}^{n}x_{i} \right)^{1/n}}=\left( \prod_{i=1}^{n} \frac{1}{x_{i}}\right)^{1/n}\leq \frac{1}{n}\sum_{i=1}^{n} \frac{1}{x_{i}}$$As both sides are non-negative, by taking the reciprocal we have our statement.

---

