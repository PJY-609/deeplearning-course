### Gradient decsent momentum

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/2%E3%80%81Improving%20Deep%20Neural%20Networks%EF%BC%9AHyperparameter%20tuning%2C%20Regularization%20and%20Optimization/Week2/Lesson1/images/5.PNG'>

* in horizontal direction, we want the learning go fast
* in vertical direction, we want the learning go slow, not oscillating too much, thus slow down the whole learning process

***

### <a name='momentum'>Momentum</a>

$v_{dw}=0,\ v_{db}=0$

$On\ iteration\ t:$

​	$compute\ dW,\ db\ on\ mini-batch​$

​	$v_{dW}=\beta v_{dW}+(1-\beta)dW​$

​	$v_{db}=\beta v_{db}+(1-\beta)db​$

​	$W:=W-\alpha v_{dW}​$

​	$b:=b-\alpha v_{db}​$

$Hyperparameters: \alpha,\ \beta​$

$\beta=0.9$

* *Analogy:*

  * assume a ball-shaped cost function where we roll down to the minimum

  * $dW, db​$ are acceleration

  * $v_{dW},v_{db}​$ are velocity

***

### <a name='rmsprop'>RMSprop</a>

$On\ iteration\ t:$

​	$Compute\ dW,db\ on\ mini-batch$

​	$s_{dW}=\beta s_{dW}+(1-\beta)dW^2$ **element-wise square calculation**

​	$s_{db}=\beta s_{db}+(1-\beta)db^2$

​	$W:=W-\alpha \frac{dW}{\sqrt{s_{dW}}+\epsilon}$ **add a small number to avoid divide by zero**

​	$b:=b-\alpha \frac{db}{\sqrt{s_{db}}+\epsilon}$

***

### <a name='adam'>Adam optimization algorithm</a>

$v_{dW}=0,s_{dW}=0,v_{db}=0,s_{db}=0$

$On\ iteration\ t:$

​	$compute\ dW, db\ using\  current\ mini-batch$

​	$v_{dW}=\beta_1v_{dW}+(1-\beta_1)dW,\ v_{db}=\beta_1v_{db}+(1-\beta_1)db \gets \ 'mementum'$

​	$s_{dW}=\beta_2s_{dW}+(1-\beta_2)dW^2,\ s_{db}=\beta_2s_{db}+(1-\beta_2)db \gets\ 'RMSprop'$

​	$v_{dW}^{correct}=\frac{v_{dW}}{(1-\beta_1^t)},\ v_{db}^{correct}=\frac{v_{db}}{(1-\beta_1^t)}$

​	$s_{dW}^{correct}=\frac{s_{dW}}{(1-\beta_2^t)},\ s_{db}^{correct}=\frac{s_{db}}{(1-\beta_2^t)}$	

​	$W:=W-\alpha \frac{v_{dW}^{correct}}{\sqrt{s_{dW}^{correct}}+\epsilon}$

​	$b:=b-\alpha \frac{v_{db}^{correct}}{\sqrt{s_{db}^{correct}}+\epsilon}$

$Hyperparameters\ choice:$

​	$\alpha:\ needs\ to\ be\ tuned$

​	$\beta_1:0.9$

​	$\beta_2=0.999$

​	$\epsilon:10^{-8}$

$Adam:\ adaptive\ moment\ estimation$

