#Definition #Topology 

> [!definition]
> The ***Cantor space*** is a [[topological space]] defined as: $C=\{ 0,1 \}^\infty$ with the [[product topology]], i.e. $U\subseteq C$ is open if and only if for every $x\in U$, there exists a finite index set $I\subseteq \mathbb{N}$ s.t. $$\{ y\in C: y_{n}=x_{n},\forall n\in I \}\subseteq U$$
---
##### Properties
> [!lemma] Proposition 1
>  $x^{(n)}\to x$ in $C$ if and only if for all $m\in \mathbb{N}$, $x_{m}^{(n)}=y_{m}$ for all $n\geq N_{m}$.

> [!proof]-
> If $x^{(n)}\to x$, then for $m\in \mathbb{N}$, there exists $N_{m}$ s.t. $$x^{(n)}\in\{ y\in C: y_{m}=x_{m}\},\quad \forall n\geq N_{m}$$Conversely, if $x_{m}^{(n)}=y_{m}$ for all $n\geq N_{m}$, for any neighborhood $U$ of $x$, there exists $I\subseteq \mathbb{N}$ finite s.t. $$\{ y\in C: y_{m}=x_{m},\forall m\in I \}\subseteq U$$Then, by choosing $N:=\max_{m\in I}N_{m}$, $x^{(n)}\in U$ for all $n\geq N$.
---
> [!lemma] Proposition 2
> Consider the map: $$b:C\to[0,1],\quad x\mapsto \sum_{n=1}^{\infty}\frac{x_{n}}{2^n}$$
> 1. $b$ is surjective.
> 1. $b$ is continuous.
> 2. $b$ is not a homeomorphism.
---
> [!lemma] Proposition 3
> Consider the map: $$t:C\to[0,1],\quad x\mapsto \sum_{n=1}^{\infty}\frac{2x_{n}}{3^n}$$Then, 
> 1. $t$ is well-defined, continuous and injective.
> 2. $t$ is not surjective and $t(C)$ is the [[Cantor set]].
> 3. $t(C)$ is closed in $[0,1]$.
> 4. $t:C\to t(C)$ is a homeomorphism.

> [!proof]-
> We have:
> 1. Firstly, for any $x\in C$, $0\leq t(x)\leq \sum_{n=1}^{\infty} \frac{2}{3^n}=1$ as $0\leq x_{n}\leq 1$.  Therefore, $t(x)\in [0,1]$ as a convergent sum. 
> 	  1. **Showing that $t$ is continuous**: Let $U\subseteq [0,1]$ open. Then, for $x\in t^{-1}(U)$, there exists $r>0$ s.t. $B_{<r}(t(x))\subseteq U$. Let $n_{0}\in \mathbb{N}$ s.t. $\sum_{n=1}^{n_{0}} \frac{2}{3^n}> 1- r$. Then, let $I:=[n_{0}]$. If $y\in C$ s.t. $y_{n}=x_{n}$ for all $n\in I$, i.e. $1\leq n\leq n_{0}$, we have: $$\left| t(x)-t(y) \right| =\left| \sum_{n=1}^{\infty}\frac{2x_{n}}{3^n}-\sum_{n=1}^{\infty}\frac{2y_{n}}{3^n} \right| \leq \sum_{n=n_{0}+1}^{\infty}\frac{2\left| x_{n}-y_{n} \right| }{3^n} \leq\sum_{n=n_{0}+1}^{\infty}\frac{2 }{3^n} =1-\sum_{n=1}^{n_{0}} \frac{2}{3^n}< r  $$Therefore, $t(y)\in U$ and $y\in t^{-1}(U)$. This shows that $t^{-1}(U)$ is open and $t$ is continuous.
> 	  2. **Showing that $t$ is injective**: Let $x,y\in C$ s.t. $t(x)=t(y)$. Then, $$\sum_{n=1}^{\infty}\frac{2(x_{n}-y_{n})}{3^n}=0$$Let $n_{0}\geq 1$ be the first index at which $x_{n_{0}}-y_{n_{0}}\neq 0$, if it doesn't exist, $x_{n}=y_{n}$ for all $n$ and we are done. Due to symmetry, we may assume that $x_{n_{0}}-y_{n_{0}}=1$. However, notice that: $$\left|\sum_{n=n_{0}+1}^{\infty}\frac{2(x_{n}-y_{n})}{3^n}\right|\leq \frac{1}{3^{n_{0}}}<1$$Therefore, it is a contradiction that $t(x)-t(y)$. This shows that $t$ is injective.
> 2. Let $x\in [0,1]\backslash t(C)$. Then, there exists a ternary expansion of $x$: $$x=\sum_{n=1}^{\infty} \frac{a_{n}}{3^n}$$with $a_{n}\in\{ 0,1,2 \}$ s.t. $a_{n_{0}}= 1$ for some $n_{0}\geq 1$.  Let $n_{0}$ be the first such index. Now, assume for $y\in C$ that: $$\left| x-t(y) \right| =\left| \sum_{n=1}^{\infty}\frac{2y_{n}-a_{n}}{3^n} \right| < \frac{1}{3^{n_{0}+1}}$$Then, $$\left| \sum_{n=1}^{n_{0}+1}\frac{2y_{n}-a_{n}}{3^n} \right| =\left| \sum_{n=1}^\infty{}\frac{2y_{n}-a_{n}}{3^n}  \right| +\left| \sum_{n=n_{0}+2}^{\infty}\frac{2y_{n}-a_{n}}{3^n}  \right|< \frac{2}{3^{n_{0}+1}} $$ Indeed, this means $2y_{n}=a_{n}$ for all $1\leq n\leq n_{0}$, which is a contradiction. This shows that for $\varepsilon:= 3^{-n_{0}-1}$, $B_{<\varepsilon}(x)\subseteq [0,1] \backslash t(C)$.
> 3. Let $U\subseteq C$ be open. We will show that $t(U)$ is open as well. Let $x\in U$. Then, there exists a finite index set $I$ s.t. $\{ y\in C: y_{n}=x_{n},\forall n\in I \}\subseteq U$. Let $n_{0}:=\max I$ and $\varepsilon:= \frac{1}{3^{n_{0}+1}}$. Then, we claim that: $$B_{<\varepsilon}(t(x))\cap t(C)\subseteq t(U)$$Let $y\in C$ s.t. $\left|  t(x)-t(y)\right|<\varepsilon$. Then, using a similar argument as above: $$\left| \sum_{n=1}^{n_{0}+1} \frac{2(x_{n}-y_{n})}{3^n}\right|=\left| \sum_{n=1}^{\infty} \frac{2(x_{n}-y_{n})}{3^n} \right|+\left| \sum_{n=n_{0}+2}^{\infty} \frac{2(x_{n}-y_{n})}{3^n} \right| <\varepsilon+ \frac{1}{3^{n_{0}+1}} $$Therefore, $x_{n}=y_{n}$ for all $1\leq n\leq n_{0}$ and especially, $y\in U$. This proves the statement.
---
> [!lemma] Proposition 4
> If $A\subseteq C$ is connected, then $A$ is either empty or a single point.

> [!proof]-
> Assume $A$ is connected but $\left| A \right|\geq 2$. Then, there exists $x,y\in A$ s.t. there exists $n$ where $x_{n}\neq y_{n}$. Let $U:=\{ z\in C: z_{n}=x_{n} \}$ and $V:=\{ z\in C:z_{n}=y_{n} \}$. Then, they are disjoint and open with $U\sqcup V=C \supseteq A$. Therefore, $U\cap A=\varnothing$ or $V\cap A=\varnothing$, which is a contradiction.
---
