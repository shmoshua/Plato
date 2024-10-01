#Definition #PAI 

> [!definition]
> Let $p(x_{1:n})$ be a [[Distribution|joint distribution]]. A ***Bayesian network*** for $p$ is a [[directed acyclic graph]] $G$ on $[n]$ s.t. 
> 1. $v\to w\iff x_{v}\in S_{w}$ where $p(x_{1:n})=\prod_{i=1}^{n}p(x_{i}|S_{i})$ for $S_{i}\subseteq \{ x_{k}:k\in [i-1] \}$.

^78dc2b

- **Remark**: One can also add dotted nodes to represent deterministic values. (cf Example 1). ^62a6d8
- **Related definition**: In ***plate notation***, we use plates to represent parts of the graph that appear more than once. ^c0cc53
---
##### Properties
---
##### Examples
> [!h] Example 1 (Bayesian Linear Regression)
> Let us have the [[Linear Regression|BLR]] problem where: 
> 1. $p(w)=\mathcal{N}(0, \sigma^2_{p}I)$
> 2. $p(y_{1:n}|x_{1:n},w)=\prod_{i=1}^{n}p(y_{i}|x_{i},w)$ where $y_{i}=w^\top x_{i}+\varepsilon_{i}$ where $\varepsilon_{i} \sim \mathcal{N}(0,\sigma^{2}_{n})$
>    
> Then, the Bayesian network is shown as:
> ```tikz
>\usepackage{tikz}
>\usetikzlibrary{arrows}
>\usetikzlibrary{fit}
>
>\begin{document}
>
>\begin{tikzpicture}
>
>\tikzset{vertex/.style = {shape=circle,draw,minimum size=1.5em}}
>\tikzset{dot/.style = {minimum size=1.5em}}
>\tikzset{edge/.style = {->,> = latex'}}
>% vertices
>\node[vertex] (a) at  (4,2) {$w$};
>\node[vertex] (b) at  (0,0) {$y_1$};
>\node[vertex] (b1) at (1.5,0) {$y_2$};
>\node[vertex] (b2) at (3,0) {$y_3$};
>\node[vertex] (c) at  (8,0) {$y_n$};
>
>\node[dot] (d) at (2,2) {$\sigma_p^2$};
>\node[dot] (d1) at (0,1.5) {$\sigma_n^2$};
>\node[dot] (x1) at (0,-1.5) {$x_1$};
>\node[dot] (x2) at (1.5,-1.5) {$x_2$};
>\node[dot] (x3) at (3,-1.5) {$x_3$};
>\node[dot] (x) at (8,-1.5) {$x_n$};
>
>\node[vertex] (aa) at  (13,2) {$w$};
>\node[vertex] (ba) at  (13,0) {$y_i$};
>
>\node[dot] (da) at (11,2) {$\sigma_p^2$};
>\node[dot] (d1a) at (11,0) {$\sigma_n^2$};
>\node[dot] (x1a) at (13,-1.5) {$x_i$};
>\node[dot] (ta) at (14.05,-1.6) {$\footnotesize{i\in[n]}$};
>
>
>%edges
>\draw[edge] (a) to (b);
>\draw[edge] (a) to (b1);
>\draw[edge] (a) to (b2);
>\draw[edge] (a) to (c);
>\draw[edge] (d) to (a);
>\draw[edge] (d1) to (b);
>\draw[edge] (d1) to (b1);
>\draw[edge] (d1) to (b2);
>\draw[edge] (d1) to (c);
>\draw[edge] (x1) to (b);
>\draw[edge] (x2) to (b1);
>\draw[edge] (x3) to (b2);
>\draw[edge] (x) to (c);
>\draw[edge] (aa) to (ba);
>\draw[edge] (da) to (aa);
>\draw[edge] (d1a) to (ba);
>\draw[edge] (x1a) to (ba);
> \node[draw,dotted,fit=(ba)(x1a)] {};
>
>
>\path (b2) to node {\dots} (c);
>\path (x3) to node {\dots} (x);
>
>\end{tikzpicture}
>\end{document} 
>```
> 
> Where on the right we have the plate notation.

^acd87b

---
