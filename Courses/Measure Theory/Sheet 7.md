#Series #MeasureTheory 

##### Exercise 7.1
1. **True**. For all open sets $U \subseteq \mathbb{R}$, $g^{-1}(U)$ is Borel. Therefore, $f^{-1}(g^{-1}(U))$ is $\mu$-measurable. 
2. **False**. Let $P$ be the Vitali set. We can define $f(x)=\begin{cases}x&x\in P\\-x&x\notin P \end{cases}$. Then, for all $c\in \mathbb{R}$, $\mathcal{L}^1(f^{-1}(\{ c \}))=0$, but $f^{-1}[0,1]=P$ is non $\mathcal{L}^1$-measurable.
3. **True**. Let $\mathbb{R}=\tilde{\mathbb{R}}\cup D$ be the partition where $D$ represents the discontinuity set of $f$. Then, for any $a\in \mathbb{R}$:$$f^{-1}(-\infty,a)=\underbrace{ (f^{-1}(-\infty,a)\cap \tilde{\mathbb{R}}) }_{ \text{open} }\cup\underbrace{ (f^{-1}(-\infty,a)\cap D) }_{ \subseteq D }$$Therefore, $f^{-1}(-\infty,a)\cap \tilde{\mathbb{R}}$ is $\mathcal{L}^1$-measurable and so is $f^{-1}(-\infty,a)\cap D$ as $\mathcal{L}^1(D)=0$.
4. **True**. We have that $\limsup_{ k \to \infty }f_{k}$ and $\liminf_{ k \to \infty }f_{k}$ are both $\mu$-measurable. We then define: 
	1. $E_{1}:=\{ x\in \mathbb{R}^n: \limsup_{ k \to \infty }f_{k}(x)=\liminf_{ k \to \infty }f_{k}(x)\}$
	2. $E_{2}:=\{ x\in \mathbb{R}^n: \limsup_{ k \to \infty }f_{k}(x)<+\infty \}$
	   
	Then, $E_{1}=(\limsup_{ k \to \infty }f_{k}-\liminf_{ k \to \infty }f_{k})^{-1}(\{ 0 \})$ is $\mu$-measurable, $E_{2}=(\limsup_{ k \to \infty }f_{k})^{-1}(-\infty,\infty)$ is $\mu$-measurable. Therefore, $E$ is $\mu$-measurable.
---
##### Exercise 7.2
- (i => ii): 
---
##### Exercise 7.3
Firstly, we know that $f-g$ is also measurable. Then, 
1. $\{ x:f(x)=g(x) \}=(f-g)^{-1}(\{ 0 \})$ which is measurable.
2. $\{ x:f(x)<g(x) \}=(f-g)^{-1}(-\infty,0)$ which is measurable.
---
##### Exercise 7.4
1. As $h$ is monotonically increasing, for all $x<y$, $g(x)=h(x)+x<h(y)+y=g(y)$.
2. 
---
##### Exercise 7.5
