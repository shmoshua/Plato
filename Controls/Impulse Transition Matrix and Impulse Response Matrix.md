#Definition #LST 

> [!definition]
> For a [[Linear Time Varying System|time varying linear system]], the ***impulse transition matrix*** is $K(\cdot,\cdot):\mathbb{R}\times \mathbb{R} \to\mathbb{R}^{n\times m}$ where: $$K(t,\sigma)=\begin{cases}\Phi(t,\sigma)B(\sigma)&\text{if }t\geq\sigma\\0&\text{otherwise}\end{cases}$$
> where $\Phi(\cdot,\cdot)$ denotes the [[State Transition Matrix|state transition matrix]]. Similarly, the ***impulse response matrix*** is $H(\cdot,\cdot):\mathbb{R}\times \mathbb{R} \to \mathbb{R}^{p,m}$ where: $$H(t,\sigma)=\begin{cases}C(t)\Phi(t,\sigma)B(\sigma)+D(t)\delta_{\sigma}(t)&\text{if  }t\geq \sigma\\0&\text{otherwise}\end{cases}$$

- The impulse transition matrix is well-defined, but the impulse response matrix is not due to [[Dirac delta]] (except if $D(\cdot)=0$).
---
##### Derivation
We have that:
- **Zero state transition**: $$\begin{array}{cccc} {s(t,t_{0},0,\cdot ):}&{PC(\mathbb{R},\mathbb{R}^m)}&\to&{\mathbb{R}^n}\\&{u(\cdot )} &\mapsto & {\int_{t_{0}}^{t} \Phi(t,\tau)B(\tau)u(\tau) \, d\tau } \end{array}{}$$
- **Zero state response**: $$\begin{array}{cccc} {\rho(t,t_{0},0,\cdot ):}&{PC(\mathbb{R},\mathbb{R}^m)}&\to&{\mathbb{R}^p}\\&{u(\cdot )} &\mapsto & {C(t)\int_{t_{0}}^{t} \Phi(t,\tau)B(\tau)u(\tau) \, d\tau +D(t)u(t)} \end{array}{}$$

Consider now $\delta_{(\sigma,\epsilon)}(\cdot)f_{j}\in PC(\mathbb{R},\mathbb{R}^m)$ where $\delta_{(\sigma,\epsilon)}(t)=\frac{1}{\epsilon}\mathbb{1}_{\sigma\leq t<\sigma+\epsilon}$ and $\{ f_{j} \}_{j=1}^m$ form a basis of $\mathbb{R}^m$. For $j=1,\dots,m$, then we have: $$s(t,t_{0},0,\delta_{(\sigma,\epsilon)}(\cdot )f_{j})=0$$for all $t<\sigma$. For $t \geq \sigma+\epsilon$,  $$\begin{align}s(t,t_{0},0,\delta_{(\sigma,\epsilon)}(\cdot )f_{j})&=\int_{\sigma}^{\sigma+\epsilon} \Phi(t,\tau)B(\tau) \frac{1}{\epsilon}f_{j} \, d\tau\\&=\frac{1}{\epsilon}\int_{\sigma}^{\sigma+\epsilon} \Phi(t,\sigma+\epsilon)\Phi(\sigma+\epsilon,\tau)B(\tau) f_{j} \, d\tau \\&=\frac{\Phi(t,\sigma+\epsilon)}{\epsilon}\int_{\sigma}^{\sigma+\epsilon} \Phi(\sigma+\epsilon,\tau)B(\tau) f_{j} \, d\tau\\&\approx \frac{\Phi(t,\sigma+\epsilon)}{\epsilon}[\Phi(\sigma+\epsilon,\sigma)B(\sigma)f_{j}] \epsilon\\&=\Phi(t,\sigma+\epsilon)\Phi(\sigma+\epsilon,\sigma)B(\sigma)f_{j} \\
\\&=\Phi(t,\sigma)B(\sigma)f_{j}\end{align}$$
Therefore, by taking $\varepsilon \to 0$, for $t\geq\sigma$, $$s(t,t_{0},0,\delta_{\sigma}(\cdot )f_{j})=\Phi(t,\sigma)B(\sigma)f_{j}=s(t,\sigma,B(\sigma)f_{j},0)$$
where $\delta_{\sigma}(\cdot)$ is known as the [[Dirac delta]]. By doing this on all basis vectors $f_{j}$, we have: $$K(t,\sigma):=\Phi(t,\sigma)B(\sigma)$$
for $t \geq\sigma$. Substituting this result into $\rho$, we get: $$\rho(t,t_{0},0,\delta_{\sigma}(\cdot )f_{j})=C(t)\Phi(t,\sigma)B(\sigma)f_{j}+D(t)\delta_{\sigma}(t)f_{j}$$Therefore, we have: $$H(t,\sigma)=C(t)\Phi(t,\sigma)B(\sigma)+D(t)\delta_{\sigma}(t)$$

---