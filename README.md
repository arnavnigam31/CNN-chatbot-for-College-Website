# Chatbot with CNN

This project is a chatbot implemented using a Convolutional Neural Network (CNN) for intent classification. It uses the `intents.json` file to learn and respond to user inputs based on predefined patterns and responses.

## Project Structure

- `intents.json`: Contains the training data for the chatbot, including patterns, responses, and tags.
- `new.py`: The main script that loads the data, trains the model, and provides a function for getting responses from the chatbot.

## Requirements

- Python 3.10
- TensorFlow
- NumPy
- Scikit-learn

## Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/arnavnigam31/CNN-chatbot-for-College-Website
   cd CNN-chatbot-for-College-Website
2. **Install the required packages:**
   ```bash
   pip install tensorflow numpy scikit-learn

3. **Run the chatbot script:**
   ```bash
     python new.py

## Model Architecture
1. **Embedding Layer**
     - `input_dim=2000:` The size of the vocabulary. This means the model will consider the top 2000 most frequent words in the dataset.
     - `output_dim=32:` The dimension of the dense embedding. Each word will be represented by a 32-dimensional vector.
     - `input_length=20:` The length of input sequences. All input sequences will be padded or truncated to this length.
2. **Convolutional Layer**
     - `filters=256:`The number of output filters in the convolution.
     - `kernel_size=10:` The length of the 1D convolution window.
     - `activation='relu':` The activation function applied to the layer’s output.

3. **Global Max Pooling Layer**
     - This layer downsamples the input representation by taking the maximum value over the time dimension, which reduces the input tensor to a fixed size                regardless of the input length.

4. **Fully Connected (Dense) Layer**

   - `units=256:` The number of neurons in the layer.
   - `activation='relu':` The activation function applied to the layer’s output.
  
5. **Output Layer**
   - `units=len(data['intents']):` The number of output neurons, which equals the number of unique intent tags.
   - `activation='softmax':` The activation function for multi-class classification. It outputs a probability distribution over the intent tags.
   
