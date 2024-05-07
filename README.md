# Precipitation-Forecasting-Using-Meteorological-and-Satellite-Cloud-Image-Data

## Overview

This project focuses on developing a sophisticated hybrid deep learning model that merges deep-CNN and deep-RNN architectures to predict precipitation classes using meteorological data and satellite images. Leveraging 48-hour sequences of meteorological data and optimized image processing, the model accurately forecasts precipitation intensity and categorizes it into 'no', 'low', 'medium', and 'high' classes. The integration of satellite data from Lake Michigan and weather station data significantly enhances predictive capabilities, particularly for Lake Effect precipitation events, enabling dependable forecasting up to three days in advance.

## Methodologies

### Notebook 1: Rainfall-meteo-image-full-data-eda-preprocessing

**Data Handling:** Processed extensive meteorological data and cloud imagery from October 2014 to March 2017, focusing on the most complete and recent data after identifying missing data segments notably from October 2011 to November 2011.

**Feature Engineering:** Transformed wind direction and speed into vector components (Wx, Wy) to simplify the model’s interpretation of wind factors, integrating both magnitude and direction, pivotal in predicting rainfall.

### Notebook 2: Model_training_handling_ClassImbalance

**Class Imbalance Strategies:** Applied five distinct strategies to address class imbalance without disrupting the temporal sequence of data:

1. Employing No Bias
2. Introducing Initial Bias
3. Applying Class Weights
4. Combining Bias and Class Weights
5. Using Categorical Focal Loss

**Data Segmentation:** Segmented data from 2014 to 2017 into six-month intervals, increasing recorded instances of rainfall from 8% to 30%, effectively enhancing the dataset's utility for training purposes.

### Notebook 3: Hybrid Models (3.1, 3.2, 3.3)

**Model Architecture:** Explored a hybrid model combining CNN for spatial image analysis and RNN for temporal sequence forecasting. Resolved sample mismatch issue between CNN and RNN inputs by aligning sample sizes across both data inputs.

### Model Development and Evaluation

Successfully trained the hybrid model, showing promising improvements in predictive accuracy. Trained models for different prediction durations, including very-next-day, after 1 day, and after 2 days. Key metrics include accuracy and recall for predicting precipitation classes.

## Key Findings

- Identified and addressed model mistakes related to concatenating outputs and passing label outputs during model fitting.
- Showed improvements in recall for predicting after 2 days, particularly for high and medium rain classes.
- Achieved consistent accuracies across models (~42-50%), highlighting the effectiveness of the developed hybrid model.

## Tools and Skills

- Deep learning: CNN, RNN
- Data preprocessing: Feature engineering, data segmentation
- Model training and evaluation
- Handling class imbalance
- Tools: Python, TensorFlow, Keras, NumPy, Pandas, Matplotlib

## Future Directions

- Explore further enhancements to model architecture and training strategies.
- Investigate additional data sources and features for improved predictions.
- Collaborate with domain experts for real-world applications and validation.