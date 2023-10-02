# capitol_Homework

A Repository where I will store all Homework assignments for Advanced Machine Learning held at Capitol Technology University

## HW 1

My initial experiment for the first homework was to utilize the equation to convert pounds to kilograms. It is important to remember that to convert pounds to kilograms we would need to divide the value in pounds by  2.205. 

To begin the process I wanted to utilize a data set of around 10 values in pounds and kilograms respectively to ensure we can have a decent starting set.
```python
import tensorflow as tf
import numpy as np
import matplotlib.pyplot as plt
from keras.models import Sequential
from keras.layers import Activation, Dense

# Kilograms (kg) array
kg_values = np.array([1.0, 5.0, 10.0, 15.0, 20.0, 25.0, 30.0, 35.0, 40.0, 45.0], dtype=float)

# Pounds (lb) array
lb_values = np.array([2.20462, 11.0231, 22.0462, 33.0693, 44.0924, 55.1155, 66.1387, 77.1618, 88.1849, 99.208], dtype=float)

for i,c in enumerate(lb_values):
  print(str(c) + " weight in pounds = weight in kilograms " + str(kg_values[I]))

Output:

for i,c in enumerate(lb_values):
  print(str(c) + " weight in pounds = weight in kilograms " + str(kg_values[I]))


OUTPUT:
2.20462 weight in pounds = weight in kilograms 1.0
11.0231 weight in pounds = weight in kilograms 5.0
22.0462 weight in pounds = weight in kilograms 10.0
33.0693 weight in pounds = weight in kilograms 15.0
44.0924 weight in pounds = weight in kilograms 20.0
55.1155 weight in pounds = weight in kilograms 25.0
66.1387 weight in pounds = weight in kilograms 30.0
77.1618 weight in pounds = weight in kilograms 35.0
88.1849 weight in pounds = weight in kilograms 40.0
99.208 weight in pounds = weight in kilograms 45.0

```

Once we have done that I am now establishing my 1 input neuron and 1 output neuron through the following code:

```python
layer_0 = Dense(units=1, input_shape=[1])
model = Sequential()
model.add(layer_0)
model.compile(loss='mean_squared_error', optimizer=tf.keras.optimizers.Adam(0.25))
model.summary()


OUTPUT:

Model: "sequential_6"
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 dense_6 (Dense)             (None, 1)                 2         
                                                                 
=================================================================
Total params: 2 (8.00 Byte)
Trainable params: 2 (8.00 Byte)
Non-trainable params: 0 (0.00 Byte)
_________________________________________________________________


history = model.fit(x=lb_values, y=kg_values, epochs=1000, verbose=True)

OUTPUT:

Epoch 1/1000
1/1 [==============================] - 0s 409ms/step - loss: 11651.7686
Epoch 2/1000
1/1 [==============================] - 0s 9ms/step - loss: 8652.5420
Epoch 3/1000
1/1 [==============================] - 0s 10ms/step - loss: 6114.2485
Epoch 4/1000
1/1 [==============================] - 0s 14ms/step - loss: 4039.8567
Epoch 5/1000
1/1 [==============================] - 0s 11ms/step - loss: 2424.2888
Epoch 6/1000
1/1 [==============================] - 0s 11ms/step - loss: 1251.4348
Epoch 7/1000
1/1 [==============================] - 0s 12ms/step - loss: 491.1049
Epoch 8/1000
1/1 [==============================] - 0s 9ms/step - loss: 96.4522
Epoch 9/1000
1/1 [==============================] - 0s 8ms/step - loss: 3.1795
Epoch 10/1000
1/1 [==============================] - 0s 8ms/step - loss: 132.0785
Epoch 11/1000
1/1 [==============================] - 0s 7ms/step - loss: 395.7714
Epoch 12/1000
1/1 [==============================] - 0s 12ms/step - loss: 708.8947
Epoch 13/1000
1/1 [==============================] - 0s 9ms/step - loss: 998.9578
Epoch 14/1000
1/1 [==============================] - 0s 10ms/step - loss: 1214.3893
```
What I also did was utilize varying values for the epochs & Adams value however by making the epoch value too large I realized that I was making more room for error due to the loss fluctuating to the point it was increasing due to the mass amount of Epochs.

What this helped me to understand is that establishing an adequate value for the epoch is essential to ensure that the loss value does not begin to fluctuate to the point that it's increasing when it should not be. Furthermore, I also tampered with the Adams value but noticed too few values caused my value for m in regards to the mx+b equation to be a bit off compared to what I desired from my current Adaams family. the accuracy is a bit less however the accuracy of the m values with respect to the mx+b equation was crucial for me to fully understand that even though accuracy was impacted, it's essential to ensure that the values that are heavily relied upon for correctly calculating the data is set to a reasonable value. This helped me understand a bit more of what is needed to understand when setting up these input and output layers.

Now within the following code, we are able to visually see how drastically the loss value decreases due to our epochs:

```python
plt.xlabel('Epoch')
plt.ylabel("Loss")
plt.plot(history.history['loss'])
print(model.predict([100.0]))

OUTPUT:
1/1 [==============================] - 1s 524ms/step
[[45.35922]]


```


I noticed that decreasing the number of epochs also would cause issues displaying why our current value is ideal in this scenario. We can also see that we are able to accurately get the value of 100 pounds which is 45.3592

To conclude we are finally able to see our weight which is 4535916 which is  equivalent to 0.453592 which is the value of when we convert 1 pound to 1 kilogram. this demonstrated our neural network was able to get an accurate weight since 1 pd is 0.453592. Our Bias is as close to 0 since there is no additional bias present in this conversion formula. What we have demonstrated is a clear understanding of how to create this network and an understanding of what occurs throughout this process.



```python
print("These are the layer variables: " + str(layer_0.get_weights()))
# The formula is F = 1.8 *c +32, where weight is 0.453592 and bias is 0

OUTPUT:
These are the layer variables: [array([[0.4535916]], dtype=float32), array([6.148701e-05], dtype=float32)]
```



