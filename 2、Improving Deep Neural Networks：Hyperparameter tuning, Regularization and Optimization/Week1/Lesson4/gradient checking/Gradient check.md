### Gradient check

* <img src='https://raw.githubusercontent.com/felipemaion/deeplearning-study/master/week%205%20-%20Gradient/images/dictionary_to_vector.png'>

* **notes on numpy copy**
  * **```b = a```**
  * **```b = a[:]```**
  * **```b = np.copy(a)```**

* Implementation

  ```python
  thetaplus = np.copy(parameters_values)
  thetaplus[i][0] = thetaplus[i][0] + epsilon
  J_plus[i], _ = forward_propagation_n(X, Y, 				vector_to_dictionary(thetaplus))
  ```

  ```python
  thetaminus = np.copy(parameters_values)
  thetaminus[i][0] = thetaminus[i][0] - epsilon
  J_minus[i], _ = forward_propagation_n(X, Y, 				vector_to_dictionary(thetaminus))
  ```

  ```python
  gradapprox[i] = (J_plus[i] - J_minus[i]) / (2 * epsilon)
  ```

  ```python
  numerator = np.linalg.norm(grad - gradapprox)                           
  denominator = np.linalg.norm(grad) + np.linalg.norm(gradapprox)     
  difference =  numerator / denominator
  ```

  