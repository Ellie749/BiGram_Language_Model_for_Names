# Character Level Language Modeling

This approach focuses on training a  models for character-level language modeling.

### Character-Level Language Modeling:
Instead of working with words or phrases, the model operates at the character level.
It learns patterns between individual characters in a sequence. For example, it might learn that 'q' is often followed by 'u' in English


### Methods

This project explores different approaches to character level language modeling. The goal is to generate new names by training models on a dataset of existing names. Below is a detailed explanation of the three types of models used:

1. Probabilistic Model
This is the simplest model, based on probabilities derived from the dataset.<br>

It calculates the conditional probability of each character given the previous character.
For example, if the model has seen that the letter 'e' frequently follows 'h' in the dataset, it assigns a higher probability to 'e' as the next character after 'h'.
Limitations:
It only considers one previous character when predicting the next one, making it unable to capture long term dependencies or patterns in the data.
There's no learning mechanism. It merely counts occurrences and calculates probabilities.
It is not scalable.<br>

2. Single Neuron Model
This model uses a single artificial neuron trained with backpropagation to predict the next character.

The neuron receives one input: the encoding of the current character.
It outputs a prediction for the next character based on learned weights.
Backpropagation is used to adjust these weights during training, minimizing the prediction error.

Unlike the probabilistic model, this approach learns to generalize patterns from the data rather than relying solely on raw probabilities.

It still considers only one previous character, limiting its ability to understand sequences with longer dependencies.<br>

3. Multi-Layer Perceptron (MLP) Model
This model expands on the single-neuron approach by using a multi-layer perceptron (MLP), which is capable of considering multiple previous characters.

The input to the model is a sequence of n previous characters (encoded as vectors).
These inputs are passed through multiple layers of neurons, allowing the model to learn complex patterns and relationships in the data.
The output layer predicts the next character.

The MLP model can learn dependencies across a sequence of characters, making it more powerful than the previous two models.
It is capable of capturing nuanced structures in the names dataset, improving the quality of the generated names.

Training an MLP is computationally more intensive compared to the simpler models.