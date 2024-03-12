#Series #Analysis 

##### Problem 2.2
1. Consider $u_{n}:[0,1]\to \mathbb{R},x\mapsto nx$. Then, $\|u_{n}\|_{A}=0$ for all $n\geq 1$. Therefore, it is not a norm.
2. The absolute homogeneity and triangle inequality follows from Minkowski inequality. For positive definiteness, assume $\|u\|_{B}=0$. Then, $$\int_{0}^{1} \left| u'(x) \right| ^{2} \, dx=0 $$Therefore, $u'=0$ and as $u(0)=0$, $u=0$. Conversely, if $u=0$, then $\|u\|_{B}=0$.
3. Analogous to 2.
4. Let for $u\in V$: $$\begin{array}{cccc} {S_{u}:}&{[0,1]\times[0,1]}&\to&{\mathbb{R}}\\&{(x,y)} &\mapsto & {\frac{u(x)-u(y)}{x-y}} \end{array}{}$$Then, from the continuity of $u$, $S_{u}$ is continuous. Therefore, $S_{u}\in L^2([0,1]^{2})$. Therefore, $\|u\|_{D}=\|S_{u}\|_{L^2}$ defines a norm.

Determining the inner space, we can use the parallelogram identity:
- For **B**, $$\begin{align}\|u+v\|_{B}^{2}+\|u-v\|_{B}^{2}&=\int_{0}^{1} \left| u'+v' \right| ^{2} \, dx+\int_{0}^{1} \left| u'-v' \right| ^{2} \, dx \\&=\int_{0}^{1} 2|u'|^{2}+2|v'|^{2} \, dx \\&=2(\|u\|_{B}^{2}+\|v\|_{B}^{2})\end{align}$$Therefore, it is an inner product space.
- For **C**, consider $u: x\mapsto x$ and $v: x\mapsto 2x$. Then, $$\begin{align}\|u+v\|^{2}_{C}+\|u-v\|^2_{C}&=\left( \int_{0}^{1} 3^3  \, dx  \right)^{2/3}+\left( \int_{0}^{1} 1  \, dx  \right)^{2/3}\\&=9+1\end{align}$$and we have: $\|u\|^{2}_{C}=1$ and $\|v\|^2_{C}=4$
- $$\begin{align}\|u+v\|_{B}^{2}+\|u-v\|_{B}^{2}&=\int_{0}^{1} \left| u'+v' \right| ^{2} \, dx+\int_{0}^{1} \left| u'-v' \right| ^{2} \, dx \\&=\int_{0}^{1} 2|u'|^{2}+2|v'|^{2} \, dx \\&=2(\|u\|_{B}^{2}+\|v\|_{B}^{2})\end{align}$$