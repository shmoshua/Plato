#Definition #DifferentialGeometry 

> [!definition]
> Let $(M,g)$ be a [[Riemannian manifold]] and $\gamma:[a,b]\to M$ be a $C^1$-curve. Then, the ***length*** of $\gamma$ is:
> $$L(\gamma):=\int_{a}^{b} \sqrt{ g_{\gamma(t)}(\gamma'(t),\gamma'(t)) } \, dt  $$For a piecewise $C^1$-curve $\gamma:[a,b]\to M$ with $a=a_{0}<a_{1}<\dots<a_{n}=b$ with $\gamma|_{[a_{i},a_{i+1}]}\in C^1$ for all $i$, $$L(\gamma):=\sum_{i=0}^{n-1}L(\gamma|_{[a_{i},a_{i+1}]})$$
> If $(M,g)$ is connected and $p,q\in M$, the ***distance*** between $p,q$ is defined as:$$d(p,q):=\inf\{ L(\gamma)|\gamma:[a,b]\to M\text{ piecewise }C^1,\gamma(a)=p,\gamma(b)=q \}$$
- **Remark**: Since $t\mapsto g_{\gamma(t)}(\gamma'(t),\gamma'(t))$ is bounded, $L(\gamma)<+\infty$.
- **Remark**: If $\alpha:[\tilde{a},\tilde{b}]\to[a,b]$ is a $C^1$-diffeomorphism and $\tilde{\gamma}:=\gamma \circ\alpha$ is a reparametrization of $\gamma$, then $L(\tilde{\gamma})=L(\gamma)$. 
