### Regularization

* $$
  \mathop{min}_{w,b}J(w,b)
  $$

* $$
  J=(w,b)=
  \frac{1}{m}
  \sum_{i=1}^{m}\mathscr{L}(\hat y^{(i)},y^{(i)})
  +
  \frac{\lambda}{2m}\|w\|^2_2
  $$

* $L2\ regularization$
  $$
  \|w\|^2_2=\sum^{n_x}_{j=1}w^2_j=w^Tw
  $$

* $L1\ regularization(w\ will\ be\ sparse)$
  $$
  \|w\|_1=\sum_{i=1}^{n_x}|w_i|
  $$

* $\lambda =regularization\ parameter$

***

### In neural network

* $$
  J(w^{[1]},b^{[1]},...,w^{[L]},b^{[L]})=
  \frac{1}{m}
  \sum_{i=1}^{m}\mathscr{L}(\hat y^{(i)},y^{(i)})
  +
  \frac{\lambda}{2m}
  \sum_{l=1}^{L}
  \|w^{[l]}\|^2
  $$

* $Frobenius\ norm:\ \| \cdot\|^2_F$
  $$
  \|w^{[l]}\|^2_F=
  \sum_{i=1}^{n^{[l-1]}}
  \sum_{j=1}^{n^{[l]}}
  (w^{[l]}_{ij})^2,\
  w:(n^{[l]},n^{[l-1]})
  $$

* $now\ in\ backward\ propagation$
  $$
  dw^{[l]}=(from\ backprop)+\frac{\lambda}{m}w^{[l]}\\
  w^{[l]}:=w^{[l]}-\alpha dw^{[l]}=(1-\frac{\alpha\lambda}{m})w^{[l]}
  -
  \alpha(from\ backprop)
  $$
  

***

### Why regularization helps

- $\lambda \uparrow,\ w^{[l]} \downarrow$
  - $weaken\ some\ weights\ of\ units\ and\ simplify\ the\ neural\ network $
  - $z^{[l]} \downarrow,\ the\ activation\ functions\ act\ more\ linear,\ thus\ avoiding\ overfitting$

- pay attention to draw the whole term of cost function with the added regularization part