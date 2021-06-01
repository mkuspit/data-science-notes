# Deep Learning

## Theory
### Deep neural networks notation
- $L$ - number of layers in the network (excluding input layer, including output layer) 
- $n^{[l]}$ - number of units in l-th layer
- $n^{[0]} = n_x$ - number of features
- $a^{[l]}$ - number of activations in l-th layer $a^{[l]} = g^{[l]}(z^{[l]})$
- $W^{[l]}$, $b^{[l]}$ - weights for l-th layer
- $a^{[0]} = x$
- $a^{[L]} = \hat{y}$

  Matrix dimensions
- $W^{[l]}$ : ($n^{[l]}$, $n^{[l-1]}$)
- $b^{[l]}$ : ($n^{[l]}$, 1)
- $z^{[l]}$ : ($n^{[l]}$, 1)
- $a^{[l]}$ : ($n^{[l]}$, 1)

Vectorized across dataset
- $Z^{[l]}$ : ($n^{[l]}$, m)
- $A^{[l]}$ : ($n^{[l]}$, m)

Forward propagation in DNN:
- $Z^{[l]} = W^{[l]}A^{[l-1]} + b^{[l]}$, 
- $A^{[l]} = g^{[l]}(Z^{[l]})$
- $A^{[0]} = X$ 
- $A^{[L]} = \hat{y}$

Backward propagation in DNN:
- $dz^{[l]} = da^{[l]} * g'^{[l]}(z^{[l]})$
- $dW^{[l]} = dz^{[l]} * a^{[l-1]T}$
- $db^{[l]} = dz^{[l]}$
- $da^{[l]} = W^{[l]T} * dz^{[l]}$
- $dz^{[l]} = W^{[l+1]T}dz^{[l+1]} * g'^{[l]}(z^{[l]})$

Parameters: $W^{[l]}$, $b^{[l]}$

Hyperparameters: 
- $\alpha$ - learning rate 
- $L$ - number of hidden layers
- $n^{[l]}$ - number of units in each layer
- number of iterations
- choice of activation function

  
### Activation functions

sigmoid
$a(z) = \frac{1}{1 + e^{-z}}$
$\frac{dz}{d}a(z) = a(z)*(1 - a(z))$

hyperbolic tangent
$a(z) = \frac{e^{z} - e^{-z}}{e^{z} + e^{-z}}$
$\frac{dz}{d}a(z) = 1 - (a(z))^2$

Rectified Linear Unit (ReLU)
$a(z) = max(0, z)$
$\frac{dz}{d}a(z) = \begin{cases} 1 \quad \text{for z > 0} \\ 0 \quad \text{for z < 0} \end{cases}$

Leaky ReLU
$a(z) = max(\\frac{z}{100}, z)$
$\frac{dz}{d}a(z) = \begin{cases}1 \quad \text{for z > 0} \\ \frac{1}{100} \quad \text{for z < 0} \end{cases}$

  
For deep NNs, if there are no activation functions (identity activation function) then the result is as if there were no hidden layers. Only makes sense if problem is a regression problem.

`Sigmoid` should only be used in the output layer due to easier interpretability. For hidden layers, `tanh` is a better performing option. The default activation function should be (leaky)\`ReLU\`.

  

### NN practical tips

  

1. Initial parameters ($W^{[l]}$) should be random, not 0. They should be close to 0 (small) as for most activation functions this will make the gradient larger and speed up initial learning process.

  

#### Data splitting

  

1. Train set - for training models

2. Holdout / Cross-validation / Development set - for testing different types of models and hyperparameter tuning

3. Test set - for final assessment of the model

 \- Traditional split: 60% / 20% / 20%

 \- Modern split (for big data): up to 98% / 1% / 1%

4. Dev and test data should come from the same distribution

5. It might be OK not to have test set if unbiased performance measure is not needed

  

#### Bias / Variance

  

1. High bias - underfitting

 \- Train test error is high (against base error)

 \- Dev test error is high

 \- Ways of handling: bigger network, longer training, different NN architecture

2. High variance - overfitting

 \- Train test error is low

 \- Dev test error is high

 \- Ways of handling: more data, regularization, different NN architecture

  

  

  

  

## NumPy implementation

  

  

  

## TensorFlow