 #Definition #MeasureTheory 

> [!definition]
> A real-valued ***simple function*** is a function $f:\Omega\to \overline{\mathbb{R}}$ of the form: $$f(x)=\sum_{i=1}^{\infty}d_{i}\chi_{A_{i}}(x)$$where $d_{i}\in \overline{\mathbb{R}}$ and $A_{i}$ are mutually disjoint sets. 
- **Remark**: Alternatively, it can be written as: $$f(x)=\sum_{y=-\infty}^{\infty}y\chi_{f^{-1}(y)}(x)$$
---
##### Properties
> [!lemma] Proposition 1
> A simple function $f(x)=\sum_{i=1}^{\infty}d_{i}\chi_{A_{i}}(x)$ is [[Measurable Function|$\mu$-measurable]] if $A_{i}$ are $\mu$-measurable.

> [!proof]-
> $\chi_{A_{i}}$ is $\mu$-measurable if $A_{i}$ is measurable by [[Measurable Function|Proposition 2]] and the sum is $\mu$-measurable.
---
> [!lemma] Proposition 2
> A function $f:\Omega\to \mathbb{R}$ is a $\mu$-measurable simple function if and only if $f$ is $\mu$-measurable and $\text{Im }f$ is at most countable.

> [!proof]-
> We have: 
> - =>: If $f$ is $\mu$-measurable simple, then: $$\text{Im }f\subseteq \left\{  d_{i}:i\geq 1 \right\}$$Therefore, the image is at most countable.
> - <=: If the image is at most countable, let $(d_{i})_{i}$ be the enumeration of the image. Then, $$f(x)=\sum_{i=1}^{\infty}d_{i}\chi_{f^{-1}[\{ d_{i} \}]}(x)$$which is simple as the preimages are disjoint. 

---
##### Integral of Non-negative Simple Functions in Measure
Let $g:\Omega\to[0,+\infty]$ be a non-negative, simple, $\mu$-measurable function where $\mu$ is a [[Radon Measure|Radon measure]]. Then, 
$$\int_{\Omega}^{} g \, d\mu:=\begin{cases}\sum_{i=1}^{\infty}d_{i}\mu(A_{i})\leq+\infty&\text{if }g<+\infty \text{ }\mu \text{-a.e.}\\+\infty&\mu(g^{-1}[\{ +\infty \}])>0\end{cases} $$
We can generalize this as follows: Let $g:\Omega\to \overline{\mathbb{R}}$ is simple and $\mu$-measurable s.t. either $\int_{\Omega}^{}g^+  \, d\mu<+\infty$ or $\int_{\Omega}^{}g^-  \, d\mu<+\infty$. Then, $g$ is called a ***$\mu$-integrable simple function*** and we set:
$$\int_{\Omega}^{} g \, d\mu=\int_{\Omega}^{} g^+ \, d\mu-\int_{\Omega}^{} g^- \, d\mu=\begin{cases}\sum_{i=1}^{\infty}d_{i}\mu(A_{i})\leq+\infty&\text{if }|g|<+\infty \text{ }\mu \text{-a.e.}\\+\infty&\mu(g^{-1}[\{ +\infty \}])>0\\-\infty&\mu(g^{-1}[\{ -\infty \}])>0\end{cases} $$
---