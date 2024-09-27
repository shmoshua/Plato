#Definition #ProbabilityTheory 

> [!definition]
> For a [[probability space]] $(\Omega,\mathcal{A},\mathbb{P})$ and an event $B\in \mathcal{A}$ with $\mathbb{P}(B)>0$, 
> 1. the ***conditional probability*** given $B$ is a new probability measure: $$\mathbb{P}(A|B):=\frac{\mathbb{P}(A\cap B)}{\mathbb{P}(B)}$$
> 2. for a [[random variable]] $X\in L^1(\Omega,\mathcal{A},\mathbb{P})$, the ***conditional expectation*** of $X$ given $B$ is: $$\mathbb{E}[X|B]:=\frac{\mathbb{E}[X\cdot \mathbb{1}_{B}]}{\mathbb{P}(B)}$$which is also the [[Expected Value|expectation]] over $\mathbb{P}(\cdot|B)$.
> 3. for a random variable $X\in L^1$ and a random variable $Y:\Omega\to E$, the ***conditional expectation*** of $X$ given $Y$ is a *real random variable* $\mathbb{E}[X|Y]:\Omega\to \mathbb{R}$ with $\mathbb{E}[X|Y]=\varphi(Y)$ where: $$\varphi: E\to \mathbb{R},\quad y\mapsto \begin{cases}\mathbb{E}[X|Y=y]& \text{if }\mathbb{P}(Y=y)>0\\0&\text{otherwise}\end{cases}$$
- **Remark**: the $\varphi(y)$ value when $\mathbb{P}(Y=y)=0$ is irrelevant as $$\mathbb{P}(Y\in \{ y\in E:\mathbb{P}(Y=y)=0 \})=\sum_{n=1}^{}$$