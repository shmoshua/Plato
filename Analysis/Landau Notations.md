#Definition #Analysis #Algorithms 

> [!definition]
> Let $D\subseteq \mathbb{R}$. For functions $f,g:D\to \mathbb{R}$, let $\ell:=\lim_{ x \to a }\frac{f(x)}{g(x)}$. Then, as $x\to a$
> 1. $f= \text{O}(g)$ if $\ell<+\infty$
> 2. $f\asymp g$ if $0<\ell<+\infty$. 
> 3. $f= \text{o}(g)$ if $\ell=0$.
> 4. $f\sim g$ if $\ell=1$.
---
##### Properties
> [!lemma] Lemma 1
> We have that for any $f,g$ and $\lambda \neq0$, 
> 1. $f\sim g$ if and only if $f=(1+\text{o}(1))g$
> 2. $\text{o}(\lambda f)=\text{o}(f)$
> 3. $\lambda\text{o}(f)=\text{o}(f)$
> 4. $f$ is [[Continuous Function|continuous]] at $x_{0}$ if and only if $f(x)=f(x_{0})+\text{o}(1)$.

> [!proof]-
> We have that:
> 1. For $h:= f-g$, we have that: $$f\sim g \iff \lim_{ x \to a } \frac{f(x)}{g(x)}=1 \iff \lim_{ x \to a } \left( \frac{f(x)}{g(x)}-1 \right)=0 \iff \lim_{ x \to a } \frac{h(x)}{g(x)}=0 \iff \frac{h}{g}=\text{o}(1)$$Therefore, $f = g+h = g+\text{o}(1)g$.
> 2. We have that: $$g= \text{o}(\lambda f) \iff \lim_{ x \to a }  \frac{g(x)}{\lambda f(x)}=0 \iff\lim_{ x \to a }  \frac{g(x)}{f(x)}=0 \iff g=\text{o}(f)$$
> 3. We have that: $$\frac{g}{\lambda}= \text{o}(f) \iff \lim_{ x \to a }  \frac{g(x)}{\lambda f(x)}=0 \iff\lim_{ x \to a }  \frac{g(x)}{f(x)}=0 \iff g=\text{o}(f)$$
> 4. We have that: $$f(x_{0})=\lim_{ x \to x_{0} } f(x) \iff \lim_{ x \to x_{0} } f(x)-f(x_{0})=0 \iff f(x)-f(x_{0})=\text{o}(1)$$
---
> [!lemma] Lemma 2 (Little o algebra)
> We have that:
> 1. $x^n=\text{o}(x^m)$ for $x\to \infty$ if and only if $n<m$
> 2. $\text{o}(x^n)\pm \text{o}(x^n)=\text{o}(x^n)$
> 3. $\text{o}(x^n)\pm \text{o}(x^m)=\text{o}(x^{\max\{ n,m \}})$
> 4. $x^m\text{o}(x^n)=\text{o}(x^{m+n})$
> 5. $\text{o}(x^m)\text{o}(x^n)=\text{o}(x^{m+n})$
> 6. $\text{o}(x^{n})^k=\text{o}(x^{nk})$

> [!proof]-
> We have that: 
> 1. We have: $$x^n=\text{o}(x^m) \iff \lim_{ x \to \infty } x^{n-m}=0 \iff n-m<0$$
> 2. Let $f,g=\text{o}(x^n)$. Then, $\lim_{ x\to a }  \frac{f(x)\pm g(x)}{x^n}=0$ and $f+g=\text{o}(x^n)$. Conversely, for any $f=\text{o}(x^n)$, we have that $f=f\pm0$ where $0=\text{o}(x^n)$.
> 3. Let $f=\text{o}(x^n)$ and $g=\text{o}(x^m)$ where $n<m$. Then, $\lim_{ x\to a }  \frac{f(x)\pm g(x)}{x^m}=0$ and $f+g=\text{o}(x^m)$. Conversely, for any $f=\text{o}(x^m)$, we have that $f=f\pm0$ where $0=\text{o}(x^n)$.
> 4. Let $f=\text{o}(x^n)$. Then, $\lim_{ x\to a } \frac{x^mf(x)}{x^{m+n}}=\lim_{ x\to a } \frac{f(x)}{x^{n}}=0$. Conversely, for any $f\in \text{o}(x^{m+n})$, we have that: $\lim_{ x \to a }\frac{f(x)}{x^{m+n}}=0$. 
> 5. Let $f=\text{o}(x^m)$ and $g=\text{o}(x^n)$. Then, $\lim_{ x \to a }\frac{f(x)g(x)}{x^{m+n}}=0$. Conversely, for $f=\text{o}(x^{m+n})$, let $g=\text{o}(x^m)$. 
> 6. Let $f=\text{o}(x^n)$. Then, $\lim_{ x \to a }\frac{f(x)^k}{x^{nk}}=0$. 
---
> [!lemma] Lemma 3 
> We have that:
> 1. $f=\text{O}(f)$
> 2. if $f=\text{O}(g)$ then $\text{O}(f)+\text{O}(g)=\text{O}(g)$.
> 3. if $f=\text{O}(g)$ then $\text{o}(f)+\text{o}(g) = \text{o}(g)$
> 4. $\text{O}(f)\text{O}(g)=\text{O}(fg)$
> 5. $\text{o}(f)\text{O}(g)=\text{o}(fg)$
> 6. if $f=\text{o}(1)$, then $\frac{1}{1+\text{o}(f)}=1+\text{o}(f)$ and $\frac{1}{1+\text{O}(f)}=1+\text{O}(f)$

> [!proof]-
> We have that:
> 1. $\lim_{ x \to a }1 = 1$. 
> 2. $\lim_{ x \to a }\frac{h(x)+r(x)}{g(x)}=\lim_{ x \to a }\frac{h(x)}{f(x)}\frac{f(x)}{g(x)}+\frac{r(x)}{g(x)}<+\infty$.
> 3. $\lim_{ x \to a }\frac{h(x)+r(x)}{g(x)}=\lim_{ x \to a }\frac{h(x)}{f(x)}\frac{f(x)}{g(x)}+\frac{r(x)}{g(x)}=0$.
> 4. $\lim_{ x \to a }\frac{h(x)r(x)}{f(x)g(x)}<+\infty$
> 5. $\lim_{ x \to a }\frac{h(x)r(x)}{f(x)g(x)}=0$.
> 6. For $g=\text{o}(f)$, we have: $$\lim_{ x \to a } \frac{\frac{1}{1+g(x)}-1}{f(x)}=\lim_{ x \to a } \frac{\frac{-g(x)}{1+g(x)}}{f(x)}=-\lim_{ x \to a } \frac{g(x)}{f(x)} \frac{1}{1+\frac{g(x)}{f(x)}f(x)}=0$$

##### Examples
> [!h] Example 1 (Taylor Expansion)
>  