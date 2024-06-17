#Definition #Topology 

> [!definition]
> A [[topological space]] $X$ is ***contractible*** if $\text{id}_{X}$ is [[Homotopy|homotopic]] to a constant map. 
---
##### Properties
> [!lemma] Proposition 1
> Let $X$ be a contractible space. 
> 1. if for $x_{0}\in X$ s.t. $\text{id}_{X}$ is homotopic to $x_{0}$, then $\pi_{1}(X,x_{0})=\{ \varepsilon_{x_{0}} \}$

^f327ea

> [!proof]-
> Let $h:X\times[0,1]\to X$ be the homotopy with $h(x,0)=x$ and $h(x,1)=x_{0}$. Let further $\gamma:[0,1]\to X$ be a path. Then, define: $$\tilde{h}:[0,1]\times[0,1]\to X,\quad (t,s)\mapsto h(\gamma(t),s)$$We verify that $\tilde{h}$ is continuous and satisfies: $\tilde{h}(t,0)=h(\gamma(t),0)=\gamma(t)$ and $\tilde{h}(t,1)=h(\gamma(t),1)=x_{0}$. Hence, it is a homotopy from $\gamma$ to $x_{0}$. However, it may not be strict, i.e. $\widehat{h}(0,s)=h(\gamma(0),s)=h(x_{0},s)$is not necessarily $x_{0}$. 
> 
> If defining $\eta(s)=h(x_{0},s)$ then $\eta\in \pi_{1}(X,x_{0})$. We now construct a homotopy from $\gamma$ to $\varepsilon_{x_{0}}$, $\widehat{h}:[0,1]\times[0,1]\to X$,  $$\widehat{h}(t,s):=\begin{cases}\eta(3ts)&0\leq t\leq \frac{1}{3}\\\tilde{h}(3t-1,s)& \frac{1}{3}\leq t\leq \frac{2}{3}\\ \eta(-3ts+3s)& \frac{2}{3}\leq t\leq 1\end{cases}$$This is continuous as $\eta(s)=\tilde{h}(0,s)$ and: $$\widehat{h}(t,0)=\begin{cases}x_{0}&0\leq t\leq \frac{1}{3}\\\gamma(3t-1)& \frac{1}{3}\leq t\leq \frac{2}{3}\\ x_{0}& \frac{2}{3}\leq t\leq 1\end{cases},\quad \widehat{h}(t,1)=\begin{cases}\eta(3t)&0\leq t\leq \frac{1}{3}\\x_{0}& \frac{1}{3}\leq t\leq \frac{2}{3}\\ \eta(-3t+3)& \frac{2}{3}\leq t\leq 1\end{cases}$$with $\widehat{h}(0,s)=x_{0}$ and $\widehat{h}(1,s)=x_{0}$. Therefore, $\widehat{h}$ is a homotopy from $\varepsilon_{x_{0}}\gamma \varepsilon_{x_{0}}=\gamma$ to $\eta \varepsilon_{x_{0}}\overline{\eta}=\varepsilon_{x_{0}}$. 

^87c949

---
##### Examples 
> [!h] Example 1 (Rn)
> $\mathbb{R}^n$ is contractible for $n\geq 0$. For $y\in \mathbb{R}^n$, we have the homotopy, $$\begin{array}{cccc} {h:}&{\mathbb{R}^n\times [0,1]}&\to&{\mathbb{R}^n}\\&{(x,t)} &\mapsto & {(1-t)x+ty} \end{array}{}$$So is any non-empty star-shaped subset of $\mathbb{R}^n$. 
---
> [!h] Example 3
> $L^2([0,1]) \backslash \{ 0 \}$ is contractible. 
---
##### Non-Examples
> [!h] Non-Example 1
> $S^1$ is not contractible.

> [!proof]-
> Assume that $S^1$ is contractible let $h$ be the homotopy with $h(x,0)=x$ and $h(x,1)=x_{0}\in S^1$ for all $x\in S^1$. By composing it with a rotation, we may assume that $x_{0}=-1$. 
> 
> Then, the map: $$\begin{array}{cccc} {\varphi:}&{S^1 \backslash\{ -1 \}}&\to&{(-\pi,\pi)}\\&{z} &\mapsto & {\text{arg}(z)}\\&{e^{it}} &\gets & {t} \end{array}{}$$is a homeomorphism.
> 
> We claim that there exists a continuous function $\tilde{f_{0}}:S^1\to \mathbb{R}$ s.t. $\text{id}_{S^1}=\exp(i\tilde{f_{0}})$. Let $$\begin{array}{cccc} {f_{t}:}&{S^1}&\to&{S^1}\\&{x} &\mapsto & {h(x,t)} \end{array}{}$$As $S^1\times [0,1]$ is compact, $h$ is uniformly continuous and we can find $k\geq 1$ s.t. for any $s,t\in [0,1]$, if  $\left| s-t \right|\leq \frac{1}{ k}$ then: $$\left| h(x,t)-h(x,s) \right| =\left| f_{t}(x)-f_{s}(x) \right| <2, \quad \forall x\in S^1$$Therefore, $f_{t} / f_{s}:S^1\to S^1 \backslash \{ -1 \}$. Now we show the claim via induction on $j$ for $0\leq j\leq k$. Firstly, $f_{1}$ is a constant function and hence there exists $\tilde{f}_{1}$ s.t. $f_{1}=\exp(i\tilde{f}_{1})$.
> 
> Now, for the induction assume $f_{j /k}$ has a lifting $\tilde{f}_{j/k}$ s.t. $f_{j / k}=\exp(i \tilde{f}_{j / k})$. Indeed, $$f_{(j-1) / k}= f_{j / k}\cdot  \frac{f_{(j-1) /k}}{f_{j /k}}=\exp(i\tilde{f}_{j /k})\cdot \left( \varphi ^{-1} \circ \varphi\circ  \frac{f_{(j-1) /k}}{f_{j /k}} \right)=\exp(i\tilde{f}_{j /k})\cdot \exp\left(i\left( \varphi\circ  \frac{f_{(j-1) /k}}{f_{j /k}}  \right)\right)$$Therefore, $\tilde{f}_{(j-1) / k}=\tilde{f}_{j/k}+\varphi \circ\frac{f_{(j-1) /k}}{f_{j /k}}$ is continuous and from the induction $f_{0}$ also has such lifting. 
> 
> Then, define: $$g(z):=\frac{ \tilde{f_{0}}(z)-\tilde{f_{0}}(-z)}{\left| \tilde{f_{0}}(z)-\tilde{f_{0}}(-z) \right| }$$where $\tilde{f_{0}}(z)-\tilde{f_{0}}(-z)\neq 0$ as $\tilde{f_{0}}$ is injective. Then, $g:S^1\to \{ \pm 1 \}$ is surjective and continuous, but $S^1$ is connected, which is a contradiction.
---
