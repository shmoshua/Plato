#Definition #DiscreteOptimization 

> [!definition]
> Let $P:=\{ x\in \mathbb{R}^n: Ax\leq b \}$ be a nonempty [[polyhedron]] and $\mathcal{F}:=P\cap \mathbb{Z}^n$. Then
> 1. a ***split*** is a tuple $(\pi,\pi_{0})\in \mathbb{Z}^n \times \mathbb{Z}$.
> 2. a ***split cut*** is $P^{(\pi,\pi_{0})}:=\text{conv}(\pi_{1}\cup \pi_{2})$ where:
> 	$$\pi_{1}:= \{ x\in P:\pi^\top x\leq \pi_{0} \},\quad \pi_{2}:= \{ x\in P:\pi^\top x\geq \pi_{0}+1 \}$$
> 3. a ***split closure*** is $P^{\text{split}}:=\bigcap_{(\pi,\pi_{0})}^{}P^{(\pi,\pi_{0})}$.
- **Related definition**: An inequality $a^\top x\le \alpha$ is a ***split inequality*** if there exists a split $(\pi,\pi_{0})$ s.t. $a^\top x\leq \alpha$ is valid for $P^{(\pi,\pi_{0})}$.

---
##### Properties
> [!lemma] Proposition 1
> Let $(\pi,\pi_{0})$ be a split.
> 1. $\mathcal{F}\subseteq P^{(\pi,\pi_{0})}$.
> 2. a rounding cut of the form $c^\top x\leq \gamma,c\in \mathbb{Z}^n, c^\top = \mu^\top A$, $\mu\geq0$ and $\gamma=\left\lfloor \mu^\top b\right\rfloor$ is a split inequality.
> 3. $P^{(\pi,\pi_{0})}$ is a polyhedron.
> 4. for $x\in P$ with $\pi_{0}<\pi^\top x < \pi_{0}+1$. Then, $x\in P^{(\pi,\pi_{0})}$ if and only if there exists $y\in \pi_{2}$ s.t. $$b-Ay\leq \frac{1}{\pi^\top x-\pi_{0}}(b-Ax )$$



> [!proof]-
> We have that:
> 1.  Let $x\in \mathcal{F}$. Then $\pi^\top x\in \mathbb{Z}$ and $x\in\pi_{1}\cup \pi_{2}$. Hence, $x\in P^{(\pi,\pi_{0})}$.
> 2. Let $\pi:=c$ and $\pi_{0}:= \gamma$. Then, $$\pi_{1}:=\{  x\in P:c^\top x\leq \gamma \},\quad \pi_{2}:=\{ x\in P : c^\top x \geq \gamma+1\}$$where $\pi_{2}$ is empty as for any $x\in P$: $$c^\top x = \mu^\top Ax \leq \mu^\top b  < \pi_{0}+1$$
> 3. We have that: $$\begin{aligned}P^{(\pi,\pi_{0})}&=\{  x\in \mathbb{R}^n: x=\lambda x_{1}+(1-\lambda)x_{2},x_{1}\in\pi_{1},x_{2}\in\pi_{2},\lambda\in[0,1] \}\\&=\{  x\in \mathbb{R}^n: x=\lambda x_{1}+(1-\lambda)x_{2},A\lambda x_{1}\leq \lambda b,A(1-\lambda)x_{2}\leq (1-\lambda)b,\\&\quad\quad \quad \quad\quad\quad \quad \quad\pi^\top \lambda x_{1}\leq \lambda \pi_{0},\pi^\top(1-\lambda)x_{2}\geq (1-\lambda)(\pi_{0}+1),\lambda\in[0,1] \}\\&=\{  x\in \mathbb{R}^n: x=y_{1}+y_{2},Ay_{1}\leq \lambda b,Ay_{2}\leq (1-\lambda)b,\\&\quad\quad \quad \quad\quad\quad \quad \quad\pi^\top y_{1}\leq \lambda \pi_{0},\pi^\top y_{2}\geq (1-\lambda)(\pi_{0}+1),\lambda\in[0,1] \}\\&=\text{proj}_{x}(Q)\end{aligned}$$
> 	where: $$Q:=\left\{\begin{bmatrix} x\\y_{1}\\y_{2}\\\lambda \end{bmatrix}\in \mathbb{R}^{3n+1}:\begin{array}{l} \ x-y_{1}-y_{2}=0\\Ay_{1}-\lambda b\leq 0\\Ay_{2}-(1-\lambda )b\leq 0\\ \pi^\top y_{1} - \lambda \pi_{0} \leq 0\\ \pi^\top y_{2} -(1-\lambda)(\pi_{0}+1) \geq 0\\0\leq \lambda\leq 1\end{array}\right\}$$

---
> [!lemma] 
> Non-dominated split inequalities come from splits $(\pi,\pi_{0})$ s.t. $$u^\top A = \pi^\top\text{ for some }u\in \mathbb{Q}^m,\quad u^\top b\notin \mathbb{Z},\quad \pi_{0}=\left\lfloor u^\top b\right\rfloor $$

> [!proof]+
> We can assume $P\cap \{ x:\pi^\top x\leq \pi_{0} \}\neq \varnothing$. Then, we have that: $$ u_{{\min}}:=\begin{array}{rl}\max & u^\top b\\\text{s.t} &u^\top A = \pi^\top \\ &\mu\leq 0\end{array} =\begin{array}{rl}\min & \pi^\top x\\\text{s.t} &Ax \leq b\end{array}\leq \pi_{0}<\begin{array}{rl}\max & \pi^\top x\\\text{s.t} &Ax \leq b\end{array}=\begin{array}{rl}\min & u^\top b\\\text{s.t} &u^\top A = \pi^\top \\ &\mu\geq 0\end{array}=:u_{\max}$$Take now a convex combination of $u_{\min}$ and $u_{\max}$: $u:= \lambda u_{\min}+(1-\lambda)u_{\max}$ s.t. $\pi_{0}<u^\top b<1$.