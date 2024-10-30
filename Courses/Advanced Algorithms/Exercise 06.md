#Series #Algorithms 

##### Problem 1
```pseudo
\begin{algorithm} \caption{Repeat} 
\begin{algorithmic}
\For{$i\in[k]$}
\State $Y_i\gets\mathcal{A}$
\EndFor
\Return $\overline{Y}:=\frac{1}{k}\sum_{i=1}^k Y_i$
\end{algorithmic}
\end{algorithm}
```

We have that: $$\mathbb{P}\left(\left| \overline{Y}-x \right|>\ell x \right)\leq \frac{\text{Var}(\overline{Y})}{\ell^{2}x^{2}}\leq\frac{10^6}{k\ell^{2}}$$Hence, for $\ell=10^{-3}$ and $k=10^{14}$, we have that: $$\mathbb{P}(\left| \overline{Y}-x \right| >0.001x)\leq 10^{-2}$$

---