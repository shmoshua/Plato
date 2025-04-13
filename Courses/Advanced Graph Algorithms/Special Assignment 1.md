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
1. A dual vector map for $\|\cdot\|_{M}$ is given by: $$(\cdot )^{\sharp}:\mathbb{R}^n\to \mathbb{R}^n,\quad x\mapsto \frac{Mx}{\sqrt{ x^\top Mx }}$$Then, the properties hold for $x=0$ and for all non-zero $x$, $x^\top x^{\sharp}=\frac{x^\top Mx}{\sqrt{ x^\top Mx }}=\sqrt{ x^\top Mx }=\|x\|_{M}$. Further, $$(\left\| x^{\sharp} \right\|_{M})_{*}=\left\| x^{\sharp} \right\| _{M^{-1}}=\frac{x^\top Mx}{x^\top Mx}=1 $$
   Let $(\cdot)^{\flat}$ be another dual map. Then, $$x^\top(x^{\sharp}-x^{\flat})=0$$
