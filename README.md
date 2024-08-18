# Urban Green Space Identification Using CNNs
Authors: Tyler Brown, Artem Minakow, Elena Putilova, Jördis Strack

## Goal

The primary objective of this project is to identify green areas and land use changes in cities over time using Convolutional Neural Networks (CNNs) applied to satellite and aerial imagery. This approach aids urban planners and environmental researchers in understanding the dynamics of urban growth and environmental sustainability.

## Data

Satellite Imagery: ESA’s Sentinel-2 mission.
Labels: OpenStreetMap (used to train the model).
Area of Interest

Location: Wuhan, China.
Bounding Box Coordinates:
North Latitude: 30.770277
South Latitude: 30.314773
East Longitude: 114.629974
West Longitude: 113.935089

Time Period: May to August of 2022.

## Model Architecture

The model implemented is a Convolutional Neural Network (CNN) specifically designed for image segmentation tasks, following a U-Net structure:
Encoder (Downsampling Path): Captures high-level features.
Bottleneck: Connects the encoder and decoder, capturing the context.
Decoder (Upsampling Path): Reconstructs the image from high-level features with precise localization.
This U-Net model is well-suited for binary image segmentation tasks, classifying each pixel as belonging to either a specific object class or the background. The architecture utilizes skip connections to maintain high-resolution features, leading to accurate and detailed segmentation results.

Total Layers: 25
Total Parameters: 1,862,849

## Hyperparameters

Batch Size: 10 (the model processes 10 samples at a time).
Epochs: 70 (early stopping triggered at 51 epochs with patience parameter set to 5).
The training and validation loss converged to low values by epoch 51, suggesting that the model had reached optimal performance.
Learning Rate: 0.001 (controls the step size at each iteration while moving toward a minimum of the loss function).
Regularization Parameter: 0.0001 (adds a penalty to the loss function proportional to the magnitude of the weights, helping to prevent overfitting).

## Model Performance

Accuracy: 0.9626
Precision: 0.9314
Recall: 0.9068
F1 Score: 0.9189
Total Proportion of Green Space Areas in Labeled Samples: 0.2355
