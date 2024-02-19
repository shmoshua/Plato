#Series #FunctionalAnalysis 

##### Problem 1
Let $C_{b}(\mathbb{R})\subseteq L^\infty(\mathbb{R})$ and consider the linear functional:$$\begin{array}{cccc} {\lambda:}&{C_{b}(\mathbb{R})}&\to&{\mathbb{R}}\\&{f} &\mapsto & {f(0)} \end{array}{}$$We will define the following gauge on $L^\infty(\mathbb{R})$: $$\begin{array}{cccc} {p:}&{L^\infty(\mathbb{R})}&\to&{\mathbb{R}}\\&{f} &\mapsto & {\|f\|_{\infty}} \end{array}{}$$Then, let $\Lambda\in L^\infty(\mathbb{R})^{*}$ be the Hahn-Banach extension of $\lambda$. 

---
##### Problem 2
Let $\{ e_{n} \}_{n}$ be the countable dense subset of $E$. We will show that $\{ \|\cdot\|_{e_{n}} \}_{n}$ is a sufficient family or seminorms on $B_{\leq 1}^{E^{*}}(0)$. 

Let $f\in B_{\leq 1}^{E^{*}}(0)$ with $f\neq 0$. Then, there exists $x\in E$ s.t. $f(x)\neq 0$. Assume however that $\|f\|_{e_{n}}=\left| f(e_{n}) \right|=0$ for all $n$. As $\{ e_{n} \}_{n}$ is dense, there exists $\{ e_{n_{k}} \}_{k}$ s.t. $e_{n_{k}}\to x$.  Therefore, $$f(x)=\lim_{ k \to \infty } f(e_{n_{k}})=0$$This is a contradiction and there exists $e_{n}$ s.t. $\|f\|_{e_{n}}\neq 0$. Therefore, $\{ \|\cdot\|_{e_{n}} \}_{n}$ is sufficient and $B_{\leq 1}^{E^{*}}(0)$ is metrizable.

---
##### Problem 4
We will show that $c_{0}(\mathbb{N})^{*}=\ell^1(\mathbb{N})$. We define the following map: $$\begin{array}{cccc} {R:}&{\ell^1(\mathbb{N})}&\to&{c_{0}(\mathbb{N})^{*}}\\&{y} &\mapsto & {f_{y}:x\mapsto \sum_{n=1}^{\infty}x_{n}y_{n}} \end{array}{}$$which is injective by definition. Then, 
1. **$R$ is well-defined**:
   For every $y\in \ell^1(\mathbb{N})$ and $x\in c_{0}(\mathbb{N})$:$$\left| f_{y}(x) \right| \leq \sum_{n=1}^{\infty}\left| x_{n} \right| \left| y_{n} \right| \leq \|x\|_{b}\sum_{n=1}^{\infty}\left| y_{n} \right| =\|x\|_{b}\cdot \|y\|_{1} $$Therefore, $f_{y}\in c_{0}(\mathbb{N})^{*}$
2. **$R$ is surjective**:
   Let $f\in c_{0}(\mathbb{N})^{*}$. Then, we define $y_{n}:=f(\chi_{\{ n \}})$. Then, 
   $$f(x)=\lim_{ n \to \infty } f(x\cdot \chi_{[n]})=\lim_{ n \to \infty }\sum_{i=1}^{n}x_{i}y_{i}=\sum_{n=1}^{\infty}x_{n}y_{n} $$
   We just need to show that $y\in \ell^1(\mathbb{N})$. Let's define: $$x^N_{n}:=\begin{cases}\text{sgn}(y_{n})&n\leq N\\0&n>N\end{cases}$$Then, $x^N\in c_{0}(\mathbb{N})$ and $$f(x^N)=f\left( \sum_{n=1}^{N}x^N_{n}\chi_{\{ n \}} \right)=\sum_{n=1}^{N}\text{sgn}(y_{n})y_{n}=\sum_{n=1}^{N}\left| y_{n} \right| $$and $\left| f(x^N) \right|\leq \left\| f \right\|$. Therefore, $y\in \ell^1(\mathbb{N})$.
---
##### Problem 5
Let $$V:=\{ g\in \ell^\infty(\mathbb{N}):\lim_{ n \to \infty } \lambda_{n}(g)<+\infty \}$$Then, with $\lambda:V\to \mathbb{R}$ defined as $\lambda(g):=\lim_{ n \to \infty }\lambda_{n}(g)$. Therefore, by Hahn-Banach, there is a linear functional $\Lambda: \ell^\infty(\mathbb{N})\to \mathbb{R}$ s.t.
1. $\Lambda(g)=\lim_{ n \to \infty }\lambda_{n}(g)$ for $g\in V$ and
2. $\Lambda(g)\leq\|g\|_{b}$
   
Therefore, $\Lambda$ is continuous.

---