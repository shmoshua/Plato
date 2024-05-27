#Definition #DifferentialGeometry 

> [!definition]
> A [[Smooth Curve|smooth curve]] $\gamma:I \to \mathbb{R}^n$ is a ***regular curve*** if for all $t\in I$: $$\frac{d\gamma}{dt}\neq 0$$i.e. the velocity vector $\gamma_{t}:= \frac{d\gamma}{dt}$ never vanishes.

---
##### Properties
> [!lemma] Proposition 1
> If $\gamma:I\to \mathbb{R}^n$ is a regular curve, 
> 1. it can be reparametrized into a new curve $\beta(s)$ where $$\beta(s)=\gamma(g(s))$$ and $g$ is a smooth change of parameters s.t. $s$ is the [[Arc Length|arc-length]] of $\beta$
> 2. the reparametrization is unique up to the choice of the base point $t_{0}$.

> [!proof]-
> Fix $t_{0}$. Then, 
> 1. We let $s=f(t)=\int_{t_{0}}^{t} \left|  \frac{d\gamma}{dt} \right| \, dt$. Further, let $g:=f^{-1}$. Then, for $t$, $$g(s)=f^{-1}(s)=t$$Now, we define $\beta=\gamma \circ g$. Then, $\beta(s)=\gamma(g(s))=\gamma(t)$. 
>    
>    Now, we show that $s$ is the arc-length of $\beta$. We have: 
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
