## Neural style transfer

#### What is neural style transfer

<img src='images\1.PNG' width='80%' height='80%'>

***

#### what  are deep convnets learning

<img src='images\2.PNG' width='80%' height='80%'>



<img src='images\GIF.gif' width='80%' height='80%'>

***

#### cost function

<img src='images\3.PNG' width='80%' height='80%'>

> $$
> J(G)=\alpha J_{content}(C,G)+\beta J_{style}(S,G)
> $$



<img src='images\4.PNG' width='80%' height='80%'>



***

#### Content cost function

<img src='images\5.PNG' width='80%' height='80%'>

> $$
> J_{content}(C,G)=\frac{1}{2}\|a^{[l](C)}-a^{[l](G)}\|^2
> $$



***

#### Style cost function

<img src='images\6.PNG' width='80%' heigth='80%'>



<img src='images\7.PNG' width='80%' height='80%'>



<img src='images\8.PNG' width='80%' height='80%'>

> $$
> G^{[l](S)}_{k k^\prime}=\sum_{i=1}^{n_H^{[l]}}\sum_{j=1}^{n_W^{[l]}}a_{ijk}^{[l](S)}a_{ijk^\prime}^{[l](S)} \quad k,k^\prime=1,\cdots,n_c^{[l]}
> $$



<img src='images\9.PNG' width='80%' height='80%'>

> $$
> J_{style}(S,G)=\sum_l \lambda^{[l]}J_{style}^{[l]}(S,G)
> $$



***

#### 1D and 3D generalizations

<img src='images\10.PNG' width='80%' height='80%'>

> $2D\ case$
> $$
> 14\times14\times3 * 5\times5\times3 \rightarrow 10\times10\times \underbrace{16}_{\#filter} \\
> 10\times10\times 16 * 5\times5\times \underbrace{16}_{match\ the\ \#filter} \rightarrow 6\times6\times \underbrace{32}_{\#filter} 
> $$
> $1D\ case$
> $$
> 14\times1 * 5\times1 \rightarrow 10\times \underbrace{16}_{\#filter}\\
> 10\times 16 * 5\times \underbrace{16}_{match\ the\ \#filter} \rightarrow 6\times \underbrace{32}_{\#filter}
> $$



<img src='images\11.PNG' width='80%' height='80%'>

> $3D\ case$
> $$
> 14\times14\times14\times \underbrace{1}_{n_c} * 5\times5\times5\times1\rightarrow 10\times10\times10\times \underbrace{16}_{\# filter}\\
> 10\times10\times10\times \underbrace{16}_{\# filter} * 5\times5\times5\times \underbrace{16}_{match\ \# filter}\rightarrow 6\times6\times6\times \underbrace{32}_{\# filter}
> $$
>
> 