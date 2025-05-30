#Series #Algorithms 

#### Exercise 2
Let $M\in \mathbb{R}^{d,d}$. Further, let $M=\sum_{i\in[d]}^{}\sigma_{i}u_{i}v_{i}^\top$ be its singular value decomposition. Then, $$\left\| M \right\| \|x\|^{2}-\braket{ x , Mx } =\sigma_{1}\|x\|^{2}-\sum_{i\in[d]}^{}\sigma_{i}\braket{ x , u_{i} } \braket{ x , v_{} } $$Now, as $\|x\|^2=\sum_{i\in[d]}^{}\braket{ x , u_{i} }^{2}$ we have that: $$\begin{aligned}-\braket{ x , Mx } &=\sum_{i\in[d]}^{}\left(-\sigma_{i}\braket{ x , u_{i} } \braket{ x , v_{i} } \right)\\&=\sum_{i\in [d]}^{}\sigma_{i} \left\langle x , \frac{u_{i} -v_{i}}{\sqrt{ 2 }}\right\rangle^{2}-\frac{\sigma_{i}\braket{ x , u_{i} } ^{2}}{2}-\frac{\sigma_{i}\braket{ x , v_{i} } ^{2}}{2}\end{aligned} $$Therefore, using that $\|x\|^2=\sum_{i\in[d]}^{}\braket{ x , u_{i} }^{2}=\sum_{i\in[d]}^{}\braket{ x , v_{i} }^{2}$, we have:$$\begin{aligned}\left\| M \right\| \|x\|^{2}-\braket{ x , Mx } &=\sum_{i\in[d]}\frac{\sigma_{1}-\sigma_{i}}{2}\braket{ x , u_{i} } ^{2}+\frac{\sigma_{1}-\sigma_{i}}{2}\braket{ x , v_{i} } ^{2}+\sigma_{i} \left\langle x , \frac{u_{i} -v_{i}}{\sqrt{ 2 }}\right\rangle^{2}\end{aligned}$$As $\sigma_{1}-\sigma_{i}\geq 0$ and $\sigma_{i}\geq 0$ for all $i\in[d]$, this is a degree-$2$ SOS proof for our statement.

---

