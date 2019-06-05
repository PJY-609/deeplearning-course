### Initialization (supplementary)

> see [link](<http://www.deeplearning.ai/ai-notes/initialization/>) for more information and visualized illustration 

To prevent the gradients of the network's activations from **vanishing** or **exploding**, 

1. The *mean* of the activations should be **zero**.
2. The *variance* of the activations should **stay the same** across every layer.



Concretely, consider a *layer l*. 

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/2%E3%80%81Improving%20Deep%20Neural%20Networks%EF%BC%9AHyperparameter%20tuning%2C%20Regularization%20and%20Optimization/Week1/Lesson3/images/1.png' width='30%'>

Its forward propagation is,
$$
\begin{aligned} a^{[l-1]} &=g^{[l-1]}\left(z^{[l-1]}\right) \\ z^{[l]} &=W^{[l]} a^{[l-1]}+b^{[l]} \\ a^{[l]} &=g^{[l]}\left(z^{[l]}\right) \end{aligned}
$$
We would like the following to hold,
$$
\begin{aligned} E\left[a^{[l-1]}\right] &=E\left[a^{[l]}\right] \\ \operatorname{Var}\left(a^{[l-1]}\right) &=\operatorname{Var}\left(a^{[l)}\right) \end{aligned}
$$

> Under the hypothesis that all entries of the weight matrix $W^{[l]}$are picked from the same distribution, $Var(w_{11}) = Var(w_{12}) = ... = Var(w_{n^{[l]}n^{[l-1]}})$. Thus, $Var(W^{[l]})$ indicates the variance of any entry of $W^{[l]}$(they're all the same!). 
> Similarly, we will denote $Var(x)$ (resp. $Var(a^{[l]})$ the variance of any entry of $x$ (resp. $a^{[l]}$. It is a fair approximation to consider that every pixel of a "real-world image" x*x* is distributed according to the same distribution.



This method applies both to the **forward propagation** (for activations) and **backward propagation** (for gradients of the cost with respect to activations). The recommended initialization is **Xavier initialization** (or one of its derived methods), for every layer *l*:
$$
\begin{aligned} W^{[l]} & \sim \mathcal{N}\left(\mu=0, \sigma^{2}=\frac{1}{n^{[l-1]} }\right) \\ b^{[l]} &=0 \end{aligned}
$$

> In other words, all the weights of layer *l* are picked randomly from a *normal distribution* with mean $\mu = 0$ and variance $\sigma^2 = \frac{1}{n^{[l-1]}}$ where $n^{[l-1]}$ is the number of neuron in layer $l-1$. Biases are initialized with zeros.

***

### Justification for Xavier initialization

 Assume that our layer’s activations are normally distributed around zero.



 The forward propagation is:
$$
\begin{aligned} z^{[l]} &=W^{[l]} a^{[l-1]}+b^{[l]} \\ a^{l ]} &=\tanh \left(z^{[l]}\right) \end{aligned}
$$


Assume we initialized our network with appropriate values and the input is **normalized**. Early on in the training, we are in the *linear regime* of $tanh$. Values are small enough and thus $tanh(z^{[l]})\approx z^{[l]}$ meaning that:
$$
\operatorname{Var}\left(a^{[l]}\right)=\operatorname{Var}\left(z^{[l]}\right)
$$


Moreover, $z^{[l]} = W^{[l]}a^{[l-1]} + b^{[l]} = vector(z_1^{[l]},z_2^{[l]},\dots,z_{n^{[l]}}^{[l]})$ where $z_k^{[l]} = \sum_{j=1}^{n^{[l-1]}}w_{kj}^{[l]}a_j^{[l-1]} + b_k^{[l]}$. For simplicity, let’s assume that $b^{[l]} = 0$ (it will end up being true given the choice of initialization we will choose). Thus, looking *element-wise* at the previous equation $Var(a^{[l-1]}) = Var(a^{[l]})$now gives:
$$
\operatorname{Var}\left(a_{k}^{[l]}\right)=\operatorname{Var}\left(z_{k}^{[l]}\right)=\operatorname{Var}\left(\sum_{j=1}^{n^{[l-1]}} w_{k j}^{[l]} a_{j}^{[l-1 ]}\right)
$$


A common math trick is to extract the summation outside the variance. To do this, we must make the following three *assumptions*:

1. Weights are independent and identically distributed
2. Inputs are independent and identically distributed
3. Weights and inputs are mutually independent



Thus, now we have:
$$
\operatorname{Var}\left(a_{k}^{[l]}\right)=\operatorname{Var}\left(z_{k}^{[l]}\right)=\operatorname{Var}\left(\sum_{j=1}^{n^{[l-1]}} w_{k j}^{[l]} a_{j}^{[l-1 ]}\right)
=\sum_{j=1}^{n^{l-1}} \operatorname{Var}\left(w_{k j}^{[l]} a_{j}^{[l-1]}\right)
$$


Another common math trick is to convert the variance of a product into a product of variances. Here is the *formula* for it:
$$
Var(XY) = E[X]^2Var(Y) + Var(X)E[Y]^2 + Var(X)Var(Y)
$$


Using this formula with $X = w_{kj}^{[l]}$and $Y = a_j^{[l-1]}$, we get:
$$
\operatorname{Var}\left(w_{k j}^{[l]} a_{j}^{[l-1]}\right)=E\left[w_{k j}^{[l]}\right]^{2} \operatorname{Var}\left(a_{j}^{[l-1]}\right)+\operatorname{Var}\left(w_{k j}^{[l]}\right) E\left[a_{j}^{[l-1]}\right]^{2}+\operatorname{Var}\left(w_{k j}^{[l]}\right) \operatorname{Var}\left(a_{j}^{[l-1]}\right)
$$


The first assumption leads to $E[w_{kj}^{[l]}]^2 = 0$and the second assumption leads to $E[a_j^{[l-1]}]^2 = 0$ because weights are initialized with zero mean, and inputs are normalized. Thus:
$$
\operatorname{Var}\left(z_{k}^{[l]}\right)=\sum_{j=1}^{n^{l-1} 1} \operatorname{Var}\left(w_{k j}^{[l]}\right) \operatorname{Var}\left(a_{j}^{[l-1]}\right)\\=\sum_{j=1}^{n^{l-1} |} \operatorname{Var}\left(W^{[l]}\right) \operatorname{Var}\left(a^{[l-1]}\right)=n^{[l-1]} \operatorname{Var}\left(W^{[l]}\right) \operatorname{Var}\left(a^{[l-1]}\right).
$$
The equality above results from our first assumption stating that:
$$
\operatorname{Var}\left(w_{k j}^{[l]}\right)=\operatorname{Var}\left(w_{11}^{[l]}\right)=\operatorname{Var}\left(w_{12}^{[l]}\right)=\cdots=\operatorname{Var}\left(W^{[l]}\right)
$$
Similarly the second assumption leads to:
$$
\operatorname{Var}\left(a_{j}^{[l-1]}\right)=\operatorname{Var}\left(a_{1}^{[l-1]}\right)=\operatorname{Var}\left(a_{2}^{[l-1]}\right)=\cdots=\operatorname{Var}\left(a^{[l-1]}\right)
$$
With the same idea:
$$
Var(z^{[l]}) = Var(z_k^{[l]})
$$
Wrapping up everything, we have:
$$
\operatorname{Var}\left(a^{[l]}\right)=n^{[l-1]} \operatorname{Var}\left(W^{[l]}\right) \operatorname{Var}\left(a^{[l-1]}\right)
$$
If we want the variance to stay the same across layers $(Var(a^{[l]}) = Var(a^{[l-1]})$, we need $Var(W^{[l]}) = \frac{1}{n^{[l-1]}}$. This justifies the choice of variance for Xavier initialization.



 Let $L$be the output layer of our network. Using this expression at every layer, we can link the output layer's variance to the input layer's variance:
$$
\begin{aligned} \operatorname{Var}\left(a^{[L]}\right) &=n^{[L-1]} \operatorname{Var}\left(W^{[L]}\right) \operatorname{Var}\left(a^{[L-1]}\right) \\ &=n^{[L-1]} \operatorname{Var}\left(W^{[L]}\right) n^{[L-2]} \operatorname{Var}\left(W^{[L-1]}\right) \operatorname{Var}\left(a^{[L-2]}\right) \\ &=\ldots \\ &=\left[\prod_{l=1}^{L} n^{[l-1]} \operatorname{Var}\left(W^{[l]}\right)\right] \operatorname{Var}(x) \end{aligned}
$$


Depending on how we initialize our weights, the relationship between the variance of our output and input will vary dramatically. Notice the following three cases.
$$
n^{[l-1]} \operatorname{Var}\left(W^{[l]}\right)\left\{\begin{array}{l}{<1} \Longrightarrow Vanishing Signal\\ {=1} \Longrightarrow \operatorname{Var}\left(a^{[L]}\right)=\operatorname{Var}(x)\\ {>1} \Longrightarrow Exploding Signal\end{array}\right.
$$
Thus, in order to avoid the vanishing or exploding of the forward propagated signal, we must set $n^{[l-1]} \operatorname{Var}\left(W^{[l]}\right)=1$ by initializing $Var(W^{[l]}) = \frac{1}{n^{[l-1]}}$.

***

### Conclusion

In practice, Machine Learning Engineers using Xavier initialization would either initialize the weights as $\mathcal{N}(0,\frac{1}{n^{[l-1]}})$or as $\mathcal{N}(0,\frac{2}{n^{[l-1]} + n^{[l]}})$. The variance term of the latter distribution is the harmonic mean of $\frac{1}{n^{[l-1]}}$and $\frac{1}{n^{[l]}}$.