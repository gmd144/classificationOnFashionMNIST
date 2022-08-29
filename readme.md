# Classification on Fashion MNIST dataset
Fashion-MNIST is a dataset of Zalando's article images consisting of a training set of 60,000 examples and a test set of 10,000 examples. Each example is a 28x28 grayscale image, associated with a label from 10 classes. Zalando intends Fashion-MNIST to serve as a direct drop-in replacement for the original MNIST dataset for benchmarking machine learning algorithms. It shares the same image size and structure of training and testing splits.

Each training and test example is assigned to one of the following labels:

<table>
  <thead>
      <tr>
        <th>Label</th>
        <th>Description</th>
      </tr>
  </thead>
  <tbody>

  </tbody>
      <tr><td>0</td> <td>T-shirt/top</td></tr>
      <tr><td>1</td> <td>Trouser</td></tr>
      <tr><td>2</td> <td>Pullover</td></tr>
      <tr><td>3</td> <td>Dress</td></tr>
      <tr><td>4</td> <td>Coat</td></tr>
      <tr><td>5</td> <td>Sandal</td></tr>
      <tr><td>6</td> <td>Shirt</td></tr>
      <tr><td>7</td> <td>Sneaker</td></tr>
      <tr><td>8</td> <td> Bag</td></tr>
      <tr><td>9</td> <td> Ankle boot</td></tr>
<table>
<hr>

Here is how the dataset looks
<br>


![](https://raw.githubusercontent.com/zalandoresearch/fashion-mnist/master/doc/img/fashion-mnist-sprite.png)

<img src="https://github.com/zalandoresearch/fashion-mnist/blob/master/doc/img/embedding.gif?raw=true" width="100%">

<br>
<hr>

# Methodology

<p>I will create two models both from scratch and I will randomly select hyperparameters for the first model and check how it performs on this dataset. Then I will use the SkLearn's RandomizedSearchCV to obtain the best values of hyperparameters to use with my CNN model. I will try to figure out only two hyperparameters i.e. number of kernels to use in the <a href="https://keras.io/api/layers/convolution_layers/convolution2d/">Conv2D</a> layer and the value for dropout in the <a href="https://keras.io/api/layers/regularization_layers/dropout/">Dropout</a> layer and I will use only one Dropout layer after the Flatten layer.</p>

<p>I have used the keras padding layer to add zero padding to the input images to improve the results of the convolution and I have used the rescaling layer to rescale my images to [0.0, 1.0] range.</p>

<p>I have used the regularization to regularize weights in the final two Dense layers. All of these measures were taken so that the model does not overfits the data. I have not implemented the augmentation to images which could be done to further reduce the overfitting threat.</p>

## Results

With the first model I was able to get 90% accuracy on train set after training the model for 15 epochs and 88% accuracy on the test set. However, with the second model after training it for the 20 epochs I was able to get a 96% training accuracy and a 92.9% accuracy on the test set.

# LICENSE

MIT