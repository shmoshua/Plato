#Series #Algorithms 

#### Problem 1.1
Let $u:= \widehat{\beta}-\beta ^{*}$. Then, similarly to the Theorem 1, $$\frac{1}{2}\left\| Xu \right\| ^2_{2}\leq \braket{ u , X^\top \varepsilon } \leq \|u\|_{1}\left\| X^\top\varepsilon \right\| _{\infty}$$However, notice that $\|u\|_{1}\leq\|\widehat{w}\|_{1}+\|w_{0}\|_{1}\leq 2\|w_{0}\|_{1}$ and: $$\mathbb{E}[\left\| X^\top\varepsilon \right\| _{\infty}]\leq \sqrt{ n }\cdot O(\log 2d)^{1/2}$$Therefore, $$\frac{1}{n}\mathbb{E}[\left\| X(\widehat{w}-w_{0}) \right\| ^{2}_{2}]\leq \frac{\left\| w_{0} \right\| _{1}}{\sqrt{ n }}O(\log 2d)^{1/2}$$
