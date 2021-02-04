# An implementation of a basic retrieval-based chatbot

Chatbots have become increasingly popular to make it easy for users to find the information they need and help reduce costs in customer service. In this project, I took on the challenge of creating a retrieval-based chatbot that responds via WhatsApp using the Twilio WhatsApp Sandbox API. The goal of this project was to apply deep learning to the dataset I constructed manually that mimics my own personality and style of interaction.

## Building the Dataset
* In order to implement my own personality into the deep learning model I decided to construct my own dataset in JSON format. The inputs of the dataset were:
    * tags - the class/category of interaction e.g. Hello, Goodbye, Thanks, Education, Hobbies etc.
    * patterns - a list of questions / phrases from the user e.g. Hello, Hi, What is your name? etc.
    * responses -  a list of responses from the chatbot e.g. Hey, Good to see you again, Aiden etc.
    
## Data Preparation
* Using the nltk library, tokenization and lemmatization was performed for each of the patterns in the dataset
* Each of the words and tags were stored in separate lists and then saved as a pickle file
* To transform the text into vectors the Bag of Words model was used (BoW). Given the simplicity of the dataset this was deemed to be the most efficient method to transform the text into vectors. For a much larger dataset the Term Frequency-Inverse Document Frequency (TF-IDF) statistic would potentially be a more accurate method of feature extraction.
* Given the small size of the dataset, no a validation or testing datasets were constructed.

## Modelling
* A neural network with one hidden layer was considered using TensorFlow with 128 neurons in the first layer, 64 in the second layer and an ouptut layer consisting of the number of neurons equal to the number of classes. The activation function used was relu for the first two layers and softmax for the output layer. Backpropagation was carried out using stochastic gradient descent.
<img src="https://github.com/aidenaslam/Predicting-Heart-Disease-in-Patients/blob/master/Figure%204.png" width="150" height="300" />
