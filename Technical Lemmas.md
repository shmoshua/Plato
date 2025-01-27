> [!lemma]
> Let $b\geq a+2>a\geq 1$. Then, $$(a!)^{\frac{1}{a}}(b!)^{\frac{1}{b}}<((a+1)!)^{\frac{1}{a+1}}((b-1)!)^{\frac{1}{b-1}}$$

> [!proof]-
> Let $f:a\mapsto \frac{(a!)^{1/a}}{((a+1)!)^{1/(a+1)}}$. We will show that $f(a)<f(b-1)$ by showing $f$ is an increasing function. Let $a\geq 2$. Then, we will show that $f(a-1)<f(a)$. By taking both sides to power of $a(a+1)(a-1)$, it suffices to show that: $$ \frac{((a-1)! )^{a(a+1)}}{(a!)^{(a-1)(a+1)}}=f(a-1)^{a(a+1)(a-1)}<f(a)^{a(a+1)(a-1)}=\frac{(a!)^{(a+1)(a-1)}}{((a+1)!)^{a(a-1)}}$$
> and this is equivalent to $((a-1)!)^{a(a+1)}((a+1)!)^{a(a-1)}<(a!)^{2(a+1)(a-1)}$. By dividing both sides by $(a!)^{2a^{2}}$, it suffices to show that: $$\frac{(a+1)^{a(a-1)}}{a^{a(a+1)}}=\frac{((a-1)!)^{a(a+1)}}{(a!)^{a(a+1)}}\cdot \frac{((a+1)!)^{a(a-1)}}{(a!)^{a(a-1)}}< \frac{1}{(a!)^{2}}$$By multiplying both sides by $a^{2a}$, $\left( \frac{a+1}{a} \right)^{a(a-1)}<\left( \frac{a^a}{a!} \right)^2$. 
---

> [!lemma]
> For $t_{1},\dots,t_{r}\geq0$, $$\left( \frac{t_{1}+\dots+t_{r}}{r} \right)^{t_{1}+\dots+t_{r}}\leq t_{1}^{t_{1}}\dots t_{r}^{t_{r}} $$

> [!proof]-
> This is equivalent to: $$\frac{t_{1}+\dots+t_{r}}{r}\log\left( \frac{t_{1}+\dots+t_{r}}{r} \right)\leq \frac{t_{1}\log t_{1}+\dots+t_{r}\log t_{r}}{r}$$which holds as $f(x)=x\log x$ is a convex function. Therefore,  we have that: $$\frac{t_{1}+\dots+t_{r}}{r}\log\left( \frac{t_{1}+\dots+t_{r}}{r} \right)\leq \frac{t_{1}\log t_{1}}{r}+{\frac{r-1}{r}}\left( \frac{t_{2}+\dots+t_{r}}{r-1} \right) \log \left( \frac{t_{2}+\dots+t_{r}}{r-1} \right)$$This proves the statement.
---
> [!lemma]
> We have that if $k=n^{\text{o}(1)}$. 
> 1. $\frac{{n-k \choose k-i}}{n \choose k}\sim \frac{k(k-1)\dots (k-i+1)}{n^i}$

> [!proof]-
> We have that:
> $$\mu:=\frac{{n-k \choose k-i}}{n \choose k}=\frac{{n-k \choose k}}{n \choose k}\cdot  \frac{k(k-1)\dots (k-i+1)}{(n-2k+i)\dots(n-2k+1)}$$Then, $$\left(\frac{ n-2k+1}{n-k+1} \right)^k \leq\mu\leq \left( \frac{n-k}{n} \right)^k \frac{k(k-1)\dots (k-i+1)}{(n-2k+i)\dots(n-2k+1)}$$
> 
> 1. Notice that: $$ \frac{n^i}{k(k-1)\dots (k-i+1)}\mu\leq  \left( \frac{n-k}{k} \right) ^k \frac{n^i}{(n-2k+i)\dots(n-2k+1)}=$$$$\frac{n^i}{n(n-1)\dots(n-i+1)}\cdot \frac{(n-k)(n-k-1)\dots(n-2k+i+1)}{(n-i)(n-i-1)\dots(n-k+1)}$$$$<\frac{n^{i}}{n(n-1)\dots(n-i+1)}\cdot \frac{(n-k+i)^{k-i}}{n^{k-i}}<\frac{n^{i}}{n(n-1)\dots(n-i+1)}\cdot \frac{(n-k+i)^{k-i}}{n^{k-i}}$$

---
> [!lemma] Lemma 4
> For $0<m<k\leq p+1$ and $w_{1},\dots,w_{k}\in \mathbb{R}^q$ then: $$\left| \frac{1}{k}\sum_{i=1}^{k}w_{i}-\frac{1}{m}\sum_{j=1}^{m}w_{j} \right|\leq \frac{p}{p+1}\max_{i,j}\left| w_{i}-w_{j} \right|  $$

> [!proof]-
> We have: $$\begin{align}\left| \frac{1}{k}\sum_{i=1}^{k}w_{i}-\frac{1}{m}\sum_{j=1}^{m}w_{j} \right|&=\left| \frac{k-m}{km}\sum_{j=1}^{m}w_{j}-\frac{1}{k}\sum_{i=m+1}^{k}w_{i}\right|=\frac{k-m}{k}\left| \frac{1}{m}\sum_{j=1}^{m}w_{j}-\frac{1}{k-m}\sum_{i=m+1}^{k}w_{i} \right| \\&=\frac{k-m}{k}\left| \text{Bary}(w_{1},\dots,w_{m})-\text{Bary}(w_{m+1},\dots,w_{k}) \right|\\& \leq \frac{k-1}{k}\max_{i,j}\left| w_{i}-w_{j} \right|  \\
\\&\leq  \frac{p}{p+1}\max_{i,j}\left| w_{i}-w_{j} \right| \end{align}$$

---
> [!lemma] Theorem 5 (Log-Sum Inequality)
> Let $a_{i}\geq 0$ and $b_{i}\geq 0$ for all $i$. Then, $$\sum_{i}^{}a_{i}\log \frac{a_{i}}{b_{i}}\geq \left( \sum_{i}^{}a_{i} \right)\log\frac{\left( \sum_{i}^{}a_{i} \right)}{\left( \sum_{i}^{}b_{i} \right)}$$

^676db7

> [!proof]-
> Let $a:=\sum_{i}^{}a_{i}$ and $b:= \sum_{i}^{}b_{i}$. Then, $a_{i} / a$ and $b_{i} / b$ can be treated as probability distribution on $n$ variables. Hence, $$\begin{align}0\leq D\left( \frac{a_{i}}{a}\|\frac{b_{i}}{b} \right)=\sum_{i}^{}\frac{a_{i}}{a}\log \frac{a_{i} / a}{b_{i} / b}=\sum_{i}^{} \frac{a_{i}}{a}\log \frac{a_{i}}{b_{i}}-\log \frac{a}{b}\end{align}$$Therefore, $$a\log \frac{a}{b}\leq \sum_{i}^{}a_{i}\log \frac{a_{i}}{b_{i}}$$

^af9688

---
> [!lemma] Theorem 6 (AM-GM)
> Let $a_{1},\dots,a_{n}\geq 0$. We have that: $$\left( \prod_{i=1}^{n}a_{i} \right)^ \frac{1}{ n}\leq  \frac{1}{n}\sum_{i=1}^{n}a_{i}$$

^e84229

> [!proof]-
> Notice that we have by Jensen,  $$\frac{1}{n}\log \prod_{i=1}^{n}a_{i}=\sum_{i=1}^{n} \frac{1}{n}\log a_{i}=\mathbb{E}[\log a_{i}]\leq \log \mathbb{E}[a_{i}]=\log \frac{1}{n}\sum_{i=1}^{n}a_{i}$$This proves the statement.

^d6a2dd

---
