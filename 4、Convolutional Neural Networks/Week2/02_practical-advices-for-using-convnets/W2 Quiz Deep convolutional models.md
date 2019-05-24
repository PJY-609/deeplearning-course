### W2 Quiz Deep convolutional models

1. Which of the following do you typically see as you move to deeper layers in a ConvNet?
   - [ ] $n_{H}$ and $n_{W}$ increases, while $n_{C}$ also increases
   - [ ] $n_{H}$ and $n_{W}$ decreases, while $n_{C}$ also decreases
   - [ ] $n_{H}$ and $n_{W}$ increases, while $n_{C}$ decreases
   - [x] $n_{H}$ and $n_{W}$ decrease, while $n_{C}$ increases

2. Which of the following do you typically see in a ConvNet? (Check all that apply.)
   - [x] Multiple CONV layers followed by a POOL layer
   - [ ] Multiple POOL layers followed by a CONV layer
   - [x] FC layers in the last few layers
   - [ ] FClayers in the first few layers

3. In order to be able to build very deep networks, we usually only use pooling layers to downsize the height/width of the activation volumes while convolutions are used with "valid" padding. Otherwise, we would downsize the input of the model too quickly.
   - [x] False

4. Training a deeper network (for example, adding additional layers to the network) allows
   the network to fit more complex functions and thus almost always results in lower
   training error. For this question, assume we're referring to "plain" networks.
   - [x] False

5. The following equation captures the computation in a ResNet block. What goes into the
   two blanks above?

   $a^{[l+2]}=g\left(W^{[l+2]} g\left(W^{[l+1]} a^{[l]}+b^{[l+1]}\right)+b^{l+2}+\_\_\_\right)+\_\_\_.$

   > $a^{[l]}$ and $0,$ respectively

6. Which ones of the following statements on Residual Networks are true? (Check all that
   apply.)
   - [ ] A ResNet with L layers would have on the order of $L^{2}$ skip connections in total.
   - [x] The skip-connection makes it easy for the network to learn an identity mapping
     between the input and the output within the ResNet block.
   - [ ] The skip-connections compute a complex non-linear function of the input to
     pass to a deeper layer in the network.
   - [x] Using a skip-connection helps the gradient to backpropagate and thus helps
     you to train deeper networks

7. Suppose you have an input volume of dimension $64 \times 64 \times 16 .$ How many parameters
   would a single $1 \times 1$ convolutional filter have (including the bias)?

   > ==$1\times1\times16+1=17$==

8. Suppose you have an input volume of dimension $n_{H} \times n_{W} \times n_{C} .​$ Which of the following
   statements you agree with? (Assume that "1\times1 convolutional layer" below always uses a
   stride of 1 and no padding.)
   - [ ] You can use a $1 \times 1$ convolutional layer to reduce $n_{H}, n_{W},$ and $n_{C}$ .
   - [x] You can use a pooling layer to reduce $n_{H}, n_{W},$ but not $n_{C}$ .
   - [x] You can use a $1 \times 1$ convolutional layer to reduce $n_{C}$ but not $n_{H}, n_{W}$
   - [ ] You can use a pooling layer to reduce $n_{H}, n_{W},$ and $n_{C}$ .

9. Which ones of the following statements on Inception Networks are true? (Check all that
   apply.)
   - [ ] Inception networks incorporates a variety of network architectures (similar to
     dropout, which randomly chooses a network architecture on each step and
     thus has a similar regularizing effect as dropout.
   - [x] A single inception block allows the network to use a combination of $1 \times 1,3 \times 3,$
     $5 \times 5$ convolutions and pooling.
   - [x] Making an inception network deeper (by stacking more inception blocks
     together) should not hurt training set performance.
   - [x] Inception blocks usually use $1 \times 1$ convolutions to reduce the input data
     volume's size before applying 3$x 3$ and $5 \times 5$ convolutions.
10. Which of the following are common reasons for using open-source implementations of
    ConvNets (both the model and/or weights)? Check all that apply.
    - [ ] The same techniques for winning computer vision competitions, such as using
      multiple crops at test time, are widely used in practical deployments (or
      production system deployments) of ConvNets.
    - [x] It is a convenient way to get working an implementation of a complex ConvNet
      architecture.
    - [ ] A model trained for one computer vision task can usually be used to perform
      data augmentation even for a different computer vision task.
    - [x] Parameters trained for one computer vision task are often useful as pretraining
      for other computer vision tasks.