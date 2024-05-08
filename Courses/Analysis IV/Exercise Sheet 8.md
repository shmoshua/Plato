#Series #Analysis 

We have that: $$\partial_{t}u=\sum_{k\in \mathbb{Z}}^{}\dot{u}_{k}(t)e^{-ikx},\quad \partial_{xx}u=-\sum_{k\in \mathbb{Z}}^{}k^{2}u_{k}(t)e^{-ikx}$$Therefore, we have:
$$\dot{u}_{0}(t)=1, \quad \dot{u}_{k}(t)=-k^{2}u_{k}(t),\quad \forall k\in \mathbb{Z} \backslash \{ 0 \}$$Then, $u_{0}(t,x)=t+C$ and $u_{k}(t)=A_{k}\exp(-k^{2}t)$ for $k\neq 0$ where $C,A_{k}$ are scalars. Therefore, $$u(x,t)=t+\sum_{k\neq 0}^{}A_{k}\exp(-k^{2}t)+C$$is the most general solution and one non-constant example would be $u(x,t)=t$. 