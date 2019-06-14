### Pooling

* **Max pooling**
  * with hyperparameters do not need to learn

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week1/01_convolutional-neural-networks/images/15.PNG' width='60%'>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week1/01_convolutional-neural-networks/images/2.gif' width="60%">

> **operate on different channels independently**



* **Average pooling**

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week1/01_convolutional-neural-networks/images/16.PNG'  width='60%'>



***

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week1/01_convolutional-neural-networks/images/17.PNG' width='80%'>

> No parameters to learn
> $$
> n_H \times n_W \times n_c \rightarrow \biggl\lfloor\frac{n_H-f}{s}+1\biggr\rfloor \times \biggl\lfloor\frac{n_W-f}{s}+1\biggr\rfloor \times n_C
> $$

