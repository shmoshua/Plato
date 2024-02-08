#Definition #LST 

> [!definition]
> For the [[Linear Time Varying System|state transition map]] $s(t,t_{0},x_{0},u)$, we know that: $$s(t,t_{0},x_{0},u)=s(t,t_{0},x_{0},0)+s(t,t_{0},0,u)$$
> 	where $s(t,t_{0},\cdot,0):\mathbb{R}^n\to \mathbb{R}^n$ is a linear function from [[Linear Time Varying System|Theorem 1]]. Therefore, the ***state transition matrix*** $\Phi:\mathbb{R}\times \mathbb{R} \to \mathbb{R}^{n,n}$ is a map s.t.$$s(t,t_{0},x_{0},0)=\Phi(t,t_{0})x_{0}$$

- **Remark**: For the [[Linear Time Varying System|output response map]] $\rho(t,t_{0},x_{0},u),$ it holds that: $$\rho(t,t_{0},x_{0},0)=C(t)\Phi(t,t_{0})x_{0}$$as $\rho(t,t_{0},x_{0},0)=C(t)s(t,t_{0},x_{0},0)+D(t)u(t)$.
---
##### Properties

> [!lemma] Proposition 1
> For $t,t_{0}\in \mathbb{R}$, it holds for $\Phi(t,t_{0})$ that:
> 1. $\Phi(\cdot,t_{0}):\mathbb{R} \to \mathbb{R}^{n,n}$ is the unique solution of the linear matrix [[Ordinary Differential Equation|ODE]]: $$\frac{ \partial  }{ \partial t } \Phi(t,t_{0})=A(t)\Phi(t,t_{0})$$where $\Phi(t_{0},t_{0})=I$. Hence, it is continuous for all $t\in \mathbb{R}$ and differentiable everywhere except at the discontinuity points of $A(t)$.
> 2. For all $t,t_{0},t_{1}\in \mathbb{R}$, $\Phi(t,t_{0})=\Phi(t,t_{1})\Phi(t_{1},t_{0})$
> 3. For all $t_{0},t_{1}\in \mathbb{R}$, $\Phi(t_{0},t_{1})$ is invertible with inverse $\Phi(t_{1},t_{0})$.

>[!proof]-
>Let's prove them!
>1. For $i\in[n]$, consider $x^i(\cdot)=s(\cdot ,t_{0},x^i(t_{0}),0)$ where $x^i(t_{0})=e_{i}$. Then, $$\dot{x}^i(t)=A(t)x^i(t) \text{ with }x^i(t_{0})=e_{i}$$and therefore, $x^i(t)=\Phi(t,t_{0})e_{i}$. From which it follows that: $$\Phi(t,t_{0})=[x^1(t)|\dots|x^n(t)]$$Therefore, $$\begin{align}\frac{ \partial  }{ \partial t } \Phi(t,t_{0})&=\left[ \left.  \frac{d}{dt} x^1(t)\right|\dots\left|\frac{d}{dt} x^n(t)\right. \right]\\&=[A(t)x^1(t)|\dots|A(t)x^n(t)]\\&=A(t)\Phi(t,t_{0})\end{align} $$
>	Moreover, $\Phi(t_{0},t_{0})=[e_{1}|\dots |e_{n}]=I$. 
>2. Let $t_{0},t_{1}\in \mathbb{R}$ be arbitrary and consider $L(t):=\Phi(t,t_{0})$ and $R(t)=\Phi(t,t_{1})\Phi(t_{1},t_{0})$. Firstly, we have when $t=t_{1}$, $$L(t_{1})=\Phi(t_{1},t_{0})=I\Phi(t_{1},t_{0})=R(t_{1})$$Moreover, $$\frac{d}{dt} L(t)=\frac{ \partial  }{ \partial t } \Phi(t,t_{0})=A(t)\Phi(t,t_{0})=A(t)L(t)$$and $$\frac{d}{dt} R(t)=\frac{ \partial  }{ \partial t } \Phi(t,t_{1})\Phi(t_{1},t_{0})=A(t)\Phi(t,t_{1})\Phi(t_{1},t_{0})=A(t)R(t)$$Therefore, $L(t)=R(t)$ by uniqueness of solution.
>3. First, we show that $\Phi(t_{0},t_{1})$ is invertible for all $t_{0},t_{1}\in \mathbb{R}$. Assume that it is not, i.e. there exists $t_{0},t_{1}\in \mathbb{R}$ s.t. $\Phi(t_{0},t_{1})$ is not invertible. This means that $\Phi(t_{0},t_{1})$ has linearly dependent columns and there exists $x_{0}\in \mathbb{R}^n$ with $x_{0}\neq 0$ s.t. $\Phi(t_{0},t_{1})x_{0}=0$ 
>   
>    Let $x(\tau)=\Phi(\tau,t_{1})x_{0}$. Then, $x(t_{0})=0$ and $$\frac{d}{d\tau} x(\tau)=\frac{d}{d\tau} \Phi(\tau,t_{1})x_{0}=A(\tau)\Phi(\tau,t_{1})x_{0}=A(\tau)x(\tau)$$Therefore, $x$ is the unique solution to: $$\dot{x}(\tau)=A(\tau)x(\tau)$$with $x(t_{0})=0$. However, notice that $x(\tau)=0$ for all $\tau\in \mathbb{R}$ is also a solution to the ODE, therefore, $$0=x(t_{1})=\Phi(t_{1},t_{1})x_{0}=Ix_{0}=x_{0}$$which is a contradiction. Therefore, $\Phi(t_{0},t_{1})$ is invertible.
>    
>    For the inverse, we have that:$$\Phi(t_{0},t_{1})\Phi(t_{1},t_{0})=\Phi(t_{0},t_{0})=I$$. This proves the inverse relationship.
---
> [!lemma] Theorem 2
> For all $t,t_{0}\in \mathbb{R}$, $x_{0}\in \mathbb{R}^n$, $u(\cdot)\in PC(\mathbb{R},\mathbb{R}^m)$, $$\begin{align}s(t,t_{0},x_{0},u)&=\Phi(t,t_{0})x_{0}+\int_{t_{0}}^{t} \Phi(t,\tau)B(\tau) u(\tau)\, d\tau\\ \rho(t,t_{0},x_{0},u)&=C(t)\Phi(t,t_{0})x_{0} +C(t)\int_{t_{0}}^{t} \Phi(t,\tau)B(\tau)u(\tau) \, d\tau +D(t)u(t) \end{align}$$
> In other words, the state transition matrix $\Phi(t,t_{0})$ completely characterizes the solution of linear time varying systems.

> [!proof]-
> Let $L(t):=s(t,t_{0},x_{0},u)$ and $R(t):=\Phi(t,t_{0})x_{0}+\int_{t_{0}}^{t}\Phi(t,\tau)B(\tau)u(\tau)  \, d\tau$. We want to show that for all $t\in \mathbb{R}$, $L(t)=R(t)$. By definition, we have: $$L(t_{0})=s(t_{0},t_{0},x_{0},u)=x_{0}=Ix_{0}+0=R(t_{0})$$Then, $$\frac{d}{dt} L(t)=\frac{d}{dt} s(t,t_{0},x_{0},u)=A(t)s(t,t_{0},x_{0},u)+B(t)u(t)=A(t)L(t)+B(t)u(t)$$Similarly, $$\begin{align}\frac{d}{dt} R(t)&=\frac{d}{dt} \left[ \Phi(t,t_{0})x_{0}+\int_{t_{0}}^{t} \Phi(t,\tau)B(\tau)u(\tau) \, d\tau \right] \\&= \frac{d}{dt} \Phi(t,t_{0})x_{0}+\frac{d}{dt} \int_{t_{0}}^{t} \Phi(t,\tau)B(\tau)u(\tau) \, d\tau\\&=A(t)\Phi(t,t_{0})x_{0}+\int_{t_{0}}^{t} \frac{ \partial  }{ \partial t } \Phi(t,\tau)B(\tau)u(\tau) \, d\tau +  \Phi(t,t)B(t)u(t)\\&=A(t)\Phi(t,t_{0})x_{0}+\int_{t_{0}}^{t} A(t)\Phi(t,\tau)B(\tau)u(\tau) \, d\tau +B(t)u(t)\\&=A(t)R(t)+B(t)u(t)\end{align}$$
> Therefore, by uniqueness of solutions of ODE, $L(t)=R(t)$.
---