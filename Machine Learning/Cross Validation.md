#Definition #ML 
> [!definition]
> Let $X=\{ x_{1},\dots,x_{n} \}$ denote the dataset.
> 1. The ***cross validation method*** is splitting $X=X_{\text{test}}\sqcup X_{\text{train}}$ such that the model is trained on $X_{\text{train}}$ and evaluated on $X_{\text{test}}$ where the performance on the test set is used as a proxy for the generalization error and model selection is carried out using this measure.
> 2. The ***$k$-fold cross validation method*** is splitting $X=\bigsqcup_{i\in[k]}^{}X_{i}$ of similar sizes s.t. at round $i\in[k]$, the model is trained on $\bigcup_{j\neq i}^{} X_{j}$ and evaluated on $X_{i}$. 

^dcaf90

- **Remark**: $k$ is typical between 3 and 10.
- **Related definition**: When $k=n$, it is called ***leave-one-out cross validation (LOOCV)***.
---
