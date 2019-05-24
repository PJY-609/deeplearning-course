### Residual block

* $a^{[l+1]}=g(z^{[l+1]}+a^{[l]})$

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week2/images/4.PNG'>

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week2/images/5.PNG'>

***

### why ResNets work

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week2/images/6.PNG'>

> $$
> a^{[l+2]}=
> g(z^{[l+2]}+w_sa^{[l]})
> =g(w^{[l+2]}a^{[l+1]}+b^{[l+2]}+w_sa^{[l]})
> \mathop{=}^{w^{[l+2]}=b^{[l+2]}=0}g(w_sa^{[l]})
> \mathop{=}^{ReLU}w_sa^{[l]}\\
> e.g.\ a^{[l+2]} \in \mathbb{R}^{256\times1}, a^{[l]}\in \mathbb{R}^{128\times1},w_s\in \mathbb{R}^{256\times128}(zero-padding)
> $$



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/4%E3%80%81Convolutional%20Neural%20Networks/Week2/images/7.PNG'>