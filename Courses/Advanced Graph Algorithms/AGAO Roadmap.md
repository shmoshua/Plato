#Roadmap #Algorithms 

$f:S\subseteq \mathbb{R}^n\to \mathbb{R}$ is ***twice differentiable*** at $x\in S$ if there exists $M\in \text{Mat}_{n,n}(\mathbb{R})$ s.t. $$f(x+\delta)=f(x)+(\nabla_{x}f)^\top \delta+\frac{1}{2}\delta^\top M\delta+o(\left\| \delta \right\| ^{2}_{2}),\quad \forall\delta\in \mathbb{R}^n$$
Then, there exists a symmetric matrix $M$ s.t. the property above holds. If $M$ is not symmetric, we can replace it by $(M+M^\top) / 2$.