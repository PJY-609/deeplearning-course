### tensorflow tutorial

* ```tf.constant(val, name=)```

* ```python
  with tf.Session() as sess:
  	sess.run()
  sess.close()
  ```

* ```python
  x = tf.placeholder(tf.float, name=)
  sigmoid = tf.sigmoid(x)
  sess.run(sigmoid, feed_dict={x:z})
  ```

* ```X=tf.constant(np.random.randn(m,n), name=)```

* ```tf.nn.sigmoid_cross_entropy_with_logits(logits=, labels=)```

* ```tf.one_hot(labels, depth, axis)```

* ```tf.ones(shape)```

* ```tf.get_variable('w', shape, initializer=tf.contrib.layers.xavier_initializer(seed = 1))```
* ```tf.get_variable('b',shape,initializer=tf.zeros_initializer())```
* ```tf.nn.relu()```

* ```tf.reduce_mean(tf.nn.softmax_cross_entropy_with_logits())```

* ```python
  optimizer = tf.train.AdamOptimizer(learning_rate = learning_rate).minimize(cost)
  init = tf.global_variables_initializer()
  with tf.Session as sess:
      sess.run(init)
      ... ...
      _, cost = 
  sess.run([optimizer, cost], feed_dict={X: minibatch_X, Y: minibatch_Y})
  ```