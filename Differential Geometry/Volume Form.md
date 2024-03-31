#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. A ***volume form*** on $M$ is a [[Differential k-Form|smooth differential $m$-form]] $\omega$, i.e. $\omega\in \Omega^m(M)$, which is nowhere vanishing, i.e. $\omega_{x}\neq 0$ for all $x\in M$.
- **Related definition**: For $f\in C^\infty_{c}(M)$, we can define: $$\int_{M}^{} f \, d\text{Vol}_{g}:=\sum_{i\in I}^{}\int_{\varphi_{i}(U_{i})}^{} (f\cdot g_{i})(\varphi _{i}^{-1}(x))\sqrt{ \det g^{(i)}(x) } \, dx  $$
---
##### Properties

$$\begin{align}Z&:=\sum_{t=0}^{\infty}P_{\text{LN}}(a_{t})\\&=\sum_{t=0}^{\infty}P_{\text{SM}}(\mathsf{EOS}|a^{t})\left( \prod_{t=0}^{t-1} \underbrace{ P_{\text{SM}}(a|a^t) }_{ =:c }\right) \\&=\sum_{t=0}^{\infty}P_{\text{SM}}(\mathsf{EOS}|a^{t}) c^t\\&=\sum_{t=0}^{\infty}\frac{p_{\text{LM}}(a^t)}{\pi(a^t)}c^t\end{align}$$
$$P_{SM}(EOS|a^t)=P_{SM}(EOS|a^{t-1})P_{SM}(a^t)$$

$$P_{SM}(EOS|a^t)=\frac{p_{\text{LM}}(a^t)}{\pi(a^t)}$$