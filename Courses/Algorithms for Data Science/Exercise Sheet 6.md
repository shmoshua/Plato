#Series #Algorithms 
#### Problem 1
1. We have that: $$\braket{ \widehat{x} , x^{*} } =\sum_{i\in[n]}^{} \widehat{x}_{i}x^{*}_{i}=N_{\geq }+(-1)N_{\leq}=N_{\geq} - N_{\leq}$$This shows the statement.
2. We have that: $$\left\| X-X^{*} \right\| _{F}^{2}=\left\| X \right\| ^{2}_{F}-2\braket{ X , X^{*} } +\left\| X^{*} \right\| _{F}^{2}$$
	$$\left\| xx^\top \right\|^{2}_{F}=\sum_{i,j}^{}x_{i}^2x_{j}^{2}=\|x\|^4 $$$$\left\| X^{*} \right\| ^{2}_{F}=\left\| x^{*} \right\| ^4=n^2$$

3. We have: $$\braket{ \widehat{X} , X^{*} } =(N_{\geq }-N_{\leq})^{2}=N_{\geq }^{2}-2N_{\geq }N_{\leq} + N_{\leq }^{2}$$
4. $$\braket{ X , X^{*} } =\sum_{i,j}^{}x_{i}x_{j}x^{*}_{i}x^{*}_{j}=\left( \sum_{i}^{}x_{i}x_{i}^{*} \right) ^{2}=\braket{ x , x^{*} } ^{2}$$
5. We have that: $$\widehat{X}_{ij}=\widehat{x}_{i}\widehat{x}_{j}=\frac{x_{i}}{\left| x_{i} \right| }\cdot \frac{x_{j}}{\left| x_{j} \right| }$$
6. $$\left\| X- X^{*}\right\|^{2}_{F}=\sum_{i,j\in [n]}^{}(x_{i}x_{j}-x^{*}_{i}x^{*}_{j}) ^{2}=\sum_{i,j\in [n]}^{}(\left| x_{i}x_{j} \right| \widehat{x}_{i}\widehat{x}_{j}-x^{*}_{i}x^{*}_{j}) ^{2}$$$$\braket{ \widehat{X} , X^{*} } =\sum_{i,j}^{}\widehat{x}_{i}\widehat{x}_{j}x^{*}_{i}x^{*}_{j}=\sum_{i,j}^{}\frac{x_{i}}{\left| x_{i} \right| }\frac{x_{j}}{\left| x_{j} \right| }x^{*}_{i}x^{*}_{j}\geq$$

$x_{i}^{2}x_{j}^{2}-2x_{i}$

If $\widehat{x}_{i}x^{*}_{i}=\frac{x_{i}x^{*}_{i}}{\left| x_{i} \right|}=1$, then $x_{i}x^{*}_{i}=\left| x_{i} \right|$ and $$\sum_{i,j}^{}(x_{i}^{2}x_{j}^{2}-2x_{i}x_{i}^{*}x_{j}x_{j}^{*}+x^{*}_{i}x)$$ $$\left\| X-X^{*} \right\| ^{2}_{F}=\left\| X \right\| ^{2}_{F}-2\braket{ X , X^{*} } +n^{2}$$We have: $$\braket{ X , X^{*} } =\left( \sum_{i\in[n]}^{}x_{i}x^{*}_{i} \right)^{2}= $$
$$\sum_{i\in [n]}x_{i}x^{*}_{i}=\sum_{i\in S_{\geq }}^{}\left| x_{i} \right| -\sum_{i\in S_{\leq }}^{}\left| x_{i} \right| \leq n \|x\|^{2}$$

If $\widehat{x}_{i}x^{*}_{i}=1$, then $\text{sgn}(x_{i})=\text{sgn}(x^{*}_{i})$ and $\left| x_{i} \right|=x_{i}x^{*}_{i}$. 

We have: $$4N_{\geq}N_{\leq}=n^2-(N_{\geq }-N_{\leq})^{2}=n^2-\braket{ \widehat{X} , X^{*} }\leq 2\left\| X-X^{*} \right\| ^{2}_{F} $$We have: $$N_{\geq }=\sum_{n=1}^{}$$



1. Let $\left\| X-X^{*} \right\|_{F}\leq 0.1n$. Then, $2N_{\geq}N_{\leq}\leq 0.01n^{2}$. Hence, $$\braket{ \widehat{x} , x^{*} } ^{2}=(N_{\geq }-N_{\leq})^{2}=(N_{\geq}+N_{\leq})^{2}-4N_{\geq}N_{\leq}\geq n^{2}-0.02n^{2}=0.98n^{2}$$

---
We have: $$\left\| X-X^{*} \right\| ^{2}_{F}=\sum_{i,j\in[n]}^{}(x^{2}_{i}x^{2}_{j}-2x_{i}x^{*}_{i}x_{j}x^{*}_{j}+1)$$
Let
$$\braket{ X , X^{*} } =\left( \sum_{i}^{}x_{i}x^{*}_{i} \right)^{2}=\left( \sum_{i\in S_{\geq }}^{}\left| x_{i} \right| -\sum_{i\in S_{\leq}}^{}\left| x_{i} \right|  \right) ^{2}$$