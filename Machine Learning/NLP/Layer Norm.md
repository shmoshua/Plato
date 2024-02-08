#Definition #NLP #ML 

> [!definition]
> Let $x\in \mathbb{R}^{d_{X}}$ be a neural network activations/outputs. Then, the ***layer norm*** of $x$ with $\gamma,\beta\in \mathbb{R}^{d_{X}}$ refers to: $$\textsf{LayerNorm}(x|\gamma,\beta)=\text{diag}(\gamma)\cdot \frac{x-\mu(x)\cdot 1}{ \sigma(x)}+\beta$$
> where $\mu(x)=\frac{1}{d_{X}}\sum_{i=1}^{d_{X}}x_{i}$ and $\sigma(x)=\sqrt{ \frac{1}{d_{X}}\sum_{i=1}^{d_{X}}(x_{i}-\mu(x))^{2} }$.
---

