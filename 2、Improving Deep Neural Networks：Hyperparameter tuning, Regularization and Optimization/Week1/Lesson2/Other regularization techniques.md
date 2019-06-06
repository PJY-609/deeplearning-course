

## Other regularization techniques

#### Data augmentation

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/2%E3%80%81Improving%20Deep%20Neural%20Networks%EF%BC%9AHyperparameter%20tuning%2C%20Regularization%20and%20Optimization/Week1/Lesson2/images/2.PNG' style="zoom:30">

***

#### Early stopping

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/2%E3%80%81Improving%20Deep%20Neural%20Networks%EF%BC%9AHyperparameter%20tuning%2C%20Regularization%20and%20Optimization/Week1/Lesson2/images/3.PNG' width='80%'>

> - $at\ first\ w \approx 0$
> - $at\ last\ w\ tends\ to\ large$ 
> - $mid-term\ mid-dize\ \|w\|^2_F​$
> - thus avoid overfitting

* **downside**
  * Orthogonalization: fixing the 2 problems seperately 
    * Optimize cost function J
    * Not overfit
  * Early stopping tends to mix the two problems:
    * minimizing the cost function J 
    * in the meantime, no to overfit
  * Alternative: L2 regularization
    * computationally expensive to search for appropriate lambda
    * but iterate as long as possible
    * easier for the hyperparameter search space to decompose
* **strength**
  * get to experiment small w, mid-size w, and large w without try out lambda

