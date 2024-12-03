#Series #ProbabilisticMethods 


##### Problem 1
Let $B$ be a uniform random permutation of the rows of $A$. Let $k:=\left\lceil c\sqrt{ n }\right\rceil$ and let $X_{j,i_{1},\dots,i_{k}}$ denote the event that $B_{i_{1},j}<\dots.<B_{i_{k},j}$. Then, $$\mathbb{P}(X_{j,i_{1},\dots,i_{k}})=\frac{1}{k!}$$and $$\mathbb{P}(\exists j\text{ with increasing subsequence in }B_{:,j})\leq n{n \choose k} \frac{1}{k!}$$where: $$n{n \choose k} \frac{1}{k!}\leq \frac{n^{k+1}}{(k!)^2}\leq \frac{n}{2\pi k}\left( \frac{en}{k^2} \right) ^k\leq \frac{\sqrt{ n }}{2\pi c}\left( \frac{e}{c^2} \right) ^{k}<1$$ for $c$ large enough. This proves the statement.