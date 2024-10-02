#Series #Algorithms 

#### 1. Rounding for Bin Packing

Let $x_{1},\dots,x_{n}$ be elements in a bin s.t. $\sum_{i=1}^{n}x_{i}=1$. Modulo reindexing wlog assume that the elements are sorted in decreasing order. Then, let $M:=\sum_{i=1}^{n-1}x_{i}$ and set $\varepsilon:=\frac{1-M}{M}$. Then, we have that $(1+\varepsilon)x_{1},\dots,(1+\varepsilon)x_{n}$ can be packed in 2 bins. Therefore, $\alpha=2$. 

---

#### 2. Target Shooting

![[PRAS#^858f88]]
![[PRAS#^bf590a|p]]

For 3, if we run it $k$ times, then: $$\begin{align}\mathbb{P}(x_{\text{med}}\in [(1-\varepsilon)\text{OPT},(1+\varepsilon)\text{OPT}])&=1-\mathbb{P}(x_{\text{med}}< (1-\varepsilon)\text{OPT})-\mathbb{P}(x_{\text{med}}>(1+\varepsilon)\text{OPT})\end{align}$$where $$\begin{align}\mathbb{P}(x_{\text{med}}>(1+\varepsilon)  \text{OPT})&\leq \mathbb{P}(\text{Bin}(k,1 / 3 )\geq k / 2)\leq e^{-(\delta^{2})k/9}=e^{-k / 36}\end{align}$$Similarly, $\mathbb{P}(x_{med}<(1-\varepsilon)  \text{OPT})\leq e^{-k/36}$. Therefore, we need that: $$2e^{-k / 36}\leq\delta$$which then gives us that $k=O(\log \frac{1}{\delta})$.

---
#### 3. Counting Satisfying Assignments
