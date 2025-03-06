##### DAGS
```tikz
\usepackage{tikz}
\usetikzlibrary{arrows}

\begin{document}

\begin{tikzpicture}

\tikzset{vertex/.style = {shape=circle,draw,minimum size=1.5em}}
\tikzset{edge/.style = {->,> = latex'}}
% vertices
\node[vertex] (a) at  (4,2) {$w$};
\node[vertex] (b) at  (0,0) {$y_1$};
\node[vertex] (b1) at (1.5,0) {$y_2$};
\node[vertex] (b2) at (3,0) {$y_3$};
\node[vertex] (c) at  (8,0) {$y_n$};


%edges
\draw[edge] (a) to (b);
\draw[edge] (a) to (b1);
\draw[edge] (a) to (b2);
\draw[edge] (a) to (c);

\path (b2) to node {\dots} (c);

\end{tikzpicture}
\end{document} 
```

> ```tikz
>\usepackage{tikz}
>\usetikzlibrary{arrows}
>\usetikzlibrary{fit}
>
>\begin{document}
>
>\begin{tikzpicture}
>
>\tikzset{vertex/.style = {shape=circle,draw,minimum size=1.5em}}
>\tikzset{dot/.style = {minimum size=1.5em}}
>\tikzset{edge/.style = {->,> = latex'}}
>% vertices
>\node[vertex] (a) at  (4,2) {$w$};
>\node[vertex] (b) at  (0,0) {$y_1$};
>\node[vertex] (b1) at (1.5,0) {$y_2$};
>\node[vertex] (b2) at (3,0) {$y_3$};
>\node[vertex] (c) at  (8,0) {$y_n$};
>
>\node[dot] (d) at (2,2) {$\sigma_p^2$};
>\node[dot] (d1) at (0,1.5) {$\sigma_n^2$};
>\node[dot] (x1) at (0,-1.5) {$x_1$};
>\node[dot] (x2) at (1.5,-1.5) {$x_2$};
>\node[dot] (x3) at (3,-1.5) {$x_3$};
>\node[dot] (x) at (8,-1.5) {$x_n$};
>
>\node[vertex] (aa) at  (13,2) {$w$};
>\node[vertex] (ba) at  (13,0) {$y_i$};
>
>\node[dot] (da) at (11,2) {$\sigma_p^2$};
>\node[dot] (d1a) at (11,0) {$\sigma_n^2$};
>\node[dot] (x1a) at (13,-1.5) {$x_i$};
>\node[dot] (ta) at (14.05,-1.6) {$\footnotesize{i\in[n]}$};
>
>
>%edges
>\draw[edge] (a) to (b);
>\draw[edge] (a) to (b1);
>\draw[edge] (a) to (b2);
>\draw[edge] (a) to (c);
>\draw[edge] (d) to (a);
>\draw[edge] (d1) to (b);
>\draw[edge] (d1) to (b1);
>\draw[edge] (d1) to (b2);
>\draw[edge] (d1) to (c);
>\draw[edge] (x1) to (b);
>\draw[edge] (x2) to (b1);
>\draw[edge] (x3) to (b2);
>\draw[edge] (x) to (c);
>\draw[edge] (aa) to (ba);
>\draw[edge] (da) to (aa);
>\draw[edge] (d1a) to (ba);
>\draw[edge] (x1a) to (ba);
> \node[draw,dotted,fit=(ba)(x1a)] {};
>
>
>\path (b2) to node {\dots} (c);
>\path (x3) to node {\dots} (x);
>
>\end{tikzpicture}
>\end{document} 
>```

```tikz
>    \usepackage{tikz}
>    \usetikzlibrary{decorations.markings}
>    \newcommand{\midarrow}{\tikz \draw[-triangle 90] (0,0) -- +(.1,0);}
>    \begin{document}
>    \begin{tikzpicture}
>    \begin{scope}[very thick,decoration={markings,mark=at position 0.55 with {\arrow{>}}}] 
>    \draw[postaction={decorate}] (0,-1)--(1.73,0);
>    \draw[postaction={decorate}] (1.73,0)--(0,1);
>    \draw[postaction={decorate}] (0,-1)--(0,1);
>    \end{scope}
>    
>    \tikzset{edge/.style = {->,> = latex'}}
>    \path[draw, ultra thick] (0,1) node[anchor=east]{$e_{2}$}
>    --node[left]{$f*g$} (0,-1)  node[anchor=east] {$e_{0}$}
>    --node[below right]{$f$} (1.73,0) node[anchor=west]{$e_{1}$}
>    --node[above right]{$g$} cycle;
>    \path[clip] (0,1) -- (0,-1) -- (1.73,0) -- cycle; 
>    \foreach \y in{-1,-0.9,...,1}
> 	   \draw (0,\y) -- (10,\y);
>    
>    \node (a) at  (0,1) {};
>    \node (b) at  (0,-1) {};
>    \node (c) at  (1.73,0) {};
>    
>    
>    \end{tikzpicture}
>    \end{document} 
```




##### Hihi




```tikz 
\usepackage{tikz-cd} \begin{document} \begin{tikzcd}     
T \arrow[drr, bend left, "x"]     \arrow[ddr, bend right, "y"]     \arrow[dr, dotted, "{(x,y)}" description] & & \\     K & X \times_Z Y \arrow[r, "p"] \arrow[d, "q"]     & X \arrow[d, "f"] \\     & Y \arrow[r, "g"]     & Z \end{tikzcd}\end{document}
```

```tikz
>  \usepackage{tikz-cd}\begin{document}\begin{tikzcd} [column sep=tiny]
>  &&& 0 \\ 0 & {H_{n+1}(K^{(n+1)})} & {H_{n+1}(K^{(n+1)},K^{(n)})} & {H_n(K^{(n)})} & {H_n(K^{(n+1)})} & 0 \\ &&& {H_n(K^{(n)},K^{(n-1)})} \\ && 0 & {H_{n-1}(K^{(n-1)})} & {H_{n-1}(K^{(n-1)},K^{(n-2)})} & {H_{n-2}(K^{(n-2)})} \\ &&& {H_{n-1}(K^{(n)})} \\ &&& 0 \arrow[from=1-4, to=2-4] \arrow[from=2-1, to=2-2] \arrow[from=2-2, to=2-3] \arrow["{\partial_{n+1}}", from=2-3, to=2-4] \arrow["{\beta_{n+1}}", color={rgb,255:red,127;green,10;blue,199}, from=2-3, to=3-4] \arrow[from=2-4, to=2-5] \arrow["{j_n}", from=2-4, to=3-4] \arrow[from=2-5, to=2-6] \arrow["{\partial_n}", from=3-4, to=4-4] \arrow["{\beta_n}", color={rgb,255:red,127;green,10;blue,199}, from=3-4, to=4-5] \arrow[from=4-3, to=4-4] \arrow["{j_{n-1}}", from=4-4, to=4-5] \arrow[from=4-4, to=5-4] \arrow[from=4-5, to=4-6] \arrow[from=5-4, to=6-4]\end{tikzcd}
>  \end{document} 
>  ```

```tikz
\usepackage{tikz}
\usetikzlibrary{arrows}
\begin{document}

\begin{tikzpicture}[shorten >=1pt,->]
  \tikzstyle{vertex}=[circle,fill=black,minimum size=6pt,inner sep=2pt]
  \node[vertex] (G_1) at (-0.5,-0) {};
  \node[vertex] (G_2) at (0.5,-0)   {};
  \node[vertex] (G_3) at (-1.2,-0.8)  {};
  \node[vertex] (G_4) at (1.2,-0.8)  {};
  \node[vertex] (G_5) at (-0.9,-1.67)  {};
  \node[vertex] (G_6) at (0.9,-1.7)  {};
  \node[vertex] (G_7) at (0,-2.2)  {};
  \draw (G_5)--(G_1) -- (G_6) -- cycle;
  \draw (G_5)--(G_2) -- (G_6) -- cycle;
  \draw (G_5)--(G_3) -- (G_6) -- cycle;
  \draw (G_5)--(G_4) -- (G_6) -- cycle;
  \draw (G_5)--(G_5) -- (G_6) -- cycle;
  \draw (G_5)--(G_7) -- (G_6) -- cycle;
  \draw (G_7)--(G_1) -- cycle;
  \draw (G_7)--(G_2) -- cycle;
  \draw (G_7)--(G_3) -- cycle;
  \draw (G_7)--(G_4) -- cycle;
  \draw (G_3)--(G_4) -- cycle;
  
\end{tikzpicture}
\end{document} 
```