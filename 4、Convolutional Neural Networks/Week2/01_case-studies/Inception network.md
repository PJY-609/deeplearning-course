### Inception network

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week2/images/10.PNG'>

***

### The problem of computational cost

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week2/images/11.PNG'>

> $$
> (28\times28\times32)\times(5\times5\times192)\approx120M
> $$

***

### Using 1 $\times$ 1 convolution

* **bottle-neck layer**

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week2/images/12.PNG'>

> $$
> (28\times28\times16)\times192+(28\times28\times32\times5\times5\times16)\approx12.4M
> $$

***

### Inception module

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week2/images/13.PNG'>

***

### Inception network

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week2/images/14.PNG'>

