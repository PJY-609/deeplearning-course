### Optimization methods

* **```random_mini_batches()```**

  * ```Shuffle```

    * ```python
      permutation = list(np.random.permutation(m))
      shuffled_X = X[:, permutation]
      shuffled_Y = Y[:, permutation].reshape((1,m))
      ```

