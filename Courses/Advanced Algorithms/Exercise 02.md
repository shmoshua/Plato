#Series #Algorithms 

### 1. Rounding for Bin Packing

### 2. Target Shooting

![[PRAS#^858f88]]
![[PRAS#^bf590a|p]]

For 3, if we run it $k$ times, then: $$\begin{align}\mathbb{P}(x_{\text{med}}\in [(1-\varepsilon)\text{OPT},(1+\varepsilon)\text{OPT}])&=1-\mathbb{P}(x_{\text{med}}< (1-\varepsilon)\text{OPT})-\mathbb{P}(x_{\text{med}}>(1+\varepsilon)\text{OPT})\end{align}$$where $$\begin{align}\mathbb{P}(x_{\text{med}}>(1+\varepsilon)  \text{OPT})&\leq \mathbb{P}(\text{Bin}(k,1 / 3 )\geq k / 2)\leq e^{-(\delta^{2})k/9}=e^{-k / 36}\end{align}$$Similarly, $\mathbb{P}(x_{med}<(1-\varepsilon)  \text{OPT})\leq e^{-k/36}$. Therefore, we need that: $$2e^{-k / 36}\leq\delta$$which then gives us that $k=O(\log \frac{1}{\delta})$.

---