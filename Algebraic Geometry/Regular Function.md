#Definition #AlgebraicGeometry 

> [!definition]
> Let $X$ be an [[algebraic set]] and $U\subseteq X$ open.
> 1. A map $\varphi:U\to K$ is ***regular*** if for every $a\in U$ there exists $f,g\in A(X)$ with $f\neq 0$ s.t. $$\varphi(x)=\frac{g(x)}{f(x)},\quad \forall x\in U_{a}\subseteq U$$for some open neighborhood $U_{a}$. 
> 2. The set of all regular functions on $U$ is denoted as $\mathcal{O}_{X}(U)$.
- **Remark**: $\mathcal{O}_{X}(U)$ is a $K$-algebra.
---
##### Properties
> [!lemma] Proposition 1 (Zero Loci of Regular Functions are Closed)
> Let $U$ be an open subset of an affine variety $X$. Let $\varphi\in \mathcal{O}_{X}(U)$. Then, 
> $$V(\varphi):=\{ x\in U:\varphi(x)=0 \}$$is closed in $U$.

> [!proof]-
> Any point $a\in U$ has an open neighborhood $U_{a}\subseteq U$ on which $\varphi=\frac{g_{a}}{f_{a}}$ for some $f_{a},g_{a}\in A(X)$. So the set: $$U_{a} \backslash V(\varphi)=\{ x\in U_{a}:\varphi(x)\neq 0 \}=U_{a} \backslash V(g_{a})$$which is open in $X$. Hence, so is the union over all $a$, which is $U \backslash V(\varphi)$. Hence, $V(\varphi)$ is closed in $U$.

---
> [!lemma] Proposition 2 (Identity Theorem for Regular Functions)
> Let $U\subseteq V$ be non-empty open sets of irreducible affine variety $X$. 
> 1. If $\varphi_{1},\varphi_{2}\in \mathcal{O}_{X}(V)$ agree on $U$, they agree on $V$.

> [!proof]-
> We have that:
> 1. the zero locus $V(\varphi_{1}-\varphi_{2}) \supseteq U$ and is closed in $V$ by Proposition 1. Hence, $\overline{U}\subseteq V(\varphi_{1}-\varphi_{2})$. However as $X$ is irreducible, $\overline{V}=X$ and $V$ is irreducible as well. This again means that $\overline{U}=V$. Hence, $V\subseteq V(\varphi_{1}-\varphi_{2})$. 

---
> [!lemma] Proposition 3 (Regular Functions on Distinguished Open Sets)
> Let $X$ be an affine variety and $f\in A(X)$. Then, 
> $$\mathcal{O}_{X}(D(f))=\left\{  \frac{g}{f^n}:g\in A(X),n\in \mathbb{N}  \right\}$$

> [!proof]-
> We have that:
> 1. $\supseteq$ is obvious. On $D(f)$, we have that $g/f^n$ is regular.
> 2. For $\subseteq$, let $\varphi:D(f)\to K$ be a regular function. By definition, for every $a\in D(f)$, there is a local representation $\varphi=\frac{g_{a}}{f_{a}}$ on an open neighborhood $U_{a}$. Wlog we may assume that the neighborhoods are $D(h_{a})$. Moreover, we may replace $g_{a}$ and $f_{a}$ with $g_{a}h_{a}$ and $f_{a}h_{a}$. Hence, both the numerator and denominator of $\varphi$ vanish on $V(h_{a})$. Then, $f_{a}$ vanishes on $V(h_{a})$ and does not vanish on $D(h_{a})$, i.e. $h_{a}$ and $f_{a}$ have the same zero locus, i.e. $h_{a}=f_{a}$.
>    
>    As a consequence, we have that $g_{a}f_{b}=g_{b}f_{a}$ for $a,b\in D(f)$. These two functions agree on $D(f_{a})\cap D(f_{b})$ since $\varphi=\frac{g_{a}}{f_{a}}=\frac{g_{b}}{f_{b}}$ and both zero otherwise. 
>    
>    Now all our open neighborhood cover $D(f)$, i.e. $D(f)=\bigcup_{a\in D(f)}^{}D(f_{a})$. Passing to the complement we have: $$V(f)=\bigcap_{a\in D(f)}^{}V(f_{a})=V(\{ f_{a} \}_{a\in D(f)})$$Hence, $f\in I(V(f))=\sqrt{ (f_{a})_{a\in D(f)} }$, i.e. $f^n=\sum_{a}^{}k_{a}f_{a}$ for some $n\in \mathbb{N}$ and $k_{a}\in A(X)$ for finitely many elements $a\in D(f)$. By defining $g:=\sum_{a}^{}k_{a}g_{a}$, we claim that $\varphi=g / f^n$ on all of $D(f)$. For all $b\in D(f)$, we have that $\varphi=g_{b} / f_{b}$ and: $$gf_{b}=\sum_{a}^{}k_{a}g_{a}f_{b}=\sum_{a}^{}k_{a}g_{b}f_{a}=g_{b}f^n$$on $D(f_{b})$. Further, these sets cover $D(f)$. 
---
> [!lemma] Lemma 4 (Stalks of Regular Functions as Localizations)
> Let $X$ be an affine variety and $a\in X$. Then, 
> 1. the [[sheaf|stalk]] $\mathcal{O}_{X,a}\cong A(X)_{I(a)}$ as a $K$-algebra where $A(X)_{I(a)}$ is the localization of $A(X)$, i.e. $$\mathcal{O}_{X,a}\cong \left\{  \frac{g}{f}:f,g\in A(X),f(a)\ne 0  \right\}$$
> 2. $\mathcal{O}_{X,a}$ is a [[local ring]] with the unique ideal: $$I_{a}:=\{ \overline{(U,\varphi)}:\varphi(a)=0 \}\cong \left\{  \frac{g}{f}:f,g\in A(x), g(a)=0,f(a)\neq 0  \right\}$$ $\mathcal{O}_{X,a}$ is called the ***local ring of $X$ at $a$.***

> [!proof]-
> Consider the $K$-algebra homomorphism: $$A(X)_{I(a)}\to \mathcal{O}_{X,a},\quad \frac{g}{f}\mapsto  \overline{\left( D(f), \frac{g}{f} \right) }$$This is indeed well-defined: If $\frac{g}{f}=\frac{g'}{f'}$, then $h(gf'-g'f)=0$ for some $h\in A(X) \backslash I(a)$. Hence, on the open neighborhood $D(h)\cap D(f)\cap D(f')$ of $a$, the functions $\frac{g}{f}$ and $\frac{g'}{f'}$ agree. Therefore, they determine the same stalk in $\mathcal{O}_{X,a}$.
> 
> The $K$-algebra homomorphism is surjective by definition and also injective: If $\frac{g}{f}$ represents zero in $\mathcal{O}_{X,a}$, by shrinking the neighborhood if necessary we may assume that it is a distinguished open set $D(h)$ containing $a$ for some $h\in A(X)\backslash I(a)$. But then, $h(g 1 -0f)$ is zero on all of $X$, hence zero in $A(X)$. 

---
> [!lemma] Lemma 5
> Let $X\subseteq \mathbb{A}^n$ be an affine variety and $a\in X$. We have that: $$\mathcal{O}_{X,a}\cong\mathcal{O}_{\mathbb{A}^n,a} / I(X)\mathcal{O}_{\mathbb{A}^n ,a}$$where $I(X)\mathcal{O}_{\mathbb{A}^n ,a}$ denotes the ideal in $\mathcal{O}_{\mathbb{A}^n,a}$ generated by all quotients $\frac{f}{1}$ for $f\in I(X)$.

> [!proof]+
> Consider the following homomorphism: $$\Phi:\mathcal{O}_{\mathbb{A}^n,a}\to \mathcal{O}_{X,a},\quad \overline{(U,\varphi)}\mapsto  \overline{(U,\overline{\varphi})}$$where for any $a\in U$, there exists a neighborhood $U_{a}\ni a$ s.t. $\varphi=\frac{g}{f}$ for some $f,g\in A$ with $f\ne 0$, we have: $$\overline{\varphi}=\frac{\overline{g}}{\overline{f}}$$We know that $\overline{f}\neq 0$. Indeed, if $\overline{f}=0$, then.
> 
> To show that this is well-defined, let $$