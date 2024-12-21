# amWRit

# CS50AI 2020
## Week 5 (Neural Networks) || Traffic

Developed upon the original distro code provided by CS50AI team.

### Traffic

Write an AI to identify which traffic sign appears in a photograph.
````
$ python traffic.py gtsrb
Epoch 1/10
500/500 [==============================] - 5s 9ms/step - loss: 3.7139 - accuracy: 0.1545
Epoch 2/10
500/500 [==============================] - 6s 11ms/step - loss: 2.0086 - accuracy: 0.4082
Epoch 3/10
500/500 [==============================] - 6s 12ms/step - loss: 1.3055 - accuracy: 0.5917
Epoch 4/10
500/500 [==============================] - 5s 11ms/step - loss: 0.9181 - accuracy: 0.7171
Epoch 5/10
500/500 [==============================] - 7s 13ms/step - loss: 0.6560 - accuracy: 0.7974
Epoch 6/10
500/500 [==============================] - 9s 18ms/step - loss: 0.5078 - accuracy: 0.8470
Epoch 7/10
500/500 [==============================] - 9s 18ms/step - loss: 0.4216 - accuracy: 0.8754
Epoch 8/10
500/500 [==============================] - 10s 20ms/step - loss: 0.3526 - accuracy: 0.8946
Epoch 9/10
500/500 [==============================] - 10s 21ms/step - loss: 0.3016 - accuracy: 0.9086
Epoch 10/10
500/500 [==============================] - 10s 20ms/step - loss: 0.2497 - accuracy: 0.9256
333/333 - 5s - loss: 0.1616 - accuracy: 0.9535
````

#### Experiments Tried
- Different number of Convolutional layers
    - One to three
- Different filter sizes in convolutional layer
    - 32
    - 64
- Different kernel sizes in different convolutional layers
    - 1x1
    - 2x2
    - 3x3
    - 4x4
    - 6x6
- Different number of Pooling layers
    - Zero to four
- Different pool size in different pooling layers
    - 1x1
    - 2x2
    - 4x4
- Different number of hidden layers
    - Zero to four
- Different size of each hidden layer
20, 60, 80, 100, 400
    - NUM_CATEGORIES * 16
    - NUM_CATEGORIES * 10
    - NUM_CATEGORIES * 8
    - NUM_CATEGORIES * 6
    - NUM_CATEGORIES * 4
    - NUM_CATEGORIES * 3
- Different dropout rates in input layer
    - 0.2
    - 0.4
    - 0.6
- Different dropout rates in hidden layers
    - 0.2
    - 0.4
    - 0.6
    
#### Observations from the experiments
- 2x2 kernel size worked best for single convolutional layer without any other layers
- On increasing the number of convolutional layer to three, memory usage and time taken was massive
- 2x2 pool size worked best for single convolutional layers with single pooling layer
- Increasing only the number of pooling layers didn't bring any significant improvement
- Different filter size (32 and 64) in two different convolution layers however brough some improvement
- Introducing one hidden layer of size 20 decreased the accuracy instead
- Increasing the size of hidden layer to 400 improved the accuracy drastically
- Adding another hidden layer with 400 size didn't bring any improvements
- On increasing number hidden layers  (upto 4), the accuracy rather decreased
- On two hidden layers, decreasing the size from first to second improved the accuracy, but didn't seem to reliable
- 0.2 seemed to be the best dropout rate (out of tested 0.2, 0.4 and 0.6)
- 0.2 dropout on input layer increased the accuracy
- 0.2 dropout on hidden layer increased the accuracy

#### Output
````
Epoch 1/10
500/500 [==============================] - 21s 40ms/step - loss: 4.6728 - accuracy: 0.3210
Epoch 2/10
500/500 [==============================] - 20s 39ms/step - loss: 0.6179 - accuracy: 0.8156
Epoch 3/10
500/500 [==============================] - 20s 39ms/step - loss: 0.3253 - accuracy: 0.9056
Epoch 4/10
500/500 [==============================] - 20s 40ms/step - loss: 0.2544 - accuracy: 0.9275
Epoch 5/10
500/500 [==============================] - 20s 40ms/step - loss: 0.2138 - accuracy: 0.9386
Epoch 6/10
500/500 [==============================] - 20s 40ms/step - loss: 0.1546 - accuracy: 0.9560
Epoch 7/10
500/500 [==============================] - 20s 40ms/step - loss: 0.1717 - accuracy: 0.9539
Epoch 8/10
500/500 [==============================] - 20s 40ms/step - loss: 0.1183 - accuracy: 0.9666
Epoch 9/10
500/500 [==============================] - 20s 40ms/step - loss: 0.1760 - accuracy: 0.9554
Epoch 10/10
500/500 [==============================] - 20s 41ms/step - loss: 0.1470 - accuracy: 0.9620
333/333 - 3s - loss: 0.0905 - accuracy: 0.9772

````
#### Base model 
- One convolutional layer
    - 3x3 kernel size
    - 32 filters
- Average accuracy: 0.8956

#### Current model 
- Two convolutional layer
    - 3x3 and 2x2 kernel size
    - 32 and 64 filters respectively
- Two pooling layers after each convolutional layer
    - 2x2 pool size in both
- 0.2 dropout on input layer
- 3 hidden layers
    - NUMBER_CATEGORIES * 16, NUMBER_CATEGORIES * 8 and NUMBER_CATEGORIES * 4 sizes
    - 0.2 dropout rate after first and second hidden layers
- Average accuracy: 0.9645

#### Keywords
````
Neural Networks
Artificial Neural Networks
Activation Functions
Neural Network Structure
Multilayer Neural Networks
Backpropagation
Overfitting
Tensorflow
Image convolution
Convolutional Neural Networks
Recurrent Neural Networks
Convolution
Pooling
Flattering
Hidden Layers
````

#### References
````
https://cs50.harvard.edu/ai/2020/notes/5/
````
