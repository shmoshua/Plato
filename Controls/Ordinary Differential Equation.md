#Definition #LST 

> [!definition]
> An ***ordinary differential equation*** can be defined as follows: 
> Given:
>  1. dynamics $f:\mathbb{R}^n\times \mathbb{R}^m\times \mathbb{R} \to \mathbb{R}^n$
>  2. initial condition: $(t_{0},x_{0})\in \mathbb{R}\times \mathbb{R}^n$
>  3. input trajectory: $u:\mathbb{R} \to \mathbb{R}^m$
>     
>  Find:
>  1. state trajectory: $x:\mathbb{R} \to \mathbb{R}^n$
>  
>  Constraints:
>  1. $x(t_{0})=x_{0}$
>  2. $\frac{d}{dt}x(t)=f(x(t),u(t),t)$ for all $t\in \mathbb{R}$
>
> These are represented in the following form: $$\dot{x}(t)=f(x(t),u(t),t)$$
---
##### Solution of an ODE
> [!definition]
> For a [[Piecewise Continuous Function|piecewise continuous]] function $p:\mathbb{R}^n\times \mathbb{R} \to \mathbb{R}^n, (x,t) \mapsto f(x,u(t),t)$ in the second argument, a continuous function $\phi :\mathbb{R}\to \mathbb{R}^n$ is called a ***solution*** of $$\dot{x}(t)=p(x(t),t)$$ if:
> 1. $\phi(t_{0})=x_{0}$ and
> 2. for all $t\in \mathbb{R} \backslash D$, $\phi$ is differentiable at $t$ with $\frac{d}{dt}\phi(t)=p(\phi(t),t)$.
---
##### Properties
> [!lemma] Theorem 1
> If $u:\mathbb{R} \to \mathbb{R}^m$ is [[Piecewise Continuous Function|piecewise continuous]] and $f:\mathbb{R}^n\times \mathbb{R}^m\times \mathbb{R} \to \mathbb{R}^n$ is [[Continuous Functions in Normed Spaces|continuous]], then $p(x,t):=f(x,u(t),t)$ is piecewise continuous in the second argument.

> [!proof]-
> Let $D$ be the discontinuity points of $u$. Then, in $\mathbb{R} \backslash D$, $u$ is continuous and $f$ is continuous therefore, $p(x,\cdot)$ must be continuous. Further, for any $\tau\in D$, $$\lim_{ t \to \tau^+ } p(x,t)=f(x,\lim_{ t \to \tau^+ } u(t),\lim_{ t \to \tau^+ } t)=f(x,\lim_{ t \to \tau^+ } u(t),\tau)=f(x,u(\tau),\tau)=p(x,\tau)$$which exist and is finite as $\lim_{ t \to \tau^+ }u(t)$ exists and is finite, and $f$ is continuous.
---
> [!lemma] Theorem 2
> For a piecewise continuous function $p:\mathbb{R}^n\times \mathbb{R}\to \mathbb{R}^n$ wrt to the second argument and [[Lipschitz Function|globally Lipschitz]] w.r.t the first argument with $k:\mathbb{R}\to \mathbb{R}_{+}$ as the Lipschitz constant. Then, for all $(t_{0},x_{0})\in \mathbb{R}\times \mathbb{R}^n$ there exists a unique continuous function $\phi:\mathbb{R} \to \mathbb{R}^n$ s.t. 
> 1. $\phi(t_{0})=x_{0}$ and
> 2. for all $t\in \mathbb{R} \backslash D$, $\dot{\phi}(t)=p(\phi(t),t)$

> [!proof]-
> We will first show that there is a solution. We construct $\{ x_{m} \}_{m\geq 1}\subseteq \mathcal{ F}(\mathbb{R},\mathbb{R}^n)$ by [[Picard iteration]].
> 1. $x_{0}(t)=x_{0}$ for all $t\in \mathbb{R}$
> 2. $x_{m+1}(t)=x_{0}+\int_{t_{0}}^{t} p(x_{m}(\tau),\tau) \, d\tau$
>    
> Then $x_{m}$ is a continuous function by construction. Now, for any $t_{1},t_{2}\in \mathbb{R}$ s.t. $t_{1} \leq t_{0}\leq t_{2}$, let: $$\bar{k}:=\sup_{t\in[t_{1},t_{2}]}k(t)$$
> and $T:=t_{2}-t_{1}$. Then, $\bar{k}$ and $T$ are both non-negative and finite. Then, for all $t\in [t_{1},t_{2}]$: $$\begin{align}\left\| x_{m+1}(t)-x_{m}(t) \right\|_{\infty}&=\left\| x_{0}+ \int_{t_{0}}^{t} p(x_{m}(\tau),\tau) \, d\tau-x_{0}-\int_{t_{0}}^{t} p(x_{m-1}(\tau),\tau) \, d\tau\right\|_{\infty}\\&=\left\| \int_{t_{0}}^{t} [p(x_{m}(\tau),\tau) -p(x_{m-1}(\tau),\tau)]\, d\tau\right\|_{\infty}  \\&\leq \left|  \int_{t_{0}}^{t} \left\| p(x_{m}(\tau),\tau) -p(x_{m-1}(\tau),\tau) \right\|_{\infty}  \, d\tau \right| \\&\leq \left|  \int_{t_{0}}^{t} k(\tau)\left\| x_{m}(\tau)-x_{m-1}(\tau)\right\|_{\infty}  \, d\tau \right| \\&\leq \bar{k} \left|  \int_{t_{0}}^{t} \left\| x_{m}(\tau)-x_{m-1}(\tau)\right\|_{\infty}  \, d\tau \right| \end{align}$$
> Then, for $m=0$, $$\left\| x_{1}(t)-x_{0}(t) \right\|_{\infty}=\left\| \int_{t_{0}}^{t} p(x_{0},\tau) \, dx  \right\|_{\infty} \leq \left\| \int_{t_{1}}^{t_{2}} p(x_{0},\tau) \, dx  \right\|_{\infty}=:M$$
> For $m=1$,
> $$\left\| x_{2}(t)-x_{1}(t) \right\| _{\infty}\leq \bar{k} \left| \int_{t_{0}}^{t} \left\| x_{1}(\tau)-x_{0}(\tau) \right\| _{\infty} \, d\tau  \right|\leq\bar{k}M(t-t_{0}) $$
> For $m=2$, 
> $$\left\| x_{3}(t)-x_{2}(t) \right\|_{\infty}\leq \bar{k} \left| \int_{t_{0}}^{t} \left\| x_{2}(\tau)-x_{1}(\tau) \right\| _{\infty} \, d\tau  \right|\leq \bar{k}^2 M \left| \int_{t_{0}}^{t} (\tau-t_{0})\, d\tau  \right|=\bar{k}^{2}M \frac{(t-t_{0})^2}{2}$$
> Continuing, we get: $$\left\| x_{m+1}(t)-x_{m}(t) \right\| _{\infty}\leq M \frac{(\bar{k}T)^m}{ m!}$$
> Then, let's show that $(x_{m})_{m\geq 1}$ is a Cauchy sequence in the Banach space $(C([t_{1},t_{2}],\mathbb{R}^n),\|\cdot\|_{\infty})$. We have, for $m \geq N \geq 0$: $$\begin{align}\left\| x_{m}-x_{N} \right\| _{\infty}&=\left\| \sum_{i=0}^{m-N-1} (x_{i+N+1}-x_{i+N})\right\|_{\infty}\\&\leq \sum_{i=0}^{m-N-1}  \left\| x_{i+N+1}-x_{i+N} \right\| _{\infty}\\&\leq M\sum_{i=0}^{m-N-1} \frac{(\bar{k}T)^{i+N}}{(i+N)!}\\&\leq M\sum_{i=0}^{m-N-1} \frac{(\bar{k}T)^{i+N}}{N!i!}\\&=\frac{ M(\bar{k}T)^N}{N!}\sum_{i=0}^{m-N-1} \frac{(\bar{k}T)^{i}}{i!}\\&\leq\frac{ M(\bar{k}T)^N}{N!}\exp(\bar{k}T)\end{align}$$
> which approaches 0 as $N\to \infty$. Therefore, it is a Cauchy sequence. Furthermore, it is bounded as: 
> $$\left\| x_{m} \right\| _{\infty}\leq \left\| x_{0} \right\| _{\infty}+\left\|x_{m}-x_{0}  \right\|_{\infty}\leq \left\| x_{0} \right\| _{\infty}+M \exp(\bar{k}T)<\infty  $$
> This means the sequence converges to some continuous function $\phi:[t_{1},t_{2}] \to \mathbb{R}^n$ with $\left\| \phi \right\|_{\infty}<\infty$. Therefore, $\{ x_{m}(t) \}_{m\geq 1}$ converges to $\phi(t)$ for all $t\in[t_{1},t_{2}]$. Now we show that it is truly a solution to the ODE. 
> 1. For all $m$, $x_{m}(t_{0})=x_{0}$. Therefore, $\phi(t_{0})=x_{0}$.
> 2. We have that $$\begin{align}\left\| \int_{t_{0}}^{t} [p(x_{m}(\tau),\tau) -p(\phi(\tau),\tau)]\, d\tau\right\|_{\infty}  &\leq \bar{k} \left|  \int_{t_{0}}^{t} \sup_{t\in [t_{1},t_{2}]}\left\| x_{m}(\tau)-\phi(\tau)\right\|_{\infty}  \, d\tau \right| \\&\leq \bar{k} \left\| x_{m}-\phi \right\| _{\infty} T  \end{align}$$ which converges to 0. Therefore, $$\int_{t_{0}}^{t} p(x_{m}(\tau),\tau) \, d\tau \xrightarrow{m\to \infty}\int_{t_{0}}^{t}p(\phi(\tau),\tau)\, d\tau$$and we have:$$\phi(t)=\lim_{ m \to \infty }x_{m} (t)=x_{0}+\lim_{ m \to \infty } \int_{t_{0}}^{t} p(x_{m}(\tau),\tau) \, d\tau =x_{0}+ \int_{t_{0}}^{t} p(\phi(\tau),\tau) \, d\tau $$By differentiating, we get that for all $t\in[t_{1},t_{2}]\backslash D$, $$\frac{d}{dt}\phi(t)=p(\phi(t),t)$$
> 
> Therefore, we can take appropriate $t_{1},t_{2}$ to find a solution.
> 
> Now let's show that this solution $\phi$ is unique. Assume we have $\psi:\mathbb{R}\to \mathbb{R}^n \neq \phi$ s.t. 
> 1. $\psi(t_{0})=x_{0}$
> 2. for all $t\in \mathbb{R} \backslash D$, $\frac{d}{dt}\psi(t)=p(\psi(t),t)$
> 
> Then, $$\begin{align} \frac{d}{d\tau}(\phi(\tau)-\psi(\tau))&=p(\phi(\tau),\tau)-p(\psi(\tau),\tau)\\\phi(t)-\psi(t) &=\int_{t_{0}}^{t} p(\phi(\tau),\tau)-p(\psi(\tau),\tau) \, d\tau\\\left\| \phi(t)-\psi(t)  \right\| &\leq\left| \int_{t_{0}}^{t} k(\tau)\left\| \phi(\tau)-\psi(\tau) \right\| \, d\tau \right| \\\left\| \phi(t)-\psi(t)  \right\| &\leq\left| \int_{t_{0}}^{t} k(\tau)\left\| \phi(\tau)-\psi(\tau) \right\| \, d\tau \right| +c_{1} \end{align}$$for any $c_{1}\geq 0$. 
> It follows that from [[Gronwall Lemma]], for all $c_{1}\geq 0$,$$\left\| \phi(t)-\psi(t)  \right\|\leq c_{1}\exp\left| \int_{t_{0}}^{t} k(\tau) \, d\tau \right| $$Therefore, $\left\| \phi(t)-\psi(t) \right\|=0$ and $\phi(t)=\psi(t)$ for all $t\in \mathbb{R}$, which is a contradiction.
---
##### Examples
---
> [!Example]- Example (No solutions)
> For the one dimensional system: $$\dot{x}(t)=-\text{sgn}(x(t))$$with the initial condition $(t_{0},x_{0})=(0,c)$ with $c>0$, we have $\phi(t)=c-t$ for $t\leq c$ but no solution for $t>c$.
---
> [!Example]- Example (Finite escape time)
> For the one dimensional system: $$\dot{x}(t)=x(t)^{2}$$with the initial condition $(t_{0},x_{0})=(0,c)$ with $c>0$, we have a solution: $$\phi(t)= \frac{c}{1-tc}$$
 