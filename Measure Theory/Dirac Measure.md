#Definition #MeasureTheory 

> [!definition]
> For a set $X$, a ***Dirac measure*** $\delta_{x}$ for $x\in X$ is given as: $$\delta_{x}(A)=\chi_{A}(x)$$for a measurable set $A$.
---
##### Properties
> [!lemma] Lemma 1
> Let $X=[0,1]$. Then, $\delta_{0}(f)=f(0)$ for $f\in C(X,\mathbb{R})$. Let: $$\mu_{n}=n \mathcal{L}^1|_{[0,1 / n]}$$Then, $\mu_{n}\to\delta_{0}$ in [[Weak Topology|weak*-topology]] on $M(X,\mathbb{R})$.

> [!proof]-
> We have that: $$\begin{align}\left| \int_{X}^{} f \, d\mu_{n}-\int_{X}^{} f \, d\delta_{0}   \right|&=\left| n\int_{0}^{1/n} f(x) \, d\mathcal{L}^1(x)-f(0)  \right|\\&=\left| n\int_{0}^{1/n} (f(x)-f(0)) \, d\mathcal{L}^1(x)  \right| \\&\leq\sup_{x\in[0,1/n]}\left| f(x)-f(0) \right| \to 0\end{align} $$
---
