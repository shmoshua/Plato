#Definition #DifferentialGeometry 

> [!definition]
> A [[Smooth Curve|smooth curve]] $\gamma:I \to \mathbb{R}^n$ is ***regular*** if 
> 1. $\dot{\gamma}(t)\neq 0$ for all $t\in I$.

---
##### Properties
> [!lemma] Proposition 1
> If $\gamma:I\to \mathbb{R}^n$ is a regular curve, 
> 1. for [[Smooth Curve|arc length]] $s:I\to \mathbb{R}$ with base $t_{0}\in I$, $\gamma$ can be reparametrized w.r.t. $s$, i.e. there exists another regular curve $\beta:s(I)\to \mathbb{R}^n$ s.t. $\beta \circ s=\gamma$ and $s$ remains the arc length of $\beta$ with base $s(t_{0})$.
> 2. the reparametrization $\beta$ is unique up to the choice of the base point $t_{0}$.

> [!proof]+
> Fix $t_{0}$. Then, 
> 1. We let $s(t)=\int_{t_{0}}^{t} \left|  \dot{\gamma}(\tau) \right| \, d\tau$. We first show that $s:I\to s(I)$ is bijective. If $t_{1}<t_{2}$, $$s(t_{2})=\int_{t_{0}}^{t_{2}}\left| \dot{\gamma}(\tau) \right|   \, d\tau=\int_{t_{0}}^{t_{1}}\left| \dot{\gamma}(\tau) \right|   \, d\tau+\int_{t_{1}}^{t_{2}}\underbrace{ \left| \dot{\gamma}(\tau) \right|  }_{ >0 }  \, d\tau>s(t_{1}) $$Therefore, we can define $g:s(I)\to I$ as its inverse. By defining $\beta:=\gamma \circ g$, we have a curve $\beta:s(I)\to \mathbb{R}^n$ s.t. $$\beta(s(t))=\gamma(g(s(t)))=\gamma(t)$$
>    
>    
>    Now, we show that $s$ is the arc-length of $\beta$. We have: 
>    $$\left| \dot{\beta} (s(t))\right|=\left| \beta(s(t))\dot{s}(t) \right| = $$
> 
>    $$|\dot{\beta}(s)|=|\dot{\gamma}(g(s))\dot{g}(s)|=|\dot{\gamma}(t) \frac{1}{\dot{f}(t)}|=\left| \dot{\gamma}(t) \frac{1}{\dot{\gamma}(t)} \right| =1$$and $\int_{0}^{s} \left| \dot{\beta}(s') \right| \, ds'=s$.
---

##### Examples of non-regular curves
- $t\mapsto (t^{2},t^{3})\in \mathbb{R}^2$ is not regular!
	```tikz
	
	\begin{document}
	\begin{tikzpicture}[line cap=round,scale=0.15]
	
	\definecolor{mycolor}{RGB}{126,29,251}
	
	\draw[-latex] (-10,0) -- (10,0){};
	\draw[-latex] (0,-10)     -- (0,10) {};
	%% \foreach[count=\j]\i in {-10,-9,...,10}
	  %% \draw (\i,0.05) -- (\i,-0.05) node [below] {$\i\ifnum\j<3\phantom{-}\fi$}; %%
	%% \foreach\i in {-10,-9,...,10} %%
	  %% \draw (0.05,\i) -- (-0.05,\i) node [left]  {$\i$}; %% 
	\draw[mycolor, thick] plot[variable=\t,domain=-2.1:2.1,smooth,thick] ({\t*\t},{\t*\t*\t});
	\end{tikzpicture}
	\end{document}
	```
	as $\gamma_{t}(0)=(0,0)$.
---
