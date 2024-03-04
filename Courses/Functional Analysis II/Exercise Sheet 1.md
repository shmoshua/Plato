#FunctionalAnalysis #Series 


> [!def] Problem 1
> Let $A$ be a unital $\mathbb{C}$-algebra and $x\in A$. Suppose there are $y,z\in A$ with $xy=zx=e$. Prove $y=z$. Moreover, prove that if there is $y'\in A$ with $xy'=e$ then $y'=y$.

We have that $\begin{align}y=ey=zxy=ze=z\end{align}$. Further, $xy'=xy=yx=e$. Therefore, $y'=y$.

---
> [!def] Problem 2
> Let $X$ be a locally compact Hausdorff space, which is not compact. Denote by $\alpha X$ the one-point compactification of $X$. Show that the unital algebra $C_{0}(X)_{I}$ is canonically isomorphic to $C(\alpha X)$.

Let $\alpha X:=X \cup \{ \infty \}$. Consider the map: $$\begin{array}{cccc} {\varphi:}&{C_{0}(X)_{I}}&\to&{C(\alpha X)}\\&{(f,\lambda)} &\mapsto & {f_{\alpha}+\lambda} \end{array}{}$$where $f_{\alpha}(x)=f(x)$ for $x\neq \infty$ and $f_{\alpha}(\infty)=0$. Then,
1. **Showing $\varphi$ is well-defined**:
	   For $f\in C_{0}(X)$ and $\lambda\in \mathbb{C}$, it suffices to show that $f_{\alpha}\in C(\alpha X)$. For $U\subseteq \mathbb{C}$ open, if $0\notin U$, then $f_{\alpha}^{-1}(U)=f^{-1}(U)$ which is open. Converse, if $0\in U$, then, $f^{-1}_{\alpha}(U)=f^{-1}(U)\cup \{ \infty \}$. So there exists $K\subseteq X$ compact s.t. $f^{-1}_{\alpha}(U)=(X \backslash K)\cup \{ \infty \}$. This proves that $f_{\alpha}$ is continuous.
2. **Showing $\varphi$ is an homomorphsim**:
	We have that: $$\begin{align}\varphi((f,\lambda)(g,\mu))&=\varphi((fg+\mu f+\lambda g,\lambda \mu))\\&=f_{\alpha}g_{\alpha}+\mu f_{\alpha}+\lambda g_{\alpha}+\lambda \mu\\&=(f_{\alpha}+\lambda)(g_{\alpha}+\mu)\\&=\varphi((f,\lambda))\varphi((g,\mu))\end{align}$$
3. **Showing $\varphi$ is bijective**:
	For injectivity, $\text{ker }\varphi=(0,0)$ as $\varphi((f,\lambda))(\infty)=\lambda$ and $f_{\alpha}=0$ if and only if $f=0$. 
	
	Now, for surjectivity, let $g\in C(\alpha X)$ and $\varepsilon>0$. Then, let $U:=B_{<\varepsilon}(g(\infty))$ and $g^{-1}(U)$ is open. However, as $\infty\in g^{-1}(U)$, we have that $g^{-1}(U)=(X \backslash K)\cup \{ \infty \}$ for some compact $K\subseteq X$. Then, consider $h:=(g-g(\infty))|_{X}$. For all $x\in X \backslash K$,  we have $\left| h(x) \right|=\left| g(x)-g(\infty) \right|<\varepsilon$ and therefore, $h\in C_{0}(X)$. It follows that $g=\varphi(h)$. 

This proves that $\varphi$ is an isomorphism.

---
> [!def] Problem 3
> Construct a function $f\in L^1(\mathbb{R})$ s.t. $\left\| f*f^{*} \right\|_{1}<\left\| f \right\|^2_{1}$

Consider the function: $$f(x)=\begin{cases}1&0<x\leq 1\\-1&-1\leq x<0\\0&\text{otherwise}\end{cases}$$Then, $f^{*}=-f$ and: 
$$\begin{align}f*f^{*}(x)&=\int_{-1}^{0} f(x-t) \, dt -\int_{0}^{1} f(x-t) \, dt \\&=-\int_{x-1}^{x} f(t) \, dt +\int_{x}^{x+1} f(t) \, dt\\&=\begin{cases}-x-2&-2<x<-1\\3x+2&-1\leq x<0\\-3x+2&0\leq x\leq 1\\ x-2&1<x<2\\0&\text{otherwise}\end{cases} \end{align}$$It follows that: $$\left\| f *f^{*}\right\|_{1}=\int_{\mathbb{R}}^{} \left| f*f^{*}(x) \right|  \, dx= \frac{8}{3}<4=\left\| f \right\| _{1}^{2}  $$

---
> [!def] Problem 4
> Let $A$ be a unital $\mathbb{C}$-algebra with a norm $\|\cdot\|$ such that: 
> 1. The pair $(A,\|\cdot\|)$ is a Banach space. 
> 2. The multiplication map $A\times A\to A$ is continuous in each variable. 
> 
> Show that there is an equivalent norm $\|\cdot\|_{\text{new}}$ on $A$ such that $\|xy\|_{\text{new}}\leq\|x\|_{\text{new}}\|y\|_{\text{new}}$.

For any $x\in A$, consider $R_{x}:A\to A,y\mapsto xy$. Then, $R_{x}\in \mathcal{B}(A)$ and: $$\left\| xy \right\| \leq \left\| R_{x} \right\| \left\| y \right\| $$ for all $x,y\in A$. Now consider $T:A\to \mathcal{B}(A),x\mapsto R_{x}$:
1. **Showing that $\text{graph}(T)$ is closed**: 
   For $(x,R)\in \overline{\text{graph}(T)}$, there exists $(x_{n})_{n} \subseteq A$ s.t. $x_{n}\to x$ and $R_{x_{n}}\to R$. Then, $$\left\| x_{n}y-R(y) \right\| \leq \left\| R_{x_{n}}-R \right\|\left\| y \right\|  $$
   Therefore, for all $y\in A$: $x_{n}y\to R(y)$. However, as $x\mapsto xy$ is continuous for all $y\in A$, $x_{n}y\to xy$. It follows that $R(y)=xy$ for all $y\in A$ and $(x,R=R_{x})\in \text{graph}(T)$, i.e. the graph is closed.
2. **Constructing $\|\cdot\|_{\text{new}}$**:
By the [[Bounded Linear Map|closed graph theorem]], $T$ is bounded and, there exists $K>0$ s.t. $$\left\| xy \right\| \leq \left\| R_{x} \right\| \left\| y \right\| \leq K\|x\|\|y\|$$Now, let $\|x\|_{\text{new}}=K\|x\|$. Then, $(A,\|\cdot\|_{\text{new}})$ is Banach as the norms are equivalent and: $$\left\| xy \right\| _{\text{new}}=K\left\| xy \right\| \leq K^{2}\|x\|\|y\|=\|x\|_{\text{new}}\|y\|_{\text{new}}$$
---