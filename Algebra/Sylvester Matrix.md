#Definition #Algebra 

> [!definition]
> Let $R$ be a [[ring]]. 
> 1. The ***Sylvester matrix*** of $f,g\in R[X]$ where $f(x)=\sum_{i=0}^{m}a_{i}x^i$ and $g(x)=\sum_{j=0}^{n}b_{j}x^j$ is given by: $$\text{Sylv}_{f,g}:=\begin{bmatrix}a_{m}&\cdots&\cdots&\cdots&a_{1}&a_{0}&0&\cdots&0\\0&a_{m}&\cdots&\cdots& \cdots&a_{1}&a_{0}&\ddots&\vdots\\\vdots&\ddots&\ddots&&&&\ddots&\ddots&0\\0&\cdots&0&a_{m}&\cdots&\cdots&\cdots&a_{1}&a_{0}\\ b_{n}&\cdots&\cdots&b_{1}&b_{0}&0&\cdots&\cdots&0\\0&b_{n}&\cdots& \cdots&b_{1}&b_{0}&\ddots&&\vdots\\\vdots&\ddots&\ddots&&&\ddots&\ddots&\ddots&0\\\vdots&&\ddots&\ddots&&&\ddots&\ddots&0\\0&\cdots&\cdots&0&b_{n}&\cdots&\cdots&b_{1}&b_{0}\end{bmatrix}\in \text{Mat}_{(m+n),(m+n)}(R)$$
- **Related definition**: The ***resultant*** of $f,g$ is $\text{Res}_{f,g}:=\det \text{Sylv}_{f,g}$.