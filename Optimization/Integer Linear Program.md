#Definition #Optimization 

> [!definition]
> An ***Integer Linear program (ILP)*** is given in standard form as follows: $$\begin{array}{rl l} \max & c^\top x\\ \text{s.t.}& Ax = b\\&x\in \mathbb{Z}^n_{+}\end{array}$$where $A\in \mathbb{Z}^{m,n},b\in \mathbb{Z}^m$ and $A$ has a full row rank.

---
##### Properties
> [!lemma] Theorem 1
> For an ILP, there exists an optimal solution $z^{*}$ s.t. $$\left| \text{supp}(z^{*}) \right| \leq 2m\log (4m\left\| A \right\| _{\infty})$$ 

> [!proof]-
> Let $z^{*}$ be the optimal solution s.t. $\left| \text{supp}(z^{*}) \right|$ is minimum. Wlog we may assume that $\text{supp}(z^{*})=\{ 1,\dots,k \}$ and $z^{*}_{i}=0$ for all $i>k$.
> 
> Consider the following set: $$W:=\left\{ \left. \sum_{i=1}^{k}A_{:,i}x_{i}\right|   x_{i}\in \{ 0,1 \}\right\}$$Let $\Delta:=\left\| A \right\|_{\infty}$. Then, $\left| W \right|\leq (2k\Delta+1)^m$. On the other hand we have at most $2^k$ combinations. Hence, whenever $2^k > (2k\Delta+1)^m$ there exists two subsets $S_{1},S_{2}\subseteq [k]$ s.t. $\sum_{i\in S_{1}}^{}A_{:,i}=\sum_{i\in S_{2}}^{}A_{:,i}$. Now, we define $d\in \{ -1,0,1 \}^n$ where: $$d_{i}=\begin{cases}1&i \in S_{1} \backslash S_{2}\\-1& i\in S_{2} \backslash S_{1}\\0&\text{otherwise}\end{cases}$$Then, $Ad=0$. Modulo multiplying by $-1$, $d_{i}=-1$ for at least one $i$. Moreover, $z^{*}+d\in \mathbb{Z}^n_{+}$. Then, by the optimum we have that $c^\top d=0$. 
> 
> Let now $\lambda:= \min\{ z^{*}_{i}|d_{i}=-1 \}$. Then, $z^{*}+\lambda d$ is optimum for the ILP. However, $\text{supp}(z^{*}+\lambda d)\subsetneq \text{supp}(z^{*})$. This is a contradiction and we have that $2^k\leq (2k\Delta+1)^m$. Hence, $$k\leq m\log (2k\Delta+1)$$
- **Remark**: For LP, we have that $\left| \text{supp}(z^{*}) \right|\leq m$.
---
> [!lemma] Theorem 2
> Let $A\in \mathbb{Z}^{m,n},b\in ^m$ and consider the ILP $\max_{x\in \mathbb{Z}^n_{+}}\{ c^\top x : Ax \leq b \}$ and its relaxed LP. 
> 1. Let $y^{*}$ be the optimum solution of LP relaxation. Then, if ILP is feasible, there exists an ILP optimal solution $x^{*}$, s.t. $$\left\| y^{*}-x^{*} \right\| _{\infty}\leq n\Delta$$where $\Delta:=\max\{  \left| \det B \right|:\text{a square submatrix }B\text{ of }A \}$
> 2. Let $z\in \mathbb{Z}^n$ be feasible for ILP. Then, there exists $x\in \mathbb{Z}^n$ also feasible s.t. 
> 	1. $c^\top x\geq c^\top z$ and 
> 	2. $\| z-x \|_{\infty}\leq n\Delta$

> [!proof]+
> We have:
> 1. Let $\widehat{x}$ be any optimal solution of ILP. Let $A_{1},A_{2}$ s.t. $A_{1}y^{*}< A_{1}\widehat{x}$ and $A_{2}y^{*}\geq A_{2}\widehat{x}$. Now, define the cone: $$C:=\{ x\in \mathbb{R}^n: A_{1}x\leq 0, A_{2}x\geq 0 \}$$Then, $y^{*}-\widehat{x}\in C$. In particular, $A_{1}y^{*}\leq b_{1}$. Then, by complementary slackness, $c^\top = v^\top A_{2}$ s.t. $v\geq 0$. Then, for any $u\in C$, $A_{2}u \geq 0$ and $$c^\top u=v^\top A_{2} u \geq 0$$Now using the internal representations $C=\text{cone}(u^1,\dots,u^t)$ s.t. $u^i\in \mathbb{Z}^n$ and $\left\| u^i \right\|_{\infty}\leq \Delta$ from (c.f. [[Cone]]), then by [[cone|Caratheodory]], wlog. $y^{*}-\widehat{x}=\sum_{i=1}^{k}\lambda_{i}u_{i}$ for $k\leq n$ and $\lambda_{i}\geq 0$ for all $i\in[k]$. Therefore, $$\left\| y^{*}-\widehat{x} \right\| _{\infty}\leq \sum_{i=1}^{k}\lambda_{i}\left\| u^i \right\| _{\infty}\leq \sum_{i=1}^{k}\lambda_{i}\Delta$$Suppose $\lambda_{j}\geq 1$. Then $\left\lfloor\lambda_{j}\right\rfloor u^j\in C$. We further have that: $$r:= \sum_{i \neq j}^{}\lambda_{i}u^i+(\lambda_{j}-\left\lfloor \lambda_{j}\right\rfloor ) u^j\in C$$Therefore, $c^\top u^j\geq 0$ hence $\widehat{x}+\left\lfloor\lambda_{j}\right\rfloor u^j$ is optimal for ILP. Hence, we can reduce $\lambda_{j}$ to below 1 and wlog we have: $$\left\| y^{*}-\widehat{x} \right\| _{\infty}\leq \sum_{i=1}^{k}\lambda_{i}\Delta\leq k\Delta\leq n\Delta$$
> 2. Let $x^{*}$ be the optimal solution for ILP. Then, similarly we set $A_{1}x^{*}< A_{1}z$ and $A_{2}x^{*}\geq A_{2}z$. Then, for the cone: $$C:= \{ x\in \mathbb{R}^n:A_{1}x\leq 0,A_{2}x\geq 0 \}=\text{cone}(u^1,\dots,u^t)$$with $\left\| u^i \right\|_{\infty}\leq \Delta$. Then, $x^{*}-z\in C$. Consider the mixed integer program: $$\begin{array}{rll}\min & \sum_{i=1}^{t}\lambda_{i}\\\text{s.t.}&c^\top y > c^\top z\\&y-z=\sum_{i=1}^{t}\lambda_{i}u^i \\&\lambda \geq 0, y \in \mathbb{Z}^n\end{array}$$Take the optimal solution $(y^{*},\lambda ^{*})$ of MIP. Then, $$\left\| y^{*}-z \right\| _{\infty}\leq\sum_{i=1}^{t}\lambda ^{*}_{i}\left\| u^i \right\| _{\infty}\leq n\left\| u^{i} \right\|_{\infty} $$

---
