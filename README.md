# Kaggle-Dog-Cat-Adoption
Kaggle Dog Cat Adoption Challenge

###### What you will need :

- A Python machine learning environment (see [here](https://github.com/pleboulanger/Python-install-for-Machine-Learning-Tensorflow-Keras-Windows-7))
- Ideas and/or curiosity

Hello! This respository will aim at explaining a baseline submission to a Kaggle [competition](https://www.kaggle.com/c/petfinder-adoption-prediction).
This competition is about predicting the potential adoption of an animal based on its profile on petfinder.my website.

In this baseline submission we will:
- Download and explore the dataset
- Try to run a simple CNN on dog and cat pictures
- Evaluate our predictions on the test set

Let's start!
>jupyter notebook

The jupyter notebook should open in your web browser. If it doesn't, copy paste the link in terminal that looks like
>http://localhost:8888/?token=31314d79ccf87a3d79cc377808db8cda06d84196887d0e0f

You can try to run the following "hello world"
```
import tensorflow as tf
mnist = tf.keras.datasets.mnist

(x_train, y_train),(x_test, y_test) = mnist.load_data()
x_train, x_test = x_train / 255.0, x_test / 255.0

model = tf.keras.models.Sequential([
  tf.keras.layers.Flatten(),
  tf.keras.layers.Dense(512, activation=tf.nn.relu),
  tf.keras.layers.Dropout(0.2),
  tf.keras.layers.Dense(10, activation=tf.nn.softmax)
])
model.compile(optimizer='adam',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])

model.fit(x_train, y_train, epochs=5)
model.evaluate(x_test, y_test)
```

The result should be something like that (showing the training):

![alt text](https://github.com/pleboulanger/Python-install-for-Machine-Learning-Tensorflow-Keras-Windows-7/blob/master/Mnist.PNG)

Congratulation, you just trained your first Deep Learning model!!

###### Sources :

Python
https://www.python.org/downloads/release/python-352/
