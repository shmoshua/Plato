> [!lemma]
> Let $b\geq a+2>a\geq 1$. Then, $$(a!)^{\frac{1}{a}}(b!)^{\frac{1}{b}}<((a+1)!)^{\frac{1}{a+1}}((b-1)!)^{\frac{1}{b-1}}$$

> [!proof]-
> Let $f:a\mapsto \frac{(a!)^{1/a}}{((a+1)!)^{1/(a+1)}}$. We will show that $f(a)<f(b-1)$ by showing $f$ is an increasing function. Let $a\geq 2$. Then, we will show that $f(a-1)<f(a)$. By taking both sides to power of $a(a+1)(a-1)$, it suffices to show that: $$ \frac{((a-1)! )^{a(a+1)}}{(a!)^{(a-1)(a+1)}}=f(a-1)^{a(a+1)(a-1)}<f(a)^{a(a+1)(a-1)}=\frac{(a!)^{(a+1)(a-1)}}{((a+1)!)^{a(a-1)}}$$
> and this is equivalent to $((a-1)!)^{a(a+1)}((a+1)!)^{a(a-1)}<(a!)^{2(a+1)(a-1)}$. By dividing both sides by $(a!)^{2a^{2}}$, it suffices to show that: $$\frac{(a+1)^{a(a-1)}}{a^{a(a+1)}}=\frac{((a-1)!)^{a(a+1)}}{(a!)^{a(a+1)}}\cdot \frac{((a+1)!)^{a(a-1)}}{(a!)^{a(a-1)}}< \frac{1}{(a!)^{2}}$$By multiplying both sides by $a^{2a}$, $\left( \frac{a+1}{a} \right)^{a(a-1)}<\left( \frac{a^a}{a!} \right)^2$. 
---
> [!lemma]
> We have that if $k=n^{\text{o}(1)}$. 
> 1. $\frac{{n-k \choose k-i}}{n \choose k}\sim \frac{k(k-1)\dots (k-i+1)}{n^i}$

> [!proof]-
> We have that:
> $$\mu:=\frac{{n-k \choose k-i}}{n \choose k}=\frac{{n-k \choose k}}{n \choose k}\cdot  \frac{k(k-1)\dots (k-i+1)}{(n-2k+i)\dots(n-2k+1)}$$Then, $$\left(\frac{ n-2k+1}{n-k+1} \right)^k \leq\mu\leq \left( \frac{n-k}{n} \right)^k \frac{k(k-1)\dots (k-i+1)}{(n-2k+i)\dots(n-2k+1)}$$
> 
> 1. Notice that: $$ \frac{n^i}{k(k-1)\dots (k-i+1)}\mu\leq  \left( \frac{n-k}{k} \right) ^k \frac{n^i}{(n-2k+i)\dots(n-2k+1)}=$$$$\frac{n^i}{n(n-1)\dots(n-i+1)}\cdot \frac{(n-k)(n-k-1)\dots(n-2k+i+1)}{(n-i)(n-i-1)\dots(n-k+1)}$$$$<\frac{n^{i}}{n(n-1)\dots(n-i+1)}\cdot \frac{(n-k+i)^{k-i}}{n^{k-i}}<\frac{n^{i}}{n(n-1)\dots(n-i+1)}\cdot \frac{(n-k+i)^{k-i}}{n^{k-i}}$$