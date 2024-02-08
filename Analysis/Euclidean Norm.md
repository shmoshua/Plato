#Definition #LST #Analysis 

> [!definition]
> 
> In $(F^n,F)$ for $F=\mathbb{R},\mathbb{C}$, the ***Euclidean norm/2-norm*** is defined as:
> $$\|x\|_{2}=\sqrt{ \sum_{i=1}^{n}|x_{i}|^2 }$$
> In function space $C([t_{0},t_{1}],\mathbb{R}^n)$, the ***2-norm*** is defined as: $$\|f\|_{2}=\sqrt{ \int_{t_{0}}^{t_{1}} \|f(t)\|^2_{2} \, dt } $$

---
##### Properties
> [!lemma] Fact EucNorm.1
> The Euclidean norm is a [[Norm|norm]]

>[!proof]-
>We show for $x,y\in F^n$:
>1. $$\|x+y\|_{2}^2=\sum_{i=1}^{n}|x_{i}+y_{i}|^2 \leq\sum_{i=1}^{n}|x_{i}|^2+\sum_{i=1}^{n}|y_{i}|^2+2\sum_{i=1}^{n}|x_{i}y_{i}|=\|x\|_{2}^2+\|y\|_{2}^2+2\sum_{i=1}^{n}|x_{i}y_{i}|$$Using Cauchy-Schwarz, we know that then: $$\|x+y\|^2_{2}\leq(\|x\|_{2}+\|y\|_{2})^2$$Therefore, $\|x+y\|_{2}\leq\|x\|_{2}+\|y\|_{2}$.
>2. For all $a\in F$:$$\|ax\|_{2}=\sqrt{ a^2 \sum_{i=1}^{n}|x_{i}|^2 }=|a|\sqrt{ \sum_{i=1}^{n}|x_{i}|^2 }=|a|\|x\|_{2}$$
>3. If $\|x\|_{2}=\sqrt{  \sum_{i=1}^{n}|x_{i}|^{2}}=0$, as $|x_{i}|^2\geq 0$ for all $i$, we have $x_{i}=0$ for all $i$, i.e. $x=0$.

---