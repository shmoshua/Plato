#Example

It is known that this is not possible for $d\geq 3$. Therefore, we will consider $d=1$.

---
##### Construction
Consider $\mathbb{R}/\mathbb{Z}$, i.e. real numbers modulo 1 and let $\pi:\mathbb{R} \to \mathbb{R} / \mathbb{Z}$ be the canonical projection. Further, let: 
$$\ell^\infty(\mathbb{R} / \mathbb{Z}):=\{ f:\mathbb{R} / \mathbb{Z} \to \mathbb{R} |f\text{ is bounded} \}$$
We say that $f\in \ell^\infty(\mathbb{R} / \mathbb{Z})$ is measurable, if $f\circ\pi: \mathbb{R} \to \mathbb{R}$ is $\mathcal{L}^1$-measurable, normalized s.t. $\mathcal{L}^1[0,1]=1$. 

For a measurable function $f\in \ell^\infty(\mathbb{R} / \mathbb{Z})$, we define: 
$$\int _{\mathbb{R}/\mathbb{Z}}f \, d\mathcal{L}^1:=\int _{0}^1(f\circ \pi)(x) \, d\mathcal{L}^1(x)  $$which exists, as $f \circ \pi$ is bounded and measurable. Then, we have an action of $\mathbb{R}$ by translation on $\ell^\infty(\mathbb{R} / \mathbb{Z})$ and $h\in \mathbb{R}$, $x+h \in \mathbb{R} / \mathbb{Z}$ is well-defined. Then, for $f\in \ell^\infty (\mathbb{R} / \mathbb{Z})$, $$ f_{h}(x)=f(x+h)$$

> [!lemma] Theorem 1
> There exists a linear map $I: \ell^\infty(\mathbb{R} / \mathbb{Z}) \to \mathbb{R}$ s.t.
> 1. $I(f)\geq 0$ if $f \geq 0$
> 2. $I(f)=\int _{\mathbb{R}/\mathbb{Z}}f \, d\mathcal{L}^1$ whenever $f$ is measurable. 
> 3. $I(f_{h})=I(f)$ for all $h\in \mathbb{R}$
> 
> for all $f\in \ell^\infty(\mathbb{R} / \mathbb{Z})$.

This is application of [[Gauge Function|Hahn-Banach]] with $V=\ell^\infty( \mathbb{R} / \mathbb{Z})$ and $M = \{ f\in \ell^\infty(\mathbb{R} / \mathbb{Z}):f \text{ is measurable} \}$ with the linear form: $$I_{0}(f):=\int _{\mathbb{R}/\mathbb{Z}}f \, d\mathcal{L}^1 $$

---
##### Finding the gauge function
The key now is to find the appropriate [[Gauge Function|gauge function]] $p:V \to \mathbb{R}$ s.t. $I_{0}(f)\leq p(f)$ for all $f\in M$.

For every pair $(A,\alpha)$ of a finite set $A$ and a function $\alpha: A \to \mathbb{R}$ define: 
$$M_{(A,\alpha)}(f):=\sup_{x \in \mathbb{R} / \mathbb{Z}} \frac{1}{\left| A \right| }\left( \sum_{a\in A}^{}f(x+\alpha(a)) \right) $$for all $f \in \ell^\infty(\mathbb{R} / \mathbb{Z})$. Then, 
$$p(f):=\inf \{ M_{(A,\alpha)}(f):A\text{ finite}, \alpha:A \to \mathbb{R} \}$$
Since we have: $$-\left\| f \right\| _{\infty}\leq M_{(A,\alpha)}(f)\leq \left\| f \right\| _{\infty}$$$p(f)$ is well defined. 

> [!lemma] Proposition 2
> $p: \ell^\infty(\mathbb{R} / \mathbb{Z})\to \mathbb{R}$ is a gauge function.

> [!proof]-
> Let's define for $f\in \ell^\infty(\mathbb{R} / \mathbb{Z})$,$$S(f):=\sup_{x\in \mathbb{R} / \mathbb{Z}}f(x)\in \mathbb{R}$$Then, $S$ satisfies the following properties:
> 1. $S(c\cdot f)=cS(f)$ if $c\geq 0$ for $f\in \ell^\infty (\mathbb{R}/\mathbb{Z})$
> 2. $S(f_{1}+f_{2})\leq S(f_{1})+S(f_{2})$ for $f_{1},f_{2}\in \ell^\infty(\mathbb{R} / \mathbb{Z})$
> 3. $S(f_{h})=S(f)$ for all $h\in \mathbb{R}$ and $f\in \ell^\infty (\mathbb{R}/ \mathbb{Z} )$
>    
> Therefore, we can conveniently rewrite: $$M_{(A,\alpha)}(f)=S\left( \frac{1}{|A|}\sum_{a\in A}^{}f_{\alpha(a)} \right) $$with the following properties:
> 1. $M_{(A,\alpha)}(c\cdot f)=cM_{(A,\alpha)}(f)$ if $c\geq 0$ for $f\in \ell^\infty (\mathbb{R}/\mathbb{Z})$
> 2. $M_{(A,\alpha)}(f_{1}+f_{2})\leq M_{(A,\alpha)}(f_{1})+M_{(A,\alpha)}(f_{2})$ for $f_{1},f_{2}\in \ell^\infty(\mathbb{R} / \mathbb{Z})$
> 3. $M_{(A,\alpha)}(f_{h})=M_{(A,\alpha)}(f)$ for all $h\in \mathbb{R}$ and $f\in \ell^\infty (\mathbb{R}/ \mathbb{Z} )$
>    
> From 1, it follows that $p(cf)=cp(f)$ for $c\geq 0$. For the second property of a gauge, let $(A,\alpha)$ and $(B, \beta)$ be two finite sets with their map to $\mathbb{R}$. We then define: $$\begin{array}{cccc} {\alpha+\beta:}&{A\times B}&\to&{\mathbb{R}}\\&{(a,b)} &\mapsto & {\alpha(a)+\beta(b)} \end{array}{}$$Then, for all $g\in \ell^\infty(\mathbb{R} / \mathbb{Z})$
> 1. $M_{(A\times B,\alpha+\beta)}(g)\leq M_{(A,\alpha)}(g)$ and
> 2. $M_{(A\times B,\alpha+\beta)}(g)\leq M_{(B,\beta)}(g)$ 
>  
>  as, $$\begin{align}M_{(A\times B,\alpha+\beta)}(g)&=S\left( \frac{1}{\left| A \right| \left| B \right| }\sum_{(a,b)\in A\times B}^{} g_{\alpha(a)+\beta(b)}\right)\\&=S\left( \frac{1}{\left| B \right| }\sum_{b\in B}^{}\left( \frac{1}{\left| A \right| }\sum_{a\in A}^{} g_{\alpha(a)} \right)_{\beta(b)}\right) \\&\leq \frac{1}{\left| B \right| }\sum_{b\in B}^{}S\left( \frac{1}{|A|}\sum_{a\in A}^{}g_{\alpha(a)} \right)\\&=M_{(A,\alpha)}(g) \end{align}$$
>
>Let now $f_{1},f_{2}\in \ell^\infty( \mathbb{R} / \mathbb{Z})$ and $(A,\alpha),(B,\beta)$ s.t. 
>1. $M_{(A,\alpha)}(f_{1})< p(f_{1})+\varepsilon$
>2. $M_{(B,\beta)}(f_{2})<p(f_{2})+\varepsilon$
>
>Then, $$\begin{align}p(f_{1}+f_{2})&\leq M_{(A\times B,\alpha+\beta)}(f_{1}+f_{2})\\&\leq M_{(A\times B,\alpha+\beta)}(f_{1})+M_{(A\times B,\alpha+\beta)}(f_{2})\\&\leq M_{(A,\alpha)}(f_{1})+M_{( B,\beta)}(f_{2})\\&< p(f_{1})+p(f_{2})+2\varepsilon\end{align}$$
>By, $\varepsilon \to 0$, we get $p(f_{1}+f_{2})\leq p(f_{1})+p(f_{2})$ and $p$ is a gauge function.
>
---
##### Showing the conditions for Hahn-Banach
Now we need to show that $I_{0}(f) \leq p(f)$ for all measurable $f\in \ell^\infty( \mathbb{R} / \mathbb{Z})$. We have for any $(A,\alpha)$: $$I_{0}(f)=\frac{1}{\left| A \right| }\int _{\mathbb{R} / \mathbb{Z}}\sum_{a\in A}^{}f_{\alpha(a)} \, d\mathcal{L}^1 \leq \int _{\mathbb{R} / \mathbb{Z}}S\left( \frac{1}{\left| A \right| }\sum_{a\in A}^{}f_{\alpha(a)} \right)  \, d\mathcal{L}^1 =M_{(A,\alpha)}(f) $$
Therefore, by taking the infimum, $I_{0}(f )\leq p(f)$.

---
##### Checking the linear extension meets the properties

Let $I: \ell^\infty(\mathbb{R} / \mathbb{Z}) \to \mathbb{R}$ be the linear form extending $I_{0}$ satisfying: $$I(f)\leq p(f)$$for all $f\in \ell^\infty(\mathbb{R} / \mathbb{Z})$. We will show $I$ meets the three properties from Theorem 1.
1. Let $f\in \ell^\infty(\mathbb{R} / \mathbb{Z})$. If $f(x)\leq 0$ for all $x\in \mathbb{R} / \mathbb{Z}$, then $I(f)\leq p(f)\leq M_{(A,\alpha)}(f)\leq 0$. Therefore, if $f\geq 0$, then $-f\leq 0$ and $I(-f)\leq 0$. By linearity of $I$, we have: $$I(f)\geq 0$$
2. Follows from $I_{0}$.
3. We claim first that $p(f - f_{h})\leq 0$ for all $f\in \ell^\infty(\mathbb{R} / \mathbb{Z})$ and $h\in \mathbb{R}$. Let $1 \leq N \in \mathbb{N}$ and $\alpha_{N}(j)=j\cdot h$. Then, $$\frac{1}{N}\sum_{j=1}^{N}(f-f_{h})(x+jh)=\frac{1}{N}\sum_{j=1}^{N}[f(x+jh)-f(x+(j+1)h)]=\frac{1}{N}(f(x+h)-f(x+(N+1)h))$$Therefore, $M_{([N],\alpha_{N})}(f-f_{h})\leq \frac{2\left\| f \right\|_{\infty}}{N}\to 0$, therefore, $I(f-f_{h})\leq p(f-f_{h})\leq 0$. By replacing $f$ by $f_{-h}$ we get: $$I(f)-I(f_{h})=I(f-f_{h})=0$$
---
##### Constructing the Finitely additive Outer Measure for $\mathbb{R} / \mathbb{Z}$

We will define the measure as follows: We have $\lambda_{0}: \mathcal{P}(\mathbb{R} / \mathbb{Z}) \to [0,+\infty]$ defined as: $$\lambda_{0}(E) =I(\chi_{E})$$where $\chi_{E}$ is the characteristic function of $E$. Then, we have that: 
1. $\lambda_{0}(E_{1} \cup E_{2})=\lambda_{0}(E_{1})+\lambda_{0}(E_{2})$ for disjoint subsets $E_{1},E_{2}\subseteq \frac{\mathbb{R}}{\mathbb{Z}}$
2. $\lambda_{0}(E)=\lambda(E)$ if $E$ is measurable.
3. $\lambda_{0}(E+h)=\lambda(E)$ for all $h\in \mathbb{R}$.
   
And, this result can be extended to $\mathbb{R}$ by having each interval $[j,j+1)$ get translated to $[0,1)=\mathbb{R} / \mathbb{Z}$.

---
##### Equivalent Implications
This result can be rephrased in terms of the existence of a finitely additive set function on: $$S^1=\{ (x,y)\in \mathbb{R}^{2}: x^{2}+y^{2} =1 \}$$
as we can parametrize: $$\begin{array}{cccc} {}&{\mathbb{R} / \mathbb{Z}}&\to&{S^1}\\&{t} &\mapsto & {(\cos(2\pi t),\sin(2\pi t))} \end{array}{}$$
that is $\text{SO}(2)$-invariant and extends the Lebesgue (angular) measure on $S^1$.

In contrast, we can look at the action of $\text{SO}(3)$ on: $$S^{2}=\{ (x,y,z)\in \mathbb{R}^3 :x ^{2}+y^{2}+z^{2}=1\}$$
This, however, has a paradoxical decomposition as was shown by [[Banach-Tarski]]:

> [!lemma] Theorem 3
> There is a countable subset $\Lambda \subseteq S^{2}$, a partition: $$S^{2} \backslash \Lambda=A_{1}\cup  A_{2} \cup A_{3} \cup A_{4}$$and two rotations $a,b\in \text{SO}(3)$ s.t. 
> 1. $a(A_{2}) = A_{2} \cup A_{3} \cup A_{4}$ and
> 2. $b(A_{4})=A_{1} \cup A_{2} \cup A_{4}$
---
> [!lemma] Corollary 4
> There is no $\text{SO}(3)$-invariant additive set function on $S^{2}$ extending the [[Lebesgue Measure]].

> [!proof]-
> If $\lambda: \mathcal{ P}(S^{2})\to [0,+\infty)$ were such a set function, we would first have $\lambda(\Lambda)=0$ as $\Lambda$ is countable. Then, $$\lambda(A_{2})=\lambda(a(A_{2}))=\lambda(A_{2})+\lambda(A_{3})+\lambda(A_{4})$$which implies that $\lambda(A_{3})=\lambda(A_{4})=0$. Similarly, we also have that $\lambda(A_{1})=\lambda(A_{2})=0$. Therefore, $$\lambda(S^{2})=\lambda(A_{1})+\lambda(A_{2})+\lambda(A_{3})+\lambda(A_{4})+\lambda(\Lambda)=0$$which implies $\lambda(E)=0$ for all $E \subseteq S^{2}$.
---