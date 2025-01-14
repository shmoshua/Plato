#Definition #PAI 

> [!definition]
> A ***$L$-layer neural network*** is a function $f_{\theta}:\mathbb{R}^d\to \mathbb{R}^k$ given by: $$f_{\theta}(x):=\varphi_{L}(W_{L}\cdot \varphi_{L-1}(W_{L-1}\cdot \dots \varphi_{1}(W_{1}x)))$$where $\varphi_{1}:$