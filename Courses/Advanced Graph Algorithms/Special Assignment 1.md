#Series #AGAO 

#### Problem 1. A different kind of Smoothness
##### Part A. 
1. This follows from the extremal value theorem and the fact that $x\mapsto x^\top y$ is a continuous function and $S^{n-1}:=\{ x\in \mathbb{R}^n: \|x\|=1 \}$ is non-empty compact. For the compactness, we have by Heine-Borel that $S^{n-1}$ is bounded and closed as $S^1$ is a preimage of a closed set w.r.t. the norm. The fact that it is continuous follows from the fact that it is linear. 
2. Let $y\in \mathbb{R}^n$ and $a\in \mathbb{R}$, then: $$\|ay\|_{*}=\sup_{x:\|x\|=1}ax^\top y=a\sup_{x:\|x\|=1}x^\top y\leq \left| a \right| \cdot \|y\|_{*}$$Conversely, let $\left\| y \right\|_{*}=x'^\top y$. Then, $\left| a \right|\|y\|_{*}=a\cdot (\underbrace{ \text{sgn}(a)\cdot x' }_{ x'' })^\top y=x''^\top(ay)\leq \left\| ay \right\|_{*}$ where $\left\| x'' \right\|=\left\| x' \right\|=1$. For the triangle inequality, $$\left\| y+y' \right\|_{*}=\sup_{x:\|x\|=1}x^\top(y+y')\leq \sup_{x:\|x\|=1}x^\top y+\sup_{x:\|x\|=1}x^\top y'=\|y\|_{*}+\|y'\|_{*} $$Finally, let $\|y\|_{*}=0$. Then, for all unit vector $e_{i}\in \mathbb{R}^n$ we have that $y_{i}=e_{i}^\top y\leq 0$. By considering $-e_{i}\in \mathbb{R}^n$, we have that $\left| y_{i} \right|=0$ for all $i\in[n]$ and therefore $y=0$. This proves that the dual norm is a norm.
3. Let $x,y\in \mathbb{R}^n$. If $x=0$, then the statement holds trivially. Otherwise, $$x^\top y=\|x\| \frac{x}{\|x\|}^\top y\leq \|x\| \|y\|_{*}$$as $\|x / \|x\|\|=1$. 
4. We have that:$$\|x\|_{**}=\sup_{y: \|y\|_{*}=1}y^\top x\leq \sup_{y: \|y\|_{*}=1}\|x\|\|y\|_{*}=\|x\|$$
5. This follows directly from Hahn-Banach, as there exists $y_{0}\in \mathbb{R}^n$ s.t. $\|y_{0}\|_{*}=1$ and $x^\top y_{0}=\|x\|$. Therefore, $$\|x\|=y_{0}^\top x\leq \|x\|_{**}$$
---
##### Part B.
1. Let $x\in \mathbb{R}^n$. We will show that $(\|x\|_{M})_{*}=\|x\|_{M^{-1}}$. If $x=0$, then we trivially have the equality. Hence, assume that $x\neq 0$. As $M$ is SPD, so is $M^{-1}$ and we have that: $$y:= \frac{M^{-1}x}{\sqrt{ x^\top M^{-1}x }}$$which is well-defined. Then, $\left\| y \right\|_{M}=\frac{1}{x^\top M^{-1}x}\cdot x^\top M^{-1}MM^{-1}x=1$ and $(\|x\|_{M})_{*}\geq \sqrt{ x^\top M^{-1}}= \|x\|_{M^{-1}}$.
   
   Conversely, for any $\|y\|_{M}=1$, let $z:= M^{1 /2}y$. Then, $\|z\|_{2}=\|y\|_{M}=1$. Therefore, by Cauchy-Schwarz:$$(\|x\|_{M})_{*}\leq \sup_{y:\|y\|_{M}=1}y^\top x\leq \sup_{z:\|z\|_{2}=1}z^\top M^{-1/2}x\leq \|M^{-1/2}x\|_{2}=\sqrt{ x^\top M^{-1}x }=\|x\|_{M^{-1}}$$
   This proves the statement.
2. Let $x\in \mathbb{R}^n$. Again we show that $(\|x\|_{\infty})_{*}=\|x\|_{1}$. If $x=0$, the equality is trivial. For $x\neq 0$ and $\|y\|_{\infty}=1$, we have that: $$x^\top y= \sum_{i\in[n]}^{}x_{i}y_{i}\leq\|y\|_{\infty}\sum_{i\in[n]}^{}\left| x_{i} \right| =\|x\|_{1}\|y\|_{\infty}$$Hence, $(\|x\|_{\infty})_{*}=\sup_{y:\|y\|_{\infty}=1}y^\top x\leq \|x\|_{1}$. Conversely, let $y\in \mathbb{R}^n$ where $y_{i}:=\text{sgn}(x_{i})$. Then, $$\|x\|_{1}=\sum_{i\in[n]}^{}\left| x_{i} \right| =\sum_{i\in[n]}^{}x_{i}y_{i}=y^\top x\leq  (\|x\|_{\infty})_{*}$$as $\|y\|_{\infty}=1$ given by $x\neq 0$. 

---
##### Part C.
1. A dual vector map for $\|\cdot\|_{M}$ is given by: $$(\cdot )^{\sharp}:\mathbb{R}^n\to \mathbb{R}^n,\quad x\mapsto \frac{Mx}{\sqrt{ x^\top Mx }}$$Then, the properties hold for $x=0$ and for all non-zero $x$, $x^\top x^{\sharp}=\frac{x^\top Mx}{\sqrt{ x^\top Mx }}=\sqrt{ x^\top Mx }=\|x\|_{M}$. Further, $$(\left\| x^{\sharp} \right\|_{M})_{*}=\left\| x^{\sharp} \right\| _{M^{-1}}=\frac{x^\top Mx}{x^\top Mx}=1 $$To show the uniqueness, notice that for $x=0$, 

---
##### Part D.
Let $x,y\in \mathbb{R}^n$. Then, by Proposition 3.3.4 we have that: $$\begin{aligned}f(y)&=f(x)+\int_{0}^{1} \nabla f(x_{\theta})^\top (y-x) \, d\theta\\&=f(x)+\int_{0}^{1} \nabla f(x)^\top (y-x) \, d\theta+\int_{0}^{1} (\nabla f(x_{\theta})-\nabla  f(x))^\top (y-x) \, d\theta\\&\leq f(x)+\int_{0}^{1} \nabla f(x)^\top (y-x) \, d\theta+\int_{0}^{1} \|\nabla f(x_{\theta})-\nabla  f(x)\|_{*}\left\| y-x \right\|  \, d\theta\end{aligned} $$where the last inequality follows from Part A.3. Now, as $f$ is $\beta$-gradient Lipschitz, $$\begin{aligned}f(y)&\leq f(x)+\int_{0}^{1} \nabla f(x)^\top (y-x) \, d\theta+\int_{0}^{1} \beta\theta\left\| y-x \right\|^{2}  \, d\theta\\&\leq f(x)+\nabla f(x)^\top (y-x) +\frac{\beta}{2}\left\| y-x \right\|^{2}  \end{aligned}$$

---
##### Part E.
Similarly to the gradient descent in the script, We perform Gradient Descent by: $$x_{i+1}:=x_{i}- \frac{1}{\beta} \nabla f(x_{i})$$Then, notice that using Part D and Part A.3 we can analogously follow the proof s.t. we have the guarantee: $$f(x_{k})-f(x^{*})\leq \frac{2\beta \left\| x_{0}-x^{*} \right\| ^{2}}{k+1},\quad \forall k\geq 1$$
Now, let $k:= \left\lceil \frac{2\beta \left\| x_{0}-x^{*} \right\|^{2}}{ \varepsilon}\right\rceil$. Then, we have that $f(x_{k})-f(x^{*})\leq \varepsilon$. In each iteration, we have 1 access to $\nabla f(\cdot)$ and computing $x_{i+1}$ takes at most $O(n)$ arithmetic operations. Hence, as $k=O\left( \frac{\beta R^{2}}{\varepsilon} \right)$ we have the desired algorithm by outputting $\tilde{x}:=x_{k}$.

---
##### Part F.

For $x\in \mathbb{R}^n$, define the following function:$$g:\mathbb{R}^n\to \mathbb{R},\quad y\mapsto f(y)-\nabla f(x)^\top y$$
Then, we claim that for any $y,z\in \mathbb{R}^n$, $$g(z)\leq g(y)+\nabla g(y)^\top (z-y)+\frac{\beta}{2}\left\| z-y \right\| ^{2}$$We have that: $$\begin{aligned}f(z)&\leq f(y)+\nabla f(y)^\top(z-y)+\frac{\beta}{2}\left\| z-y \right\| ^{2}\\&=f(y)+(\nabla f(y)-\nabla f(x))^\top(z-y)+\nabla f(x)^\top (z-y)+\frac{\beta}{2}\left\| z-y \right\| ^{2}\end{aligned}$$Noticing that $\nabla g(y)=\nabla f(y)-\nabla f(x)$ and rearranging, we have our claim. 

Now similarly, by convexity of $f$,$$\begin{aligned}g(y)&=f(y)-\nabla f(x)^\top y\\&\geq f(z)-\nabla f(x)^\top z+\nabla f(z)^\top (y-z) -\nabla f(x)^\top (y-z)\\&=g(z)+\nabla  g(z)^\top (y-z)\end{aligned}$$and $g$ is convex as well. Hence, $x$ is a global minimum for $g$ and let $t^{*}$ be a minimizer of $\phi(t):=g(y)-\left\| \nabla g(y) \right\|_{*} t+\frac{\beta}{2}t^{2}$. Then, $t^{*}=\left\| \nabla g(y) \right\|_{*} / \beta$. 

Now, let $w\in \mathbb{R}^n$ with $\|w\|=1$ s.t. $\left\| \nabla g(y) \right\|_{*}=\nabla g(y)^\top w$, which exists. Then, by defining $z:=y-t^{*} w$, we have:  $$g(x)\leq g(z)\leq g(y)-t^{*}\nabla  g(y)^\top w+\frac{\beta}{2}\cdot  (t^{*})^{2}\|w\|^{2}=g(y)-\frac{\|\nabla  g(y)\|_{*}^{2}}{2\beta}$$Therefore, $$\frac{\left\| \nabla f(x)-\nabla f(y) \right\| ^{2}_{*}}{2\beta}\leq g(y)-g(x)=f(y)-f(x)+\nabla f(x)^\top(x-y)$$and by symmetry, $$\frac{\left\| \nabla f(x)-\nabla f(y) \right\| ^{2}_{*}}{2\beta}\leq f(x)-f(y)-\nabla f(y)^\top(x-y)$$By adding the two inequalities, $$\left\| \nabla f(x)-\nabla f(y) \right\| ^{2}_{*}\leq \beta(\nabla f(x)-\nabla f(y))^\top(x-y)\leq \beta \|\nabla f(x)-\nabla f(y)\|_{*}\|x-y\|$$Now if $\left\| \nabla f(x)-\nabla f(y) \right\|_{*}=0$, then the statement is trivially true. Otherwise, we get the statement by dividing both sides with $\left\| \nabla f(x)-\nabla f(y) \right\|_{*}$.

---
##### Part G.
We have that $\text{H}_{f}(x)$ is positive semidefinite for all $x$. Hence, $f$ is a convex function. 

Now, using the second-order Taylor, for some $z\in [x,y]$ we have:$$\begin{aligned}f(y)&=f(x)+\nabla f(x)^\top(y-x)+\frac{1}{2}(y-x)\text{H}_{f}(z)(y-x)\\&\leq f(x)+\nabla f(x)^\top(y-x)+\frac{\beta}{2}\|y-x\|^{2}\end{aligned}$$The rest follows from Part F.

---
##### Part H.
1. Let $j:=\arg\max_{i}x(i)$. Then, $$m(x)=\frac{1}{\lambda}\log \left( \sum_{i}^{}e^{\lambda x(i)} \right)\leq \frac{1}{\lambda}\log \left( ne^{\lambda x(j)} \right)\leq \frac{\log(n)}{\lambda}+x(j) $$For the left inequality, we have: $$m(x)=\frac{1}{\lambda}\log \left( \sum_{i}^{}e^{\lambda x(i)} \right)\geq \frac{1}{\lambda}\log \left( e^{\lambda x(j)} \right)=x(j)$$as $\exp\geq 0$.
2. We compute the Hessian of $m$, we have that: $$\partial_{i}m(x)=\frac{e^{\lambda x(i)}}{\sum_{i}^{}e^{\lambda x(i)}}=:p(i),\quad \partial^{2}_{i,j}m(x)= \frac{(\sum_{i}^{}e^{\lambda x(i)})\mathbb{1}_{i=j}\lambda e^{\lambda x(i)}-\lambda e^{\lambda x(i)}e^{\lambda x(j)}}{(\sum_{i}^{}e^{\lambda x(i)})^{2}}$$Now, notice that $$\partial^{2}_{i,j}m(x)=\lambda p(i)\left( \mathbb{1}_{i=j}-p(j) \right) $$Hence, $\text{H}_{m}(x)=\lambda(\text{diag}(p)-pp^\top)$. For any $y\in \mathbb{R}^n$, $$y^\top \text{H}_{m}(x)y=\lambda \left( \sum_{i}^{}p(i)y(i)^{2}- \left( \sum_{i}p(i)y(i) \right)^{2}\right)$$As $\sum_{i}p(i)=1$ and $p(i)\geq 0$ for all $i$, we can treat $p$ as a probability measure on $[n]$. Hence, we have that $y^\top \text{H}_{m}(x)y=\lambda(\mathbb{E}[y^{2}]-\mathbb{E}[y]^{2})=\lambda \cdot\text{Var}(y)\geq 0$. Similarly, $$y^\top \text{H}_{m}(x)y\leq \lambda \sum_{i}^{}p(i)y(i)^{2}\leq \lambda \sum_{i}^{}p(i)\left\| y \right\|^{2}_{\infty}=\lambda \|y\|^{2}_{\infty} $$Therefore, $m$ satisfies the condition for Part G and this shows the statement.

---
##### Part I
1. Let $h(x):=f_{0}+Px$. Then, $\nabla g(x)=P^\top \nabla s(h(x))$. As we have that the dual of $\|\cdot\|_{\infty}$ is $\|\cdot\|_{1}$, we have that: $$\begin{aligned}\left\| \nabla g(x) -\nabla g(y)\right\|_{1}&=\left\| P^\top (\nabla  s(h(x))-\nabla  s(h(y))) \right\|_{1} \leq \left\| P^\top \right\| _{1\to 1}\left\| \nabla  s(h(x))-\nabla s(h(y)) \right\| _{1}\end{aligned} $$Now, as $s$ is $O(\lambda)$-gradient Lipschitz, $$\left\| \nabla  g(x)-\nabla g(y) \right\| _{1}\leq O(\lambda)\cdot \left\| P^\top \right\| _{1\to 1}\cdot \left\| P(x-y) \right\|_{\infty}\leq O(\lambda)\cdot \left\| P^\top \right\| _{1\to 1}\cdot \left\| P \right\|_{\infty\to \infty}\left\| x-y \right\| _{\infty} $$Therefore, it suffices to show that $\left\| P^\top \right\|_{1\to1}=\left\| P \right\|_{\infty\to \infty}$. We have that by the definition of dual norms:$$\left\| P^\top \right\| _{1\to 1}=\sup_{\|x\|_{1}=1}\left\| P^\top x \right\|_{1}=\sup_{\|x\|_{1}=1}\sup_{\|y\|_{\infty}=1} y^\top P^\top x =\sup_{\left\| y \right\| _{\infty }=1}\left\| Py \right\| _{\infty}=\left\| P \right\| _{\infty\to \infty}$$
2. We have that: $$\left\| f_{0}+P\widehat{x} \right\| _{\infty}\leq g(\widehat{x})\leq g(x^{*})+\frac{\varepsilon}{2}\text{OPT}$$Now, let $x'\in \mathbb{R}^n$ s.t. $\|f_{0}+Px'\|_{\infty}=\text{OPT}$. Then, $$\left\| f_{0}+P\widehat{x} \right\| _{\infty}\leq g(x')+\frac{\varepsilon}{2}\text{OPT}\leq \text{OPT}+\frac{\varepsilon}{2}\text{OPT}+\frac{2\log(\left| E \right| )}{\lambda}$$Hence, by taking $\lambda=\frac{4 \log \left| E \right|}{\varepsilon \text{OPT}}$, we have the desired bound.
   
---
##### Part J
1. Notice that as $\widehat{P}$ is a projection matrix, $\widehat{P}^{2}=\widehat{P}$ and it follows that $P^{2}=P$. Now, $$Pf_{0}=P(I-P)U^{-1}\tilde{f}_{0}=0$$Let $x^{*}\in \mathbb{R}^n$ be a minimzer i.e. $\left\| f_{0}-Px^{*} \right\|_{\infty}=\text{OPT}$. Then, we have that: $$\begin{aligned}\left\| f_{0} \right\| _{\infty}=\left\| f_{0}+Px^{*}-Pf_{0}-P^{2}x^{*} \right\|_{\infty} \leq \left\| f_{0}+Px^{*} \right\|_{\infty}+\left\| P \right\|_{\infty\to \infty}\left\| f_{0}+Px^{*} \right\| _{\infty}  \end{aligned}$$This shows the claim.
   
2. We have: $$g(y)\leq g(0)=s(f_{0})\leq \left\| f_{0} \right\| _{\infty}+\frac{2\log \left| E \right| }{\lambda}\leq (1+\left\| P \right\| _{\infty\to \infty})\text{OPT}+\frac{2\log \left| E \right| }{\lambda}$$
3. Let $x\in \mathbb{R}^\left| E \right|$ with $g(x)\leq g(0)$ and $x^{*}\in X^{*}$. Then, by defining $y:=x-Px+Px^{*}$, we have that $Py=Px-Px+Px^{*}=Px^{*}$ and $g(y)=g(x^{*})$. Therefore, $y\in X^{*}$ and we have that: $$\min_{x^{*}\in X^{*}}\left\| x-x^{*} \right\| _{\infty}\leq \left\| x-y \right\| _{\infty}=\left\| Px-Px^{*} \right\| \left\| f_{0}+Px -f_{0}-Px^{*}\right\|_{\infty}$$Hence, by triangle inequality, $$\min_{x^{*}\in X^{*}}\left\| x-x^{*} \right\| _{\infty}\leq \left\| f_{0}+Px \right\| _{\infty}+\left\| f_{0}+P x^{*}\right\|_{\infty} \leq g(x)+g(x^{*})\leq 2g(x)\leq O(g(x))$$The rest follows from Part J.2.
---
#### Problem 2. Computing dissimilar test groups
##### Part A
1. We first claim that $2-\lambda_{n}\leq 2\eta(G)$. Let $S\subseteq V$ with $\left| S \right|\leq n /2$ and  $z\in \{ -1,1 \}^\left| V \right|$ s.t. $z_{v}=1$ if and only if $v\in S$. Then, notice that: $$z^\top Lz=\sum_{\{ u,v \}\in E}^{}(z_{u}-z_{v})^{2}=4\cdot  e(S,V \backslash S),\quad z^\top Dz=\sum_{v\in V}^{}d_{v} z_{v}^{2}=\sum_{v\in V}^{}d_{v}=2\left| E \right| $$Therefore, $$\lambda_{n}=\max_{x\neq 0} \frac{x^\top Lx}{x^\top Dx}\geq \frac{2e(S, V \backslash S)}{\left| E \right| }=2\left( 1-\frac{e(S)-e(V\backslash S)}{\left| E \right| } \right)=2\left( 1-\eta(S)\right)$$Hence, $$2\eta(G)=\min_{S\subseteq V: \left| S \right| \leq n /2} 2\eta(S)\geq 2-\lambda_{n} $$
   Now, we show the statement via induction over $k:=\left| S_{0} \right|$
	1. Let $k=0$. Then, $S_{0}=\varnothing$ and $(A,B)=(S_{-1},S_{1})$ and $y\in \{ +1,-1 \}^V$. Therefore, $y_{u}+y_{v}=2\cdot \mathbb{1}_{(u,v)\in E(A)\cup E(B)}$. Hence, 
	    $$q(y)=\frac{\sum_{(u,v)\in E}^{}(y_{u}+y_{v})^{2}}{\sum_{v\in V}d_{v}y_{v}^{2}}=\frac{4(e(A)+e(B))}{2\left| E \right| }$$It follows that: $$e(A)+e(B)=\frac{1}{2}\left| E \right| q(y)\leq \frac{1}{2}\left| E \right| \sqrt{ 2(2-\lambda) }\leq \frac{1}{2}\left| E \right| \sqrt{ 4\eta(G) }=\left| E \right| \sqrt{ \eta(G) }$$
	2. Let $k\geq 1$. Then, let $(A',B')$ be the output of $\text{Groups}(G[S_{0}])$ and $(A,B)$ be the output of the algorithm. Wlog assume that $(A,B)=(A'\cup S_{-1},B'\cup S_{1})$. Then this means that: $$e(A',S_{1})+e(B',S_{-1})\geq e(A',S_{-1})+e(B',S_{1})$$
	   
	   Notice that $$e(S_{0},S_{-1})+e(S_{0},S_{1})=e(A',S_{-1})+e(B',S_{-1})+e(A',S_{1})+e(B',S_{1})$$Hence, $e(A',S_{-1})+e(B',S_{1})\leq \frac{e(S_{0},S_{-1})+e(S_{0},S_{1})}{2}$. 
	   
	   Now, we introduce two claims:
		1. **Claim 1**: $\eta(G[S_{0}])\leq \eta(G)\cdot \frac{\left| E \right|}{e(S_{0})}$
		Let $T\subseteq G$. Then, let $T_{0}:= T\cap S_{0}$. We have that $$\eta(G[S_{0}])\leq\eta_{S_{0}}(T_{0})=\frac{e(T_{0})+e(S_{0} \backslash T_{0})}{e(S_{0})}\leq \frac{e(T)+e(V \backslash T)}{e(S_{0})}=\frac{e(T)+e(V \backslash T)}{\left| E \right| }\cdot \frac{\left| E \right| }{e(S_{0})}$$This proves the claim.
		1. **Claim 2**: $e(A')+e(B')\leq 2\sqrt{ \eta(G) }(\left| E \right|+e(S_{0}))$
		   From induction hypothesis and Claim 1, we have that: $$e(A')+e(B')\leq 4\sqrt{ \eta(G[S_{0}]) }e(S_{0})\leq 4\sqrt{ \eta(G) }\cdot \sqrt{ \left| E \right| e(S_{0}) }\leq 2\sqrt{ \eta(G) }(\left| E \right| +e(S_{0}))$$where the last inequality follows from AM-GM.
		2. **Claim 3**: $$\frac{4(e(S_{-1})+e(S_{1}))+e(S_{0},S_{-1})+e(S_{0},S_{1})}{\left| E \right| -e(S_{0})+e(S_{-1}\cup S_{1})}\leq 2\sqrt{ \eta(G) }$$Hence, $$4(e(S_{-1})+e(S_{1}))+e(S_{0},S_{-1})+e(S_{0},S_{1})\leq 2\sqrt{ \eta(G) }(\left| E \right| -e(S_{0})+e(S_{-1}\cup S_{1}))$$
		
		Therefore, $$\begin{aligned}e(A)+e(B)&=e(A')+e(A',S_{-1})+e(S_{-1})+e(B')+e(B',S_{1})+e(S_{1})\\&=e(A')+e(B')+\frac{e(S_{0},S_{-1})+e(S_{0},S_{1})}{2}+e(S_{-1})+e(S_{1})\\&\leq \sqrt{ \eta(G) }( 2\left| E \right| +2e(S_{0})+\left| E \right| -e(S_{0})+e(S_{-1}\cup S_{1}))\\&\leq \sqrt{ \eta(G) }( 3\left| E \right| +e(S_{0})+e(S_{-1}\cup S_{1}))\\&\leq 4\sqrt{ \eta(G) }\left| E \right| \end{aligned}$$as $e(S_{0})+e(S_{-1}\cup S_{1})\leq \left| E \right|$.

	This concludes the induction.

2. Firstly, as $q(y)\leq \sqrt{ 2(2-\lambda_{n}) }< \sqrt{ 2 q(0)}$, we have that $y\neq 0$. Hence, $S_{0}\subsetneq V$ and $e(S_{0})\leq \left| E \right|$. In other words, at each recursion, we reduce the size of the edges by at least 1. Hence, we can have at most $\left| E \right|=O(n^2)$ recursions. 
   
   In each recursion, we need $O(n^3)$ to compute $\lambda_{n}$ and $z$ via Gaussian elimination. To compute $y$, notice that we do not need to optimize it over all $\theta$, but only at $z(u)^{2}$ over all $u\in V$. Indeed, by definition $y_{\theta}$ is constant between each interval given by $z(u)^{2}$. Therefore, there are at most $O(n)$ test vectors and for each we need $O(n^2)$ operations to compute as we go over all edges. Finally, partitioning $V$ according to $y$ takes $O(n)$ time.
   
   This shows that the algorithm can be implemented in polynomial time.
---
##### Part B
1. Let $z\in \{ -1,0,1 \}^V$. Then, $z^\top Dz=\sum_{v\in V}^{}d_{v} z_{v}^{2}$. Hence, $$q(z)+\lambda_{n}\geq \frac{\sum_{\{ u,v \}\in E}^{}(z_{u}+z_{v})^{2}}{\sum_{v\in V}^{}d_{v}z_{v}^{2}}+\frac{\sum_{\{ u,v \}\in E}^{}(z_{u}-z_{v})^{2}}{\sum_{v\in V}^{}d_{v}z_{v}^{2}}=\frac{2\sum_{\{ u,v \}\in E}^{}(z_{u}^2+z_{v}^{2})}{\sum_{v\in V}^{}d_{v}z_{v}^{2}}=2$$as we have: $$2\sum_{\{ u,v \}\in E}^{}(z_{u}^2+z_{v}^{2})=\sum_{v\in V}^{}\sum_{u\in N(v)}^{}z_{v}^{2}+\sum_{u\in V}^{}\sum_{v\in N(u)}^{}z_{u}^{2}=2 \sum_{v\in V}^{}d_{v}z^{2}_{v}$$
2. We use the probabilistic method. Let $\theta \sim \text{Uni}([0,1))$. Then, let $X:=\sum_{(u,v)\in E}(y_{\theta}(u)+y_{\theta}(v))^{2}$ and $Y:=\sum_{v\in V} d_{v}y_{\theta}(v)^{2}$ which are discrete random variables as $y_{\theta}\in \{ -1,0,1 \}^V$. Now, from Problem Set 5 Exercise 7.6, it suffices to show that $\frac{\mathbb{E}[X]}{\mathbb{E}[Y]}\leq \sqrt{ 2(2-\lambda) }$. Indeed, we then have $\theta\in [0,1)$ s.t. $$q(y)\leq q(y_{\theta})\leq \frac{\mathbb{E}[X]}{\mathbb{E}[Y]}\leq \sqrt{ 2(2-\lambda) }$$
   Firstly, $$\mathbb{E}[Y]=\sum_{v\in V}^{}d_{v}\mathbb{E}[y_{\theta}(v)^{2}]=\sum_{v\in V}^{}d_{v}\mathbb{P}(\theta<z(v)^{2})=\sum_{v\in V}^{}d_{v}z(v)^{2}=z^\top Dz$$
   Now, for any edge $uv$, we have: $$(y_{\theta}(u)+y_{\theta}(v))^{2}=\begin{cases}4& \text{if }\theta<  \min\{z(u)^{2},z(v)^{2}\}\text{ and }\text{sgn}(z(u)z(v))=1\\1&\text{if }\min\{z(u)^{2},z(v)^{2}\}\leq \theta< \max\{z(u)^{2},z(v)^{2}\}\\0&\text{ otherwise}\end{cases}$$Therefore, $$\begin{aligned}\mathbb{E}[(y_{\theta}(u)+y_{\theta}(v))^{2}]&\leq 4\cdot \min\{ z(u)^{2},z(v)^{2} \}+\max\{z(u)^{2},z(v)^{2}\}-\min\{ z(u)^{2},z(v)^{2} \}\\&\leq 3\cdot \min\{ z(u)^{2},z(v)^{2} \}+\max\{z(u)^{2},z(v)^{2}\}\\&\leq \underbrace{ 2\cdot \min\{ z(u)^{2},z(v)^{2} \} }_{ \leq z(u)^{2}+z(v)^{2} }+ \underbrace{ \min\{ z(u)^{2},z(v)^{2} \}+\max\{z(u)^{2},z(v)^{2}\} }_{ =z(u)^{2}+z(v)^{2} }\\&\leq 2(z(u)^{2}+z(v)^{2})\end{aligned}$$
	$$\mathbb{E}[X]=\sum_{(u,v)\in E}\mathbb{E}[(y_{\theta}(u)+y_{\theta}(v))^{2}]\leq 2\sum_{(u,v)\in E} z(u)^{2}+z(v)^{2}$$and $$\frac{\mathbb{E}[X]}{\mathbb{E}[Y]}\leq  \frac{2\sum_{(u,v)\in E}^{}z(u)^{2}+z(v)^{2}}{\sum_{v\in V}^{}d_{v}z(v)^{2}}$$
	
	Now, let $N$ be the normalized Laplacian. Then, $z^\top Nz=\lambda_{n}z^\top z=\lambda_{n}$. 
	
	We have that: $$\mathbb{E}[(y_{\theta}(u)+y_{\theta}(v))^{2}]=\mathbb{E}[y_{\theta}(u)^{2}]+2\mathbb{E}[y_{\theta}(u)y_{\theta}(v)]+\mathbb{E}[y_{\theta}(v)^{2}]$$Now, $$\mathbb{E}[y_{\theta}(u)^{2}]=\mathbb{P}(y_{\theta}(u)\neq 0)=1-\mathbb{P}(y_{\theta}(u)=0)=1-\mathbb{P}(z(u)^{2}\leq \theta)=\mathbb{P}(\theta< z(u)^{2})=z(u)^{2}$$Similarly $\mathbb{E}[y_{\theta}(v)^{2}]=z(v)^{2}$. Further, $y_{\theta}(u)y_{\theta}(v)=\text{sgn}(z(u))\text{sgn}(z(v))\mathbb{1}_{\min \{ z(u)^{2},z(v)^{2} \}> \theta}$$$\begin{aligned}\mathbb{E}[y_{\theta}(u)y_{\theta}(v)]&=\text{sgn}(z(u))\text{sgn}(z(v)) \mathbb{P}(\min \{ z(u)^{2},z(v)^{2} \}> \theta)\\&=\text{sgn}(z(u))\text{sgn}(z(v))\min \{ z(u)^{2},z(v)^{2} \} \\&\leq \text{sgn}(z(u))\text{sgn}(z(v))z(u)z(v)\\&\leq z(u)z(v)\end{aligned}$$Therefore, $$\mathbb{E}[(y_{\theta}(u)+y_{\theta}(v))^{2}]\leq z(u)^{2}+z(v)^{2}+2z(u)z(v)=2z(u)^{2}+2z(v)^{2}-(z(u)-z(v))^{2}$$Now, $$\sum_{(u,v)\in E}z(u)^{2}+z(v)^{2}=\sum_{v\in V}^{}d_{v}z(v)^{2}=z^\top Dz$$and $$\sum_{(u,v)\in E}^{}(z(u)-z(v))^{2}=z^\top Lz$$Therefore, $$\mathbb{E}[X]=\sum_{(u,v)\in E}^{}\mathbb{E}[(y_{\theta}(u)+y_{\theta}(v))^{2}]\leq 2z^\top Dz-z^\top Lz$$
	
	
	Using Cauchy-Schwarz, we get: $$\mathbb{E}[X]=\sum_{(u,v)\in E}^{}\mathbb{E}[(y_{\theta}(u)+y_{\theta}(v))^{2}]\leq \sqrt{ \sum_{(u,v)\in E}(z(u)^{2}+z(v)^{2})^{2} }\cdot \sqrt{ \sum_{(u,v)\in E}^{}1+\text{sgn}(z(u))\text{sgn}(z(v)) }$$

---
##### Part C.
1. Consider the lollipop graph $L_{n,n}$. Then, 
2. Let $P_{n}$ be the path graph on $n$ nodes. Then, 
3. Let $C_{n}$ be a cycle graph where $n$ is odd. Then, we will analyze $q(C_{n})$.
	1. If $y$ does not contain zero, $q(y)= \frac{\sum_{(u,v)\in E}^{}(y(u)-y(v))^{2}}{2n}$. We have that $y(u)-y(v)=4\cdot \mathbb{1}_{y(u)=y(v)}$. As $n$ is odd, if there is no zero, we have at least one such edge where $y$ is equal. Hence, in this case the minimum quality is given as $\frac{4}{2n}=\frac{2}{n}$. 
	2. If $y$ contains at least one zero, then we have that there are at least 2 edges where $(y(u)-y(v))^{2}=1$. Therefore, the smallest numerator we can have is $2$. However, in this case the denominator can be at most $2(n-1)$ (by having only one zero), we have that the minimum quality is given as $\frac{1}{n-1}$. 
	
	This shows that $q(C_{n})=\Theta\left(  \frac{1}{n} \right)$. Now to find $\lambda_{n}$, notice that $D=2I$ and we have that $N=I-\frac{1}{2}A$. As $A$ is circulant and we have that $\mu_{k}:=2\cos\left( \frac{2\pi k}{n} \right)$ for $k=0,\dots,n-1$ are the eigenvalues by Fourier. Hence, $\lambda_{k}=1- \cos \left( \frac{2\pi k}{n} \right)$ are the eigenvalues of $N$. This is maximized when $k=\left\lfloor n / 2\right\rfloor$.  If $n=2\ell+1$, then $\left\lfloor n /2\right\rfloor=\ell$ and we have that: $$2-\lambda_{n}=1+\cos\left( \frac{2\pi \ell}{2\ell+1} \right)=1+\cos\left(\pi- \frac{\pi}{n} \right)=1-\cos\left( \frac{\pi}{n} \right)=\Theta\left( \frac{1}{n^{2}} \right)$$
	
	
