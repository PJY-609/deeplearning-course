### Normalizing training set

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/2%E3%80%81Improving%20Deep%20Neural%20Networks%EF%BC%9AHyperparameter%20tuning%2C%20Regularization%20and%20Optimization/Week1/Lesson3/images/4.PNG'>

* $Subtract\ mean:$
  * $\mu=\frac{1}{m}\sum^m_{i=1}x^{(i)}​$
  * $x:=x-\mu$
  * <img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/2%E3%80%81Improving%20Deep%20Neural%20Networks%EF%BC%9AHyperparameter%20tuning%2C%20Regularization%20and%20Optimization/Week1/Lesson3/images/5.PNG'>
* $Normalize\ variance:$
  * $\sigma^2=\frac{1}{m}\sum^m_{i=1}x^{(i)}\underbrace{**}_{elementwise\ power}2​$
  * $x/=\sigma^2$
  * <img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/2%E3%80%81Improving%20Deep%20Neural%20Networks%EF%BC%9AHyperparameter%20tuning%2C%20Regularization%20and%20Optimization/Week1/Lesson3/images/6.PNG'>

* ==**use the same $\mu$ and $\sigma^2$ to test and dev set**==
  * want the data in dev and test set go through the same transformation

***

### Why normalize inputs?

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/2%E3%80%81Improving%20Deep%20Neural%20Networks%EF%BC%9AHyperparameter%20tuning%2C%20Regularization%20and%20Optimization/Week1/Lesson3/images/7.PNG' style='zoom:30'>

