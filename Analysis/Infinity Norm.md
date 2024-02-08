#Definition #LST #Analysis 

> [!definition]
> In $(F^n,F)$ for $F=\mathbb{R},\mathbb{C}$, the ***infinity norm*** is defined as:
> $$\|x\|_{\infty}=\max_{i\in[n]}|x_{i}|$$
> In function space $C(D,\mathbb{R}^n)$, the ***infinity norm*** is defined as: $$\|f\|_{\infty}=\sup_{t\in D}\|f(t)\|_{2}$$

---
##### Properties
> [!lemma] Fact InfNorm.1
> The infinity norm is a [[Norm|norm]]

>[!proof]-
>We show for $x,y\in F^n$:
>1. $$\|x+y\|_{\infty}=\max_{i\in[n]}|x_{i}+y_{i}|\leq \max_{i\in[n]}|x_{i}|+|y_{i}|\leq \max_{i\in[n]}|x_{i}|+\max_{i\in[n]}|y_{i}|=\|x\|_{\infty}+\|y\|_{\infty}$$
>2. For all $a\in F$:$$\|ax\|_{\infty}=\max_{i\in[n]}|a| |x_{i}|=|a|\max_{i\in[n]}|x_{i}|=|a|\|x\|_{\infty}$$
>3. If $\|x\|_{\infty}=\max_{i\in[n]}|x_{i}|=0$, as $|x_{i}|\geq 0$ for all $i$, we have $x_{i}=0$ for all $i$, i.e. $x=0$.

---