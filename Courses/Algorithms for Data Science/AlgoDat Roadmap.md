#Roadmap #Algorithms 

### 1. Least Squares and Regression

![[Linear Regression#^e4d197]]

---
> [!lemma] Proposition 1
> For the least squares solution $w^{*}$ we have that: $$\mathbb{E}[\|w_{0}-w^{*}\|^{2}]=\sigma^{2} \cdot  \frac{d}{n}$$

> [!proof]+
> Let $X=[x_{1}|\dots|x_{n}]^\top\in \mathbb{R}^{n,d}$. By orthogonalizing the data and scaling, we may assume that $\frac{1}{n}X^\top X=I_{d}$. Then,
> 
> Notice that: $$\nabla_{w }\|Xw-y\|^{2}=2X^\top(Xw-y)=2nw-2X^\top y$$Hence, from the optimality of $w^{*}$, we get that $nw^{*}=X^\top y$ and: $$w^{*}-w_{0}=\frac{1}{n}X^\top y-$$
> 
 $$\begin{align} \mathbb{E}[\left\| w^{*}-w_{0} \right\| ^{2}]=\end{align}$$