- introduce non-linearity, allowing neural networks to model complex, non-linear relationships.
1. Sigmoid  Function :
   - maps any real valued number between (0,1), allowing it to be used in binary classification.
   - The function is **differentiable**.That means, we can find the slope of the sigmoid curve at any two points.
   - **softmax function** : more generalised logistic activation function used for multiclass classification
   - The function is **monotonic** but function’s derivative is not.
   - Drawbacks :
     - Gradient saturation and vanishing gradient problem - 
       - One of the major drawbacks of the sigmoid activation function is that it **saturates at high and low input values**. This means that as the input to the sigmoid function becomes very large or very small, the output of the function becomes very close to either 0 or 1.This can lead to the gradients becoming very small and can make it difficult to train deep learning networks using the sigmoid activation function. This is known as the **"vanishing gradient"** problem.
     - slower convergence / computationally inefficient
     - Exploding gradient problem might also occur ? How when and why ? -- NOT CONVINCED YET
     - not zero centered - 
       - This means that the **activations of the neurons in the network can be all positive or all negative,** which can cause problems when using certain optimization algorithms, such as gradient descent. #TODO understand HOW ?

2. Tanh Function:
   - range is (-1,1). It is **zero centered**
   - The advantage is that the negative inputs will be mapped strongly negative and the zero inputs will be mapped near zero in the tanh graph.The function is **differentiable** and is **monotonic** while its **derivative is not monotonic**.
   - still suffers from `vanishing gradient` problem

3. Rectified Linear Unit (ReLU) Function :
   - `ReLU(x)=max(0,x)`
   - addressed vanishing gradient problem faced by above two functions
   - However, outputs 0 for negative input values and leaves positive values unchanged, which decreases the ability of the model to fit or train from the data properly. That means any negative input given to the ReLU activation function turns the value into zero immediately in the graph, which in turns affects the resulting graph by not mapping the negative values appropriately.
   - function and it's derivative `both are monotonic in nature`

4. Leaky ReLU:
   - **range** of the Leaky ReLU is (-infinity to infinity).
   - function and it's derivative - both monotonic in nature
   - Leaky ReLU is a variant of ReLU that introduces a small, non-zero slope for negative inputs. This prevents complete saturation of negative values and is useful in scenarios where sparse gradients may occur.
   - - It is defined as max(αx, x), where x is the input and α is a small positive , which is a `hyperparamter`  defined before model training. 

5. Softmax Function:
   - activation function often used in the output layer of a neural network for multi-class classification problems which transforms the raw score outputs from the previous layer into probabilities that sum up to 1, giving a distribution of class probabilities.
   - Cross-entropy loss is a popular loss function for classification tasks, including multi-class classification. It measures the dissimilarity between the predicted probability distribution (often obtained by applying the softmax function to the raw output scores) and the actual label distribution.
   - `takes in a vector of real numbers and converts them into a probability distribution, where each element of the vector is transformed into a value between 0 and 1. The resulting values also sum up to 1, making it suitable for tasks like multiclass classification.`
   - converts logits or raw values into probabilities


Reference : 
[Colab Notebook](https://colab.research.google.com/drive/1grRyyStgDxWGe_yI15DUsWlW2UeELtUy?usp=sharing)
[ref 1](https://vinija.ai/concepts/activation/)