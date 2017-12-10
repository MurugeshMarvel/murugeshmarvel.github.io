---
layout: post
title: TF
permalink: /tf-tutorial/
---

# Tensorflow - Getting Started


```
import tensorflow as tf
```

### Computational Graph


```
#Building Computation graph
node1 = tf.constant(3.0, dtype=tf.float32)
node2 = tf.constant(4.0)
print(node1, node2)
```

    (<tf.Tensor 'Const:0' shape=() dtype=float32>, <tf.Tensor 'Const_1:0' shape=() dtype=float32>)



```
#Running Computation graph
sess = tf.Session()
print(sess.run([node1, node2]))
```

    [3.0, 4.0]


#### Adding Constants


```
node3 = tf.add(node1, node2)
print ("node3:", node3)
print "sess.run(node3)",sess.run(node3)
```

    ('node3:', <tf.Tensor 'Add_2:0' shape=() dtype=float32>)
    sess.run(node3) 7.0


### Accepting External Inputs - Placeholders


```
a = tf.placeholder(tf.float32)
b = tf.placeholder(tf.float32)
adder_node = a +b
```


```
print sess.run(adder_node,{a:4,b:9.1})
```

    13.1



```
print sess.run(adder_node,{a:[3,5],b:[4,8]})
```

    [  7.  13.]


### Complexing operations using placeholders


```
add_and_triple = adder_node * 3.
print sess.run(add_and_triple, {a:[4,6],b:[9,1]})
```

    [ 39.  21.]


## Variables


```
w = tf.Variable([.3],dtype=tf.float32)
b = tf.Variable([-.3], dtype=tf.float32)
x = tf.placeholder(tf.float32)
linear_model = w * x +b
```


```
init = tf.global_variables_initializer()
sess.run(init)
```


```
print sess.run(linear_model, {x:[1,2,3,4]})
```

    [ 0.          0.30000001  0.60000002  0.90000004]


#### Loss Function


```
y = tf.placeholder(tf.float32)
squared_deltas = tf.square(linear_model - y)
loss = tf.reduce_sum(squared_deltas)
print sess.run(loss, {x:[1,2,3,4], y:[0,-1,-2,-3]})
```

    23.66


##### Reassigning the Variable to minimise loss


```
new_w = tf.assign(w,[-1.])
new_b = tf.assign(b,[1.])
sess.run([new_w, new_b])
print(sess.run(loss, {x:[1,2,3,4],y:[0,-1,-2,-3]}))
```

    0.0
