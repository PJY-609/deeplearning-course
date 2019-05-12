### mini-batch gradient descent

$$
X=
\begin{bmatrix}
x^{(1)} & \cdots & x^{(k)}&|&x^{(i+1)} & \cdots & x^{(2k)}&|&\cdots&|&x^{(i)}&\cdots & x^{(m)}
\end{bmatrix}\\
$$

$$
Y=
\begin{bmatrix}
y^{(1)} & \cdots & y^{(k)}&|&y^{(i+1)} & \cdots & y^{(2k)}&|&\cdots&|&y^{(i)}&\cdots & y^{(m)}
\end{bmatrix}
$$

* mini-batches $t: X^{\{t\}}(n_x,mini-batch\ size),\ Y^{\{t\}}(1,mini-batch\ size)$

  $\underbrace{x^{(1)}  \cdots  x^{(k)}}_{X^{\{1\}}} \quad \cdots \quad \underbrace{x^{(i)}  \cdots  x^{(m)}}_{X^{\{j\}}}​$

  $\underbrace{y^{(1)}  \cdots  y^{(k)}}_{Y^{\{1\}}} \quad \cdots \quad \underbrace{y^{(i)}  \cdots  y^{(m)}}_{Y^{\{j\}}}$

* do not need to wait till the whole giant vector finish computing

* **epoch**: one pass through the deep network

***

### Training with mini-batch gradient descent

<img src='images\1.png'>

***

### Choosing the mini-batch size

* If minibatch size = m : Batch gradient descent

  * take low-noise and large steps
  * too long per iteration

* If minibatch size = 1 : Stochastic gradient decent

  * oscillating around the optimal point
  * lose speedup from vectorization

* In practice: between 1 and m

* Small training set: use batch gradient descent

* typical mini-batch size: **64, 128, 256, 512, ...**

  * try several values to see if it optimizes the model

* make sure minibatch size fit in CPU\GPU memory

  