# Final-Master-Project-Emotion-detection-in-audio

In this project, we aim to generate a model capable of predicting human emotions in speech. To do so, we will use ASR (Automatic Speech Recognition) technology, which is also used for real-time transcription of the human voice. 
We will use different Machine Learning models with which we will train the neural networks so that the machine will be able to accurately predict what emotions the person is expressing.

For the first model we will use Mel's representation, which is exactly the spectrogram figure shown in the data description. The conversion process consists of 4 distinct phases. 
In these phases, what the model does is to take the input audio signal, which is usually a sequence of amplitude values over time, and transforms it into a logarithmic scale.  
The adjustments we have made are as follows:
We created functions to add random noise to prevent overfitting, as we make it harder for the model during learning.
We also added temporal displacement to simulate variations in synchronisation so that it does not learn to generalise the audios.
We transform the audio to a Mel spectrogram (mentioned above).
We added 2 recurrent layers, these layers are a type of neural network specific for processing sequential data, which allows them to remember previous information and use it to influence future inputs.
The last layer is a dense/feed forward/hidden layer that is connected to all the neurons in the previous layer. They are used to learn high-level patterns.

The second model we will use is a Transformer called Wav2Vec2. It is designed for Automatic Speech Recognition (ASR) and developed by Facebook AI. 
This model has been trained with 50,000 hours of unlabelled audio. Its main goal is to train and learn from large amounts of data and then be able to tune on smaller amounts of labelled data. 
In this project, we will perform Fine-tuning. This technique consists of taking a pre-trained model and adapting it for a specific new task.
During fine-tuning, we have made adjustments such as batch size, which is the amount of training examples that the model processes in each iteration before updating the weights.
Along with the training arguments, we found the parameters of the Training Arguments object, which control the learning rate, the evaluation and saving strategies.
Before implementing the Wav2Vec2-Large model, we tried the Wav2Vec2-base, but when we saw that the predictions were not good, we opted to use the Large model.
