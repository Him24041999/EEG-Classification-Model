# EEG Classification Model

## Project Overview

This project focuses on classifying Electroencephalogram (EEG) data to identify epileptic seizures using machine learning techniques. The goal is to develop robust models for detecting seizures and understanding neurological disorders by analyzing EEG recordings. The datasets used include the CHB-MIT EEG Database and the Bonn EEG Dataset, offering a comprehensive range of seizure types and non-seizure data.

## Data

- **File Format:** `.edf` (European Data Format)
- **Description:** Contains 916 hours of scalp EEG recordings from 24 individuals, sampled at 256 Hz.
- **Preprocessing:**
  - Visualization and extraction of 342 features.
  - Removal of columns with null counts > 50, leaving 207 features.
  - Conversion to CSV and cleaning of data, including handling missing values.
  - Creation of a final dataframe with file number, seizure number, start and end times.

## Feature Extraction

Features were extracted from both time and frequency domains to capture relevant patterns in EEG signals. This process is crucial for enhancing the classification model's ability to differentiate between seizure and non-seizure states.
![1](https://github.com/user-attachments/assets/d75f85f9-0b80-40be-8c16-ef29085882b6)


## Model Architecture and Training

### Logistic Regression

- **Description:** A fundamental linear model for binary classification that predicts the probability of an instance belonging to a specific class using a sigmoid function.
- **Training Details:**
  - Data Split: 80% training, 20% testing.
  - Standardization applied using `StandardScaler`.
  - Evaluation Metrics: Accuracy, Confusion Matrix, and Classification Report.

### Convolutional Neural Networks (CNNs)

- **Description:** Deep learning models designed for structured grid data (e.g., images). CNNs use convolutional layers to detect local patterns and pooling layers for down-sampling.
- **Training Details:**
  - Model Architecture: `Conv1D`, `MaxPooling1D`, `Flatten`, and `Dense` layers.
  - Output Layer: Binary classification with a sigmoid activation function.
  - Compilation: Binary cross-entropy loss and Adam optimizer.
  - Visualization: Training and validation accuracy and loss over epochs.

## Results and Discussion

### Logistic Regression

- **Accuracy:** 99%
- **Confusion Matrix:** 
  - True Negatives: 113
  - False Positives: 0
  - True Positives: 24
  - False Negatives: 1
- **Precision and Recall:** 
  - Non-Seizure Precision: 0.99, Recall: 1.0
  - Seizure Precision: 1.0, Recall: 0.96

### Convolutional Neural Network

- **Accuracy:** 79%
- **Confusion Matrix:**
  - True Negatives: 105
  - False Positives: 8
  - True Positives: 4
  - False Negatives: 21
- **Precision and Recall:**
  - Non-Seizure Precision: 83%, Recall: 0.93
  - Seizure Precision: 0.33, Recall: 0.16

**Model Performance:** The Logistic Regression model significantly outperformed the CNN model in both accuracy and precision.

## Future Work

1. **Enhance CNN Model:** Experiment with hyperparameters, architectures, and techniques like transfer learning.
2. **Temporal Data Analysis:** Explore Recurrent Neural Networks (RNNs) or attention mechanisms for better handling of time-dependent patterns.
3. **Model Integration:** Combine Logistic Regression with CNN or other models for improved predictions.
4. **Diverse Data:** Incorporate additional diverse EEG datasets to enhance model robustness and generalizability.
5. **Expert Collaboration:** Partner with neuroscience experts to refine feature selection and model understanding.

## Conclusion

This research demonstrates the application of data science and machine learning in the analysis of EEG data to detect epileptic seizures. The Logistic Regression model proved to be highly effective, while the CNN model showed promise but requires further improvement. The study underscores the potential of machine learning in advancing the understanding and detection of neurological disorders.


