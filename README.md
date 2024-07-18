**Facial Expression Recognition**

**Introduction**
This project aims to classify the five expressions, angry, happy, neutral, sad, and surprised available in the VIRI database, and three different expressions,
fear, disgust, and happy available in the NVIE database.

**About**
It uses VIRI and NVIE databases with the names VIRI and NVIE which you can download from the link below:
https://github.com/naseemmuhammadtahir/raw-data.git

All the models are implemented using Pytorch 
**Process for training**
First, we import the VIRI and NVIE database and divided them into 3 parts, train-set, val-set and test-set by using 70%, 15% and 15% split-ratio. 
Then we create our model architectures. For visible modalities, we modified the ResNet-18 CNN architecture. In the final layer of ResNet-18, we incorporated several dropout layers, fully connected (FC) layers, and a SoftMax layer tailored to the visible dataset. 
For infrared modalities, again we modified the ResNet-18 CNN architecture. In the final layer of ResNet-18, we incorporated several dropout layers, fully connected (FC) layers, activation functions, batch norm layers and a SoftMax layer tailored to the infrared dataset. 
For visible and infrared, we combined the features pair-wise and again modified the final layer by incorporating several dropout, fully connected layers, batch norm layers and a softmax layer.

**Process for evaluation**
First, we loaded the test-set for both databases and then we reshape our image to 224 * 224 pixels to meet the requirements of our trained model and pass it as an input to our model. The output is a list containing probabilities, each for an emotion. The index of maximum probability from the list indicates the  emotion (0=Angry, 1=Happy, 2=Neutral, 3=Sad, 4=Surprise) for the VIRI database and (0=Happy, 1=Disgust, 2=Fear) for the NVIE database. We evalauted our moels for Accuracy, Precision, Recall and F1-Score. 
We also computed the CAM graphs to viusualize the important parts of the face using our proposed ResNet-18 model from the last layer. 



