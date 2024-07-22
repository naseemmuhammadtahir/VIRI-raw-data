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

**Evaluation Method**
To comprehensively evaluate the performance of our proposed facial expression recognition model, we employed several standard metrics and performed extensive experiments on two publicly accessible datasets: VIRI and NVIE.
**Datasets**
VIRI Database: Contains 566 image pairings of five distinct facial expressions (angry, happy, neutral, sad, surprised) captured in visible and infrared modalities.
NVIE Database: Contains visible and infrared images from over 100 subjects, capturing six fundamental facial expressions (happy, sad, surprised, fear, rage, disgust).
**Experimental Setup**
Data Splitting: Each dataset was divided into training (70%), validation (15%), and test (15%) sets. Data augmentation techniques such as rotations, zooming, distortion, shear, and flipping were applied to the training sets to increase the diversity of the training examples and mitigate overfitting.
Training: The ResNet-18 model, modified with an attention mechanism, was trained separately on visible and infrared images, as well as on a combined dataset using an early fusion approach. We utilized the Adam optimizer with a CosineAnnealingLR scheduler, and set the batch size to 64. The loss function used for training was cross-entropy.
**Evaluation Metrics**
The following metrics were used to evaluate the performance of the models:
Accuracy: The ratio of correctly predicted samples to the total number of samples.
Precision: The ratio of true positive predictions to the total predicted positives.
Recall: The ratio of true positive predictions to the total actual positives.
F1-Score: The harmonic mean of precision and recall.



