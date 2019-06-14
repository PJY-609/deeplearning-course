### GRU - Gated recurrent unit

<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/01_recurrent-neural-networks/images/16.PNG'>



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/01_recurrent-neural-networks/images/17.PNG' width='80%' height='80%'>

> $$
> c^{<t>}=a^{<t>}\\
> \tilde c^{<t>}=tanh(W_c[c^{<t-1>},x^{<t>}]+b_c)\\
> \Gamma_u=\sigma(W_u[c^{<t-1>},x^{<t>}]+b_u)\\
> c^{<t>}=\Gamma_u*\tilde c^{<t>}+(1-\Gamma_u)*c^{<t-1>} \quad (*\ is\ element-wise)
> $$
>
> * Consider $\Gamma_u$ as a update gate range over $(0,1)$ 
>   * when $\Gamma_u=1$ , it choses to update $c^{<t>}=\tilde c^{<t>}$
>   * when $\Gamma_u=0$, it choses to hold on $c^{<t>}=c^{<t-1>}$
> * In practice,  $\Gamma_u$ is normally very close to 0
>   * therefore, GRUs is good at maintaining values
>   * fix the gradients vanishing issue  
> * $c^{<t>}$ ,$\tilde c^{<t>}$, $\Gamma_u$ are vectors
>   * each bit can be regarded as storing different information of this sentence



<img src='https://raw.githubusercontent.com/yujuezhao/deeplearning-course/master/5%E3%80%81Sequence%20Models/Week1/01_recurrent-neural-networks/images/18.PNG' width='80%' height='80%'>

> $$
> \begin{array}{l}{\tilde{c}^{<t>}=\tanh \left(W_{c}\left[\Gamma_{r} * c^{<t-1>}, x^{<t>}\right]+b_{c}\right)} \\ {\Gamma_{u}=\sigma\left(W_{u}\left[c^{<t-1>}, x^{<t>}\right]+b_{u}\right)} \\ {\Gamma_{r}=\sigma\left(W_{r}\left[c^{<t-1>}, x^{<t>}\right]+b_{r}\right)} \\ {c^{<t>}=\Gamma_{u}* \tilde{c}^{<t>}+\left(1-\Gamma_{u}\right) * c^{<t-1>}} \\ {a^{<t>}=c^{<t>}}\end{array}
> $$

