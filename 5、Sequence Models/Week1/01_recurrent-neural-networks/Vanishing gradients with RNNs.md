### Vanishing gradients with RNNs

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/01_recurrent-neural-networks/images/15.PNG' width='80%' heigth='80%'>

> *Example*
>
> > *The cats, which ... ... , ~~was~~ full*
> >
> > *The cats, which ... ... , were full*
>
> * RNN is not good at catching  long dependency
> * mainly local influenced
> * **gradients exploding** is easy to detect by finding `NaN`, which represents overflow 
>   * **gradient clipping** 
> * **gradients vanishing** is hard to fix

