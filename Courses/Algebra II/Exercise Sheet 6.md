#Series #Algebra 

> [!def] Problem 1
> Let $K$ be a field of characteristic 0 and $L:K$ a finite algebraic extension. Show that $L:K$ is simple if and only if there are only finitely many intermediate fields.

Assume that $L=K(\alpha)$ for some $\alpha\in L$ and $[L:K]=n$. Then, we can write $m_{\alpha,K}=f_{1}\cdot\dots \cdot f_{m}$ in $L[X]$, where $f_{i}$ is irreducible. Let $F$ be an intermediate field. Then, $m_{\alpha,F}|m_{\alpha,K}$ in $F[X]$ and consequently in $L[X]$. Therefore, $m_{\alpha,F}=f_{i_{1}}\cdot\dots \cdot f_{i_{k}}$ for $i_{j}\in[m]$. Let $m_{\alpha,F}(x)=a_{0}+a_{1}x+\dots+x^r\in F[X]$. Then, $m_{\alpha,F}=m_{\alpha,\tilde{F}}$ where $\tilde{F}:=K(a_{0},\dots,a_{r-1})$. Then, we have that $F(\alpha)=K(\alpha)=\tilde{F}(\alpha)$ and $$[K(\alpha):\tilde{F}]=[K(\alpha):F]$$

