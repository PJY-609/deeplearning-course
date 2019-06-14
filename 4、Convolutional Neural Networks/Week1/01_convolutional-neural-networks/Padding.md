### Padding

* $(n-f+1) \times (n-f+1)$
  * shrinking output
  * throw away information 
* **padding**
  * $p=padding=1$
  * $(n+2p-f+1)\times (n+2p-f+1)$

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week1/01_convolutional-neural-networks/images/6.PNG' height='70%' width='70%'>

***

### <a name='valid-same'>Valid and Same convolutions</a>

* **Valid**: no padding
* **Same**: pad so that output size is the same size as the input size
  * $n+2p-f+1=n \Rightarrow p= \frac{f-1}{2}$
  * $f​$ is usually **odd**
    * a central position

