# NLP-classification
text classification using Encoder decoder

Here we used two methos for the classification lstm and sequence and modeling

Keras classification

The general case: canonical sequence-to-sequence
In the general case, input sequences and output sequences have different lengths (e.g. machine translation) and the entire input sequence is required in order to start predicting the target. This requires a more advanced setup, which is what people commonly refer to when mentioning "sequence to sequence models" with no further context. Here's how it works:

A RNN layer (or stack thereof) acts as "encoder": it processes the input sequence and returns its own internal state.
Note that we discard the outputs of the encoder RNN, only recovering the state. 
This state will serve as the "context", or "conditioning", of the decoder in the next step.
Another RNN layer (or stack thereof) acts as "decoder": 
it is trained to predict the next characters of the target sequence, given previous characters of the target sequence.
Specifically, it is trained to turn the target sequences into the same sequences but offset by one timestep in the future,
a training process called "teacher forcing" in this context. Importantly, the encoder uses as initial state the state vectors from the encoder, 
which is how the decoder obtains information about what it is supposed to generate.
Effectively, the decoder learns to generate targets[t+1...] given targets[...t], conditioned on the input sequence.

Used Resouse:-

https://blog.keras.io/a-ten-minute-introduction-to-sequence-to-sequence-learning-in-keras.html

https://arxiv.org/pdf/1411.4389.pdf

DAta set link:-https://www.kaggle.com/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews
