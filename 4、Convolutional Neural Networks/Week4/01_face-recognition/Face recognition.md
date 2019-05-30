## Face recognition

#### What is face recognition problem 

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week4/01_face-recognition/images/1.PNG' width='80%' height='80%'>

***

#### One-shot learning

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week4/01_face-recognition/images/2.PNG' width='80%' height='80%'>

***

#### Siamese network

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week4/01_face-recognition/images/3.PNG' width='80%' height='80%'>

***

#### Triplet loss

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week4/01_face-recognition/images/4.PNG' width='80%' height='80%'>

> $$
> \|f(Anchor)-f(Positive)\|^2-\|f(Anchor)-f(Negative)\|^2+\underbrace{\alpha}_{margin}\leq0
> $$



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week4/01_face-recognition/images/5.PNG' width='80%' height='80%'>

> $Given\ 3\ images\ A,P,N$
> $$
> \mathscr{L}(A,P,N)=max(\|f(A)-f(P))\|^2-\|f(A)-f(N)\|^2+\alpha,0)\\
> J=\sum_{i=1}^{m}\mathscr{L}(A^{(i)},P^{(i)},N^{(i)})
> $$



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week4/01_face-recognition/images/6.PNG' width='80%' height='80%'>

***

#### Face recognition and binary classification

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week4/01_face-recognition/images/7.PNG' width='80%' height='80%'>

> $$
> \hat y=\sigma(\sum_{k=1}^{128}w_k \cdot d(f({x^{(i)}})_k, f(x^{(j)})_k)+b)\\
> d(f(x^{(i)}),f(x^{(j)}))=|f(x^{(i)}),f(x^{(j)})|\\
> \\ d(f(x^{(i)}),f(x^{(j)}))=\frac{(f(x^{(i)}),f(x^{(j)}))^2}{f(x^{(i)})-f(x^{(j)})} \sim \chi^2 \ distance
> $$

