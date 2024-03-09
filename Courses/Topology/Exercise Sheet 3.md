#Series #Topology 

> [!def] Problem 1
> Let $X=\mathcal{F}(\mathbb{R},\mathbb{C})$ with the topology $\mathcal{T}_{p}$.
> 1. Let $A\subseteq X$ be any subset. Show that $0\in \bar{A}$ if and only if, for any $x\in \mathbb{R}$ and any $\varepsilon>0$, there exists $f\in A$ such that $\left| f(x) \right|<\varepsilon$.
> 2. For $t\in \mathbb{R}$, let $g_{t}\in X$ be the function defined by $g_{t}(x)=x-t$. Let $A=\{ g_{t}|t\in \mathbb{R} \}$. Show that $0\notin A$ and that $0\in\overline{A}$.
> 3. Show that there exists no sequence $(f_{n})_{n}$ with $f_{n}\in A$ for all $n$ such that $f_{n}\to 0$ as $n\to +\infty$ (for the topology $\mathcal{T}_{p}$).

We have: 
1. let $0\in \overline{A}$. Then, then for any neighborhood $U$ of $0$, $U\cap A\neq \varnothing$. Therefore, for any $x\in \mathbb{R}$ and $\varepsilon>0$, there exists $f\in \{ g\in \mathcal{F}(\mathbb{R},\mathbb{C}):\left| g(x) \right|<\varepsilon \}\cap A$. 
   
   Conversely, suppose for all $x\in \mathbb{R}$ and $\varepsilon>0$, there exists $f\in A$ s.t. $\left| f(x) \right|<\varepsilon$. Then, for any (open) neighborhood $U$ of $0$ and $x\in U$, there exists $\varepsilon>0$ s.t. $$\{ g\in \mathcal{F}(\mathbb{R},\mathbb{C}):\left| g(x) \right| <\varepsilon \}\subseteq U$$As $f\in U\cap A$, $0\in\overline{A}$.
2. There cannot be $t\in \mathbb{R}$ s.t. $g_{t}(x)=x-t=0$ for all $x\in \mathbb{R}$. Therefore, $0\notin A$. However, for any $x\in \mathbb{R}$ and $\varepsilon>0$, $g_{x}\in A$ and $\left| g_{x}(x) \right|=0<\varepsilon$. Therefore, by 1, $0\in \overline{A}$.
3. Let $(g_{t_{n}})_{n}\subseteq A$ s.t. $g_{t_{n}}\to{0}$ in $\mathcal{T}_{p}$. This means that for all $x\in \mathbb{R}$, $g_{t_{n}}(x)=x-t_{n}\to 0$, i.e. $\lim_{ n \to \infty }t_{n}=x$ for all $x\in \mathbb{R}$, which is a contradiction.
---
