# Emo-Track

A Sentiment Analysis model through Speech that can recognize various emotions in speech, like Calm, Happy, Sad, Angry, Fearful, Surprise, Disgust, and Neutral. The model achieves an impressive accuracy of 95.83%.

# Table of Contents
* Overview
* Dataset
* Model Architecture
* Results
* Confusion Matrix

# Overview
Sentiment analysis is a challenging task in the field of Natural Language Processing and Audio Signal Processing. This project aims to develop a model that can accurately classify emotions in speech. The model extract essential features from the audio and uses Support Vector Machine (SVM) technique to train the model on the features and their corresponding labels and predict the corresponding emotion category.

# Dataset
The SER model is trained on Ryerson Audio – Visual Database of Emotional Speech and Song (RAVDESS) dataset where the Emotional Speech Audio dataset is used. It contains 1440 audio files by 24 professional actors (12 Female, 12 Male). This dataset includes eight types of emotion audios viz. Calm, Happy, Sad, Angry, Fearful, Surprise, Disgust, and Neutral where each expression is produced at two levels of Emotional Intensity (Normal, Strong) except the Neutral which is only produced in Normal intensity.

File naming convention:
<p align="center">
    <img width="500" src="![image](https://github.com/aishi2/Emo-Track/assets/130057966/d199fcf6-71fc-4d6b-b11c-f72e57452a0c)" alt="File Naming Convention">
    <p align="center">Fig - File Naming Convention</p>
</p>
----image of file naming


<p align="center">
    <img width="500" src="https://user-images.githubusercontent.com/71036685/236631557-2042f780-aa75-4db3-8092-c66559248a78.png" alt="Dataset count chat">
    <p align="center">Fig - Dataset count chat</p>
</p>
----image of dataset chart

# Model Architecture
* From the dataset, three features are extracted
  - Mel-Frequency Cepstral Coefficients (MFCC) - Represents the short-term power spectrum of a sound signal. MFCC Coefficients, Delta Coefficients and Delta-Delta Coefficients are extracted.
  - Modulation Spectrogram - Represents the distribution of energy in the modulation frequency domain. 256 Number of Mel Filters are used to compute the Mel spectrogram.
  - Zero Crossing Rate (ZCR) - Rate at which a signal changes its sign. A high ZCR may indicate a noisy or percussive signal while A low ZCR indicate a smooth signal.
* Mean and Standard Deviation of all the features are taken into consideration.
* Dimensionality reduction is applied using Principal Component Analysis (PCA) by visualizing the Explained Variance Ratio Plot.

<p align="center">
    <img width="500" src="https://user-images.githubusercontent.com/71036685/236631557-2042f780-aa75-4db3-8092-c66559248a78.png" alt="Explained Variance Ratio Plot">
    <p align="center">Fig - Explained Variance Ratio Plot</p>
</p>
----image of variance ratio plot

* Standardization of feature set is done to ensure that all features are on a similar scale.
* Support Vector Machine (SVM) is used to train the model using 20 folds Stratified KFold Cross Validation.

<p align="center">
    <img width="500" src="https://user-images.githubusercontent.com/71036685/236631557-2042f780-aa75-4db3-8092-c66559248a78.png" alt="Training folds">
    <p align="center">Fig - Training folds</p>
</p>
----image of KFold training

* Achieved the best model with the accuracy of 95.83%.

# Results
The Emo-Track model achieves an accuracy of 95.83%. This high accuracy demonstrates the effectiveness of the model in accurately predicting emotions in speech. However, please note that the model's performance may vary depending on the input data and the specific context.
![Confusion Matrix](https://github.com/aishi2/Emo-Track/assets/130057966/2134e1e1-9385-4013-bb79-07b9777dcb44){:align=center}
# Confusion Matrix
<p align="center">
    <img width="500" src="![Confusion Matrix](https://github.com/aishi2/Emo-Track/assets/130057966/2134e1e1-9385-4013-bb79-07b9777dcb44)" alt="Confusion Matrix">
    <p align="center">Fig - Confusion Matrix</p>
</p>
