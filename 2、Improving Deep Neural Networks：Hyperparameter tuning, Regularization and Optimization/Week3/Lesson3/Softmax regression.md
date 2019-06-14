### Softmax regression

$C=\#classes,\ n^{[L]}=C,\ \hat y\ is\ (C, 1)$

$\hat y \to \begin{cases} P(class1|x)\\P(class2|x)\\\cdots\\P(classC|x)  \end{cases}$

$z^{[L]}=W^{[L]}a^{[L-1]}+b^{[L]}$

$Activation\ function: g^{[L]}(z^{[L]})$

​	$t=e^{(z^{[L]})}​$

​	$a^{[L]}=\frac{e^{z^{[L]}}}{\sum_it_i},\ a^{[L]}_i=\frac{t_i}{\sum_it_i}​$

$a^{[L]}=g^{[L]}(z^{[L]}),\ a^{[L]}\ and\ z^{[L]}\ are\ (C, 1)$

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/2%E3%80%81Improving%20Deep%20Neural%20Networks%EF%BC%9AHyperparameter%20tuning%2C%20Regularization%20and%20Optimization/Week3/Lesson3/images/1.PNG' width='80%'>

***

### training a softmax classifier

* **loss function**

  $\mathscr{L}(\hat y,y)=-\sum_{j=1}^{C}y_jlog(\hat y_j)$

  it looks at wherever the ground true class in the training set is, and tries to make the corresponding probabilities as high as possible

* $\mathscr{J} (W^{[1]},b^{[1]},\cdots)=\frac{1}{m}\sum_i \mathscr{L}(\hat y^{(i)},y^{(i)})​$

* $Y=\begin{bmatrix} y^{(i)}&\cdots&y^{(m)}  \end{bmatrix},\ Y\in\mathbb{R}^{(C,m)}$
* $\hat Y=\begin{bmatrix} \hat y^{(i)}&\cdots&\hat y^{(m)}  \end{bmatrix},\ \hat Y\in\mathbb{R}^{(C,m)}$

* **Backprop**

  * $\frac{\partial \mathscr{J}}{\partial z^{[L]}}=dz^{[L]}=\hat y-y,\ dz^{[L]}\in \mathbb{R}^{(C,1)}$

