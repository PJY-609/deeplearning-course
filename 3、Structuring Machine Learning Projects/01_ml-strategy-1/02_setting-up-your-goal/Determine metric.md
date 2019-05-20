## Determine metric

### Use single number evaluation metric

| classifier | Precision | Recall | F1 score |
| :--------: | :-------: | :----: | :------: |
|     A      |    95%    |  90%   |  92.4%   |
|     B      |    98%    |  85%   |  91.0%   |

* **Precision**
  * if A says it is a *cat*, then there is 95% it is a *cat*
*  **Recall**
  * if all the images are *cats*, A would recognize 90% of them as *cats*

* **Downside**
  * can't judge whether A or B is better, each performs better at a single metric

* <img src="http://latex.codecogs.com/gif.latex? \hspace{2mm} F_1\ score={'average'\hspace of\hspace, precision\hspace, and\hspace, recall}" />
* <img src="http://latex.codecogs.com/gif.latex? \frac{2}{\frac{1}{P}+\frac{1}{R}}"/>

***

### Satisficing and optimizing metric

| Classifier | Accuracy | Running Time |
| :--------: | :------: | :----------: |
|     A      |   90%    |     80ms     |
|     B      |   92%    |     95ms     |
|     C      |   95%    |    1500ms    |

- **optimizing**: maximize accuracy
- **satisficing**: subject to running time $\leq$ 100ms
- N metric: 1 optimizing, N-1 satisficing
- <img src="http://latex.codecogs.com/gif.latex? cost=accuracy-0.5*running\_time" />

***

