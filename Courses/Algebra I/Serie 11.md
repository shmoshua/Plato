#Series #Algebra

##### Exercise 58
1. We assume that $R$ is a non-trivial domain. Let $n:=\text{char}(R)$ and assume $n\neq 0$. As $R$ is non-trivial, $n\geq 2$. We will show that $n$ has to be prime. If $n$ is not prime, there exists $1<p,q<n$ s.t. $n=pq$. Then, we have that: $$n\cdot 1_{R}=(p\cdot 1_{R})(q\cdot 1_{R})=0_{R}$$
	However, as $R$ is a domain, either $p\cdot 1_{R}=0_{R}$ or $q \cdot 1_{R}=0_{R}$. Consequently, $\text{char}(R)=p$ or $\text{char}(R)=q$ which is a contradiction.
2. If $\text{char}(R)=n>0$, then $n\cdot 1=0$. Then, $$n\cdot a=n\cdot 1\cdot a=0\cdot a=0$$
---
##### Exercise 59
1. Let $R$ be a commutative ring and $\mathfrak{m}\subseteq R$ a maximal ideal. then, by definition, $\mathfrak{m}\neq R$. Now, for $a,b\in R$ s.t. $ab\in \mathfrak{m}$, we have that for $R / \mathfrak{m}$: $$\overline{a}\cdot \overline{b}=\overline{a b}=\overline{0}$$However, as $\mathfrak{m}$ is maximal, $R / \mathfrak{m}$ is a field and we have that $\overline{a}=\overline{0}$ or $\overline{b}=\overline{0}$. From this it follows that $a\in \mathfrak{m}$ or $b\in \mathfrak{m}$. Therefore, $\mathfrak{m}$ is a prime ideal.
2. Let $R$ be a finite integral domain with $\left| R \right|=n$ and $x\in R$ where $x\neq 0$. As $x$ has no zero-divisor, $x^1,\dots,x^n\neq 0$. In other words, there exists $1\leq a<b\leq n$ s.t. $x^a=x^b$. From which it follows that $x^{b-a}=1$ and $x^{b-a-1}=x ^{-1}$ where $b-a\geq 2$. Therefore, every non-zero element has a multiplicative inverse and $R$ is a field.
3. We will first show that $R / \mathfrak{p}$ is an integral domain. As $\mathfrak{p}\neq R$, $\mathfrak{p}$ is non-trivial. Further, for $\overline{a},\overline{b}\in R / \mathfrak{p}$, with $\overline{a}\cdot \overline{b}=\overline{a\cdot b}=\overline{0}$, we have that $ab\in \mathfrak{p}$ and that $a\in \mathfrak{p}\lor b\in \mathfrak{p}$. In other words, $\overline{a}=\overline{0}$ or $\overline{b}=\overline{0}$. This shows that $R / \mathfrak{p}$ is an integral domain.
	As $R / \mathfrak{p}$ is finite, by 2, we have that $R / \mathfrak{p}$ is a field, which implies that $\mathfrak{p}$ is maximal.
---
##### Exercise 60
1. First, we show that $\mathfrak{a}$ is an additive subgroup of $\mathcal{P}(\mathbb{N})$. We know from Exercise 50, that for $A\in \mathcal{P}(\mathbb{N})$, $-A=A$. Therefore, for $A,B\in \mathfrak{a}$,$$A+B=(A \backslash B)\cup(B \backslash A)\in \mathfrak{a}$$as it is a union of two finite sets. Therefore, $\mathfrak{a}$ is an additive subgroup. Further, for any $X\in \mathcal{P}(\mathbb{N})$ and $A\in \mathfrak{a}$, $$A*X=X*A=X \cap A\subseteq A$$hence, $A*X=X*A\in \mathfrak{a}$. This proves that $\mathfrak{a}$ is an ideal.
2. Let $A=\{ 0 \}\cup\{n\in \mathbb{N}:n\text{ is even}\}$ and $B=\{ 0 \}\cup\{n\in \mathbb{N}:n\text{ is odd}\}$. Then, $$A*B=A\cap B=\{ 0 \}\in \mathfrak{a}$$However, neither $A$ or $B$ are in $\mathfrak{a}$. Therefore, $\mathfrak{a}$ is not a prime ideal.
---
##### Exercise 61
As $(a+b \sqrt{ d })(a'+b'\sqrt{ d })=aa'+bb'd+(ab'+ba')\sqrt{ d }$, for $$\frac{a+b \sqrt{ d }}{a'+b'\sqrt{ d }}= \frac{(aa'-bb'd)+(ba'-ab')\sqrt{ d }}{a'a'-b'b'd}=\frac{aa'-bb'd}{a'a'-b'b'd}+\frac{(ba'-ab')\sqrt{ d }}{a'a'-b'b'd}$$Therefore, $\text{Quot}(\sqrt{ d })=\mathbb{Q}[\sqrt{ d }]$.

---
##### Exercise 62
1. If $R$ is trivial, then $M$ is empty and has a finite character. Therefore, we assume $R$ is non-trivial. Then, as $(0)\in M$, $M$ is non-empty. Now, for $X\in M$, let $Y\subseteq X$ be finite. We will show that $1_{R}\notin (Y)$. Assume that $1_{R}\in (Y)$. Then, for all ideal $\mathfrak{a}\subseteq R$ s.t. $Y \subseteq \mathfrak{a}$, $1_{R}\in \mathfrak{a}$. Therefore, $1_{R}\in (X)$ which is a contradiction. 
	
	Conversely, assume that $1_{R}\in(X)$. Then, we define: $$\mathfrak{A}:=\left\{  \sum_{i=1}^{n}r_{i}x_{i}:r_{i}\in R,x_{i}\in X, n\in \mathbb{N}  \right\}$$One can easily see that $\mathfrak{A}$ is an ideal and $X\subseteq \mathfrak{A}$. Therefore, $(X)\subseteq \mathfrak{A}$ and there exists $x_{1},\dots,x_{n}\in X$ s.t. $\sum_{i=1}^{n}r_{i}x_{i}=1_{R}$. Therefore, there exists a finite subset $Y:=\{ x_{1},\dots,x_{n} \}$ s.t. $1_{R}\in (Y)$. This proves that $M$ has a finite character.
2. Using the Teichmüller principle, $M$ has a maximal element $X$ w.r.t. inclusion. We will show that $(X)$ is a maximal ideal in $R$. Firstly, as $1_{R}\notin(X)$, $(X)\neq R$. Let $\mathfrak{a}\subsetneq R$ be an ideal. Then, $1_{R}\notin(\mathfrak{a})=\mathfrak{a}$ and $\mathfrak{a}\in M$. If $(X)\subsetneq\mathfrak{a}$, then $X\subsetneq \mathfrak{a}$ which is a contradiction to the maximality of $X$. Therefore, $R$ has a maximal ideal.
3. Let $\mathfrak{a}\subseteq R$ and $\mathfrak{a}\neq R$ be an ideal. If $\mathfrak{a}$ is maximal, we are done. Otherwise, 
4. from the reasoning in 2, $\mathfrak{a}\in M$. 