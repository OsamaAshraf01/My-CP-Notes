#optimization
$$
\begin{align}
f(x) &= \min_{i=1}^{k} (x_i) + \max_{i=1}^{k}(x_i) \\
&= \min_{j=1}^{k} [x_j + \max_{i=1}^{k}(x_i)]
\end{align}
$$
this trick eases the minimization of $f(x)$
this allows you to develop an algorithm that minimizes $x_i$ for fixed $x_j$. After that, you run this algorithm $j$ times for each $x_j$ and minimize the value of each time to find the answer.