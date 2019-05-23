### Convolutions over volume

* $height\times width \times \#channel$ 
  * the number of channels must match



* the dynamic of convolution over volume

<img src='images\1.gif'>



* the output of convolution over volume is 2D images

<img src='images\9.png' height='70%' width='70%'>



* stack the output of multiple filters  
  * $(n\times n \times n_c)*(f\times f \times n_c) \Rightarrow (n-f+1)\times (n-f+1) \times \underset{\#filter}{n^{\prime}_c}​$

<img src='images\10.Png' height='70%' width='70%'>

