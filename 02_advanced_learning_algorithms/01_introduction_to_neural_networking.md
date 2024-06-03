# Introduction to Neural Networks

## What is a Neural Network?
A neural network is a computational model inspired by the way biological neural networks in the human brain process information. It consists of layers of interconnected nodes (neurons), where each connection has an associated weight.

## Basic Components
- **Neuron (Node):** The basic unit of a neural network that processes input and produces an output.
- **Weight ($`w`$):** A parameter that adjusts the input's influence on the neuron's output.
- **Bias ($`b`$):** An additional parameter added to the input to adjust the output along with the weights.
- **Activation Function ($`\sigma`$):** A function that transforms the neuron's output to introduce non-linearity.

## Neural Network Structure
- **Input Layer:** Receives the input data.
- **Hidden Layers:** Intermediate layers that process the inputs.
- **Output Layer:** Produces the final output.

### Example of a Simple Neural Network
Consider a neural network with one hidden layer.

### Notations
- $`x`$: Input
- $`w`$: Weight
- $`b`$: Bias
- $`\sigma`$: Activation Function
- $`a`$: Activation (output of a neuron)

## Working of a Neural Network
1. **Forward Propagation:**
   - Compute the weighted sum of inputs and biases.
   - Apply the activation function to the weighted sum.

   For a single neuron:
   $`a = \sigma(w \cdot x + b)`$

2. **Training a Neural Network:**
   - **Loss Function:** Measures the difference between the predicted output and the actual output.
   - **Backpropagation:** Adjusts the weights and biases to minimize the loss function using gradient descent.

## Example: Image Classification (1 or 0)
Let's classify images containing either the digit 1 or 0.

### Step-by-Step Example
1. **Input Layer:**
   - The input is an image represented as a vector of pixel values (e.g., $`x`$).

2. **Hidden Layer:**
   - Each neuron in the hidden layer calculates a weighted sum of inputs plus bias and applies the activation function.
   $`a^{(1)} = \sigma(W^{(1)} \cdot x + b^{(1)})`$

3. **Output Layer:**
   - The output neuron provides the final classification result.
   $`a^{(2)} = \sigma(W^{(2)} \cdot a^{(1)} + b^{(2)})`$

### Example Calculation
Assume the following simple neural network:
- Input layer with 2 neurons (for simplicity).
- One hidden layer with 2 neurons.
- Output layer with 1 neuron (binary classification: 1 or 0).

Given:
- Input: $`x = \begin{bmatrix} 0.5 \\ 0.2 \end{bmatrix}`$
- Weights: $`W^{(1)} = \begin{bmatrix} 0.1 & 0.2 \\ 0.3 & 0.4 \end{bmatrix}, W^{(2)} = \begin{bmatrix} 0.5 \\ 0.6 \end{bmatrix}`$
- Biases: $`b^{(1)} = \begin{bmatrix} 0.1 \\ 0.1 \end{bmatrix}, b^{(2)} = \begin{bmatrix} 0.1 \end{bmatrix}`$
- Activation Function: Sigmoid ($`\sigma(x) = \frac{1}{1 + e^{-x}}`$)

1. **Hidden Layer Calculation:**
   $`
   a^{(1)} = \sigma(W^{(1)} \cdot x + b^{(1)})
   = \sigma\left(\begin{bmatrix} 0.1 & 0.2 \\ 0.3 & 0.4 \end{bmatrix} \cdot \begin{bmatrix} 0.5 \\ 0.2 \end{bmatrix} + \begin{bmatrix} 0.1 \\ 0.1 \end{bmatrix}\right)
   = \sigma\left(\begin{bmatrix} 0.1 \cdot 0.5 + 0.2 \cdot 0.2 \\ 0.3 \cdot 0.5 + 0.4 \cdot 0.2 \end{bmatrix} + \begin{bmatrix} 0.1 \\ 0.1 \end{bmatrix}\right)
   = \sigma\left(\begin{bmatrix} 0.17 \\ 0.27 \end{bmatrix} + \begin{bmatrix} 0.1 \\ 0.1 \end{bmatrix}\right)
   = \sigma\left(\begin{bmatrix} 0.27 \\ 0.37 \end{bmatrix}\right)
   = \begin{bmatrix} \sigma(0.27) \\ \sigma(0.37) \end{bmatrix}
   = \begin{bmatrix} 0.567 \\ 0.591 \end{bmatrix}
   `$

2. **Output Layer Calculation:**
   $`
   a^{(2)} = \sigma(W^{(2)} \cdot a^{(1)} + b^{(2)})
   = \sigma\left(\begin{bmatrix} 0.5 & 0.6 \end{bmatrix} \cdot \begin{bmatrix} 0.567 \\ 0.591 \end{bmatrix} + 0.1\right)
   = \sigma(0.5 \cdot 0.567 + 0.6 \cdot 0.591 + 0.1)
   = \sigma(0.2835 + 0.3546 + 0.1)
   = \sigma(0.7381)
   = 0.676
   `$

The final output $`0.676`$ suggests the image is more likely to be classified as 1 (assuming a threshold of 0.5).

## Conclusion
Neural networks process inputs through layers of interconnected neurons, using weights, biases, and activation functions to make predictions. Understanding these basics helps in building more complex models for tasks like image classification.
