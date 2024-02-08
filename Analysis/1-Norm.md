#Definition #LST #Analysis 
> [!definition]
> In $(F^n,F)$ for $F=\mathbb{R},\mathbb{C}$, the ***1-norm*** is defined as:
> $$\|x\|_{1}=\sum_{i=1}^{n}|x_{i}|$$
> In function space $C([t_{0},t_{1}],\mathbb{R}^n)$, the **1-norm** is defined as:$$\|f\|_{1}=\int_{t_{0}}^{t_{1}}\|f(t)\|_{2}dt $$

---
##### Properties
> [!lemma] Fact 1Norm.1
> 1-norm in $(F^n,F)$ is a [[Norm|norm]]

>[!proof]-
>We show for $x,y\in F^n$:
>1. $$\|x\|_{1}+\|y\|_{1}=\sum_{i=1}^{n}|x_{i}|+\sum_{i=1}^{n}|y_{i}|\geq \sum_{i=1}^{n}|x_{i}+y_{i}|=\|x+y\|_{1}$$
>2. For all $a\in F$:$$\|ax\|_{1}=\sum_{i=1}^{n}|ax_{i}|=|a|\sum_{i=1}^{n}|x_{i}|=|a|\|x\|_{1}$$
>3. If $\|x\|_{1}=\sum_{i=1}^{n}|x_{i}|=0$, as $|x_{i}|\geq 0$ for all $i$, we have $x_{i}=0$ for all $i$, i.e. $x=0$.

---