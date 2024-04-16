#Definition #Algebra 

> [!definition] 
> A [[Extension Field|field extension]] $L:F$ is a ***splitting field*** of a polynomial $f(x)\in F[X]$ if $f$ factors completely in $L[X]$ and $f$ does not split in any intermediate field $F\subseteq K\subsetneq L$
---
##### Properties
> [!lemma] Theorem 1
> Let $F$ is a field and $f(x)\in F[X]$ a polynomial of degree $n$. Then, there exists a splitting field $K:F$ of $f$ s.t. $[K:F]\leq n!$

> [!proof]-
> Via induction, if $n=1$, then $K=F$. Suppose that $n>1$. If $f$ factors into linear terms in $F[X]$ then take $K=F$. Otherwise, $f$ has an irreducible factor $g(x)$ of degree $\geq 2$. Then, by Kronecker, there exists an extension $E_{1}\supseteq F(\alpha)\supseteq F$ which has a root $\alpha$ of $g(x)$ and hence $f(x)$ and $[F(\alpha):F]\leq n$.
> 
> Then, we have $f(x)=(x-\alpha)f_{1}(x)$ in $F(\alpha)[X]$ with $\deg f_{1}=n-1$. By induction there exists a splitting field $E:F(\alpha)$ of $f_{1}$ s.t. $[E:F(\alpha)]\leq (n-1)!$. Then, $$[E:F]=[E:F(\alpha)][F(\alpha):F]\leq n!$$Let $K:=\bigcap_{\beta}^{}E_{\beta}$ where $E_{\beta}$ runs over all subfields of $E$ containing $F$ and all roots of $f(x)$. This proves the statement.
---
> [!lemma] Theorem 2 (Splitting Field Isomorphism)
> Let $\varphi:F\to \tilde{F}$ be an isomorphism of fields and $f\in F[X]$ and $\varphi \circ f=:\tilde{f}\in \tilde{F}[X]$. Further, let $K,\tilde{K}$ be the splitting fields of $f,\tilde{f}$ over $F,\tilde{F}$ respectively. Then, 
> 1. $\varphi$ extends to an isomorphism $\sigma:K\to \tilde{K}$
> 2. $[K:F]=[\tilde{K}:\tilde{F}]$
> 3. the number of such extensions is at most $[K:F]$

> [!proof]-
> We will use induction over $[K:F]$. If $[K:F]=1$, then $K=F,\sigma=\varphi$ and there exists at most 1 such extension. 
> 
> Assume $[K:F]>1$. Then, there exists a root $\alpha\in K \backslash F$ of $f$. Fix this root. Then, $m_{\alpha,F}(x)|f(x)$ since $f(\alpha)=0$. If there exists an isomorphism $\sigma:K\to \tilde{K}$ extending $\varphi$, then $\sigma(\alpha)$ is a root of $(\varphi m_{\alpha,F})(x)$. Hence, the values $\sigma(\alpha)$ must come from roots of $\varphi m_{\alpha,F}$. 
> 
> Further, note that $\tilde{m}:=\varphi m_{\alpha,F}$ has a root in $\tilde{K}$, since the isomorphism $\varphi:F\to \tilde{F}$ extends to a ring isomorphism $\varphi:F[X]\to \tilde{F}[X]$ and $m_{\alpha,F}|f$ in $F[X]$, $\tilde{m}|\tilde{f}$ in $\tilde{F}[X]$. As $m_{\alpha,F}$ is irreducible in $F[X]$, $\tilde{m}$ is irreducible in $\tilde{F}[X]$, and since $\tilde{f}$ splits in $\tilde{K}$, so does $\tilde{m}$ in $\tilde{K}$. This shows that $\tilde{m}$ has a root in $\tilde{K}$. Pick $\tilde{\alpha}\in \tilde{K}$ s.t. $\tilde{m}(\tilde{\alpha})=0$. Then, $d:=\deg \tilde{m}=\deg m>1$ since $[F(\alpha):F]>1$, i.e. there are at most $d$ different choices for $\tilde{\alpha}$. 
> 
> This gives us an extension of $\varphi$ by [[Extension Field|Theorem 6]] $\varphi':F(\alpha)\to \tilde{F}(\tilde{\alpha})$ s.t. $\varphi'|_{F}=\varphi$ and $[F(\alpha):F]=[\tilde{F}(\tilde{\alpha}):\tilde{F}]$.
> 
> Now we can apply the induction: Take $F(\alpha),\tilde{F}(\tilde{\alpha})$ as new base fields with isomorphism $\varphi'$. Since $K$ is a splitting field of $f$ over $F$, so is it a splitting field of $f$ over $F(\alpha)$ and same goes for $\tilde{K}$ and $\tilde{f}$ over $\tilde{F}(\tilde{\alpha})$. As $[F(\alpha):F]>1$, we have that $[K:F(\alpha)]=[K:F] /[F(\alpha):F]<[K:F]$. By induction, $\varphi:F(\alpha)\to \tilde{F}(\tilde{\alpha})$ extends to an isomorphism $\sigma:K\to \tilde{K}$ s.t. $\sigma|_{F(\alpha)}=\varphi'$.
> 
> However, as $\varphi'|_{F}=\varphi$, we have that $\sigma|_{F}=\varphi$. Further, there are at most $[K:F(\alpha)]$ such extensions. Since $\varphi'$ is determined by $\varphi(\alpha)\in \tilde{K}$, which is a root of $\tilde{m}$. Therefore, there exists at most $[F(\alpha):F]$ choices of such $\varphi'$. This proves the statement.
> 
- **Corollary**: Let $f\in F[X]$ be a non-constant polynomial and $K,\tilde{K}$ two splitting fields of $f$ over $F$. Then, $[K:F]=[\tilde{K}:F]$ and there exists an isomorphism $\sigma:K\to \tilde{K}$ s.t. $\sigma|_{F}=\text{id}_{F}$, i.e. $\sigma$ is an ***$F$-isomorphism***.
---
##### Examples
> [!h] Example 1
> Let $f(x)=x^4-2=(x-\sqrt[4]{2  })(x+\sqrt[4]{2  })(x-i\sqrt[4]{2  })(x+i\sqrt[4]{2  })$. Then, 
> 1. a splitting field of $f$ over $\mathbb{Q}[X]$ is $\mathbb{Q}(\sqrt[4]{2  },i\sqrt[4]{2  })=\mathbb{Q}(\sqrt[4]{2  },i)$ with degree 8.
> 2. a splitting field of $f$ over $\mathbb{R}[X]$ is $\mathbb{R}(i)=\mathbb{C}$ with degree 2.
---
> [!h] Example 2
> Let $f(x):=x^3-2\in \mathbb{Q}[X]$. Then, the splitting field of $f$ over $\mathbb{Q}$ is $K:=\mathbb{Q}(\sqrt[3]{2  },\sqrt[3]{2  }\xi,\sqrt[3]{2  }\xi^{2})=\mathbb{Q}(\sqrt[3]{2  },\xi)$ where $\xi$ is the complex root of unity. Then, $$[K:\mathbb{Q}]=[\mathbb{Q}(\sqrt[3]{2  }):\mathbb{Q}]\cdot [\mathbb{Q}(\xi):\mathbb{Q}]=6$$