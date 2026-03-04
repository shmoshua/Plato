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
