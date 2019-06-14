### LSTM

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/01_recurrent-neural-networks/images/19.PNG' width='80%' height='80%'>

> $\Gamma_u$, $\Gamma_f$, $\Gamma_0$ 3 gates to govern the output of LSTM 



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/01_recurrent-neural-networks/images/20.PNG' width='80%' height='80%'>

> * pay attention to all the gates computing with $a^{<t-1>},x^{<t>}$ 
> * *peephole* connection insert $c^{<t-1>}$ into $\Gamma_o$
> * See to read line and understand why LSTM is good at memorizing long-term dependency
> * LSTMs are more powerful while GRUs are smaller in scale and easy to train

