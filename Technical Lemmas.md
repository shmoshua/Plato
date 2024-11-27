> [!lemma]
> Let $b\geq a+2>a\geq 1$. Then, $$(a!)^{\frac{1}{a}}(b!)^{\frac{1}{b}}<((a+1)!)^{\frac{1}{a+1}}((b-1)!)^{\frac{1}{b-1}}$$

---
> [!lemma]
> We have that:
> 1. $\frac{{n-k \choose k-i}}{n \choose k}\sim \frac{k(k-1)\dots (k-i+1)}{n^i}$

> [!proof]+
> We have that:
> $$\mu:=\frac{{n-k \choose k-i}}{n \choose k}=\frac{{n-k \choose k}}{n \choose k}\cdot  \frac{k(k-1)\dots (k-i+1)}{(n-2k+i)\dots(n-2k+1)}$$Then, $$\mu\leq \left( \frac{n-k}{n} \right)^k \frac{k(k-1)\dots (k-i+1)}{(n-2k+i)\dots(n-2k+1)}$$
> 
> 1. Notice that: $$\lim_{ n \to \infty } \frac{n^i}{k(k-1)\dots (k-i+1)}\mu\leq\lim_{ n \to \infty }  \left( \frac{n-k}{k} \right) ^k \frac{n^i}{(n-2k+i)\dots(n-2k+1)}=$$$$\frac{n^i}{n(n-1)\dots(n-i+1)}\cdot \frac{(n-k)(n-k-1)\dots(n-2k+i+1)}{(n-i)(n-i-1)\dots(n-k+1)}$$$$<\frac{n^{i}}{n(n-1)\dots(n-i+1)}\cdot \frac{(n-k+i)^{k-i}}{n^{k-i}}<\frac{n^{i}}{n(n-1)\dots(n-i+1)}\cdot \frac{(n-k+i)^{k-i}}{n^{k-i}}$$