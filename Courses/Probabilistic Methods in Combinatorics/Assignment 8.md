#Series #ProbabilisticMethods 

##### Problem 1
Color each cell independently randomly and uniformly. Let $S$ be a sequence of operations of row/column color switches. Notice that:
1. the order of the switch does not matter. 
1. if we switch the same row/column twice, we return back to the same.

Therefore, we may wlog consider $S\in\{ 0,1 \}^{2n}$ where $S_{i}=1$ if and only if $i$-th row/column is switched. Let $X_{1},\dots,X_{n^{2}}\in \{ +1,-1 \}$ where $X_{i}=1$ if and only if $i$-th cell is red in the initial configuration. Now, $Y^S_{i}\in \{ +1,-1 \}$ depending on the outcome after $X_{i}$. Let $Y^S:=\sum_{i}^{}Y^S_{i}$. Then, for a fixed $S$, $$\mathbb{P}\left( \text{\#red cells }> \frac{n^{2}}{2}+\sqrt{ \frac{\ln 2}{n} }n^2 \right)=\mathbb{P}\left( Y^S> 2\sqrt{ \frac{\ln 2}{n} }n^{2} \right)< \exp \left( -2 n\ln 2 \right) =2^{-2n}$$Hence, $$\mathbb{P}\left( \exists S:\#\text{red cells}>\frac{n^{2}}{2}+\sqrt{ \frac{\ln 2}{n} }n^2  \right) <1$$


---
##### Problem 2
We have that:
1. 