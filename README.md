# COVID-image-classification
COVID-image-classification


## Business and Data Understanding:

Stakeholders: 
- Medical professionals (e.g. doctors, nurses, radiologists) 
- Implement the algorithm into a user-friendly tool for medical professionals to easily upload X-ray images and receive a classification of COVID-19 or not
- Work with medical institutions, hospitals, and clinics to market and distribute the tool to areas with limited access to PCR testing or where PCR tests are not immediately available
- COVID-19 has infected over 400 million people and caused more than 5 million deaths worldwide as of March 2023. Source: World Health Organization

Business objectives:
- PCR testing, which is the most reliable diagnostic method for COVID-19, may not be readily available in some areas, leading to delayed diagnosis and treatment.
- For institutions with access to X-Ray or CT, develop an accurate model to predict COVID-19 based on image classification

## Data understanding:
-  The dataset contains X-ray and CT images of both Non-COVID and COVID cases.
The dataset has been augmented with different techniques to generate approximately 17,099 images. There are two main folders in the dataset, one for X-ray images and the other for CT images.
- The X-ray folder contains two sub-folders of 5,500 Non-COVID images and 4,044 COVID images.The CT folder also contains two sub-folders of 2,628 Non-COVID images and 5,427 COVID images.
- The dataset was published on June 12, 2020, and is currently in Version 3. The contributors to the dataset are Walid El-Shafai and Fathi E. Abd El-Samie. https://data.mendeley.com/datasets/8h65ywd2jr 


## Modeling

Baseline model: This model has two convolutional layers with 32 and 64 filters respectively, followed by a dense layer with 16 units and a sigmoid output layer. It uses a batch size of 64 and an early stopping callback with a minimum delta of 1e-2 and patience of 5. The loss function is 'binary_crossentropy'.

Model 1: This model is similar to the baseline model, but has an additional MaxPooling2D layer after the second convolutional layer, and a dense layer with 64 units before the output layer. It uses a batch size of 32 and trains for 10 epochs with no early stopping.

Model 2: This model is also similar to the baseline model, but has L2 regularization with a weight of 0.01 on the weights of the second and third convolutional layers, and the dense layer before the output layer. It uses a batch size of 32 and trains for 10 epochs with no early stopping. Additionally, it tracks precision and recall as additional metrics.

Model 3 (final model): This model has a more complex architecture, with four convolutional layers, each with 32 or 64 filters, followed by two dense layers with 256 units each, and a sigmoid output layer. It uses a batch size of 32 and trains for 20 epochs with no early stopping. The loss function is 'binary_crossentropy' and the optimizer is 'Adam'.
