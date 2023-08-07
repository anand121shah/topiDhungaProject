
# Documentation

## Overview

This project involves the creation of an anomaly detection system based on sensor data. The models created can be used to detect anomalous sensor readings, which can be indicative of potential issues or failures.

## Models and Files

The following models/files were created during this project:

1. **Isolation Forest Model (`isolation_forest_model.pkl`):** This is a trained Isolation Forest model that can be used to detect anomalies in new sensor data.

2. **Standard Scaler (`standard_scaler.pkl`):** This is a Standard Scaler object that was used to standardize the features of the sensor data. It should be used to standardize any new data before making predictions with the Isolation Forest model or applying PCA.

3. **PCA object (`pca.pkl`):** This is a Principal Component Analysis (PCA) object that was used for dimensionality reduction on the sensor data. It can be used to apply PCA to new data.

## Using the Models

### Loading the Models

The models can be loaded in Python using the `joblib` library:

```python
from sklearn.preprocessing import StandardScaler
from sklearn.decomposition import PCA
from sklearn.ensemble import IsolationForest
import joblib

# Load the models
model = joblib.load('isolation_forest_model.pkl')
scaler = joblib.load('standard_scaler.pkl')
pca = joblib.load('pca.pkl')
```

### Preprocessing New Data

Any new data should be preprocessed in the same way as the training data before making predictions with the Isolation Forest model or applying PCA. This includes filling missing values with the column means and standardizing the data using the saved Standard Scaler.

Here is an example of how to preprocess new data:

```python
# Example new data
new_data = pd.DataFrame({
    'L_1': [0.32],
    'L_2': [0.24],
    'A_1': [0.11],
    'A_2': [0.76],
    'B_1': [0.97],
    'B_2': [0.65],
    #... ensure all features are included here
})

# Fill missing values with column means
new_data = new_data.fillna(new_data.mean())

# Standardize the data
scaled_new_data = scaler.transform(new_data)
```

### Predicting Anomalies

After preprocessing the new data, the Isolation Forest model can be used to predict whether each data point is an anomaly:

```python
predictions = model.predict(scaled_new_data)

# Interpret the predictions
if predictions[0] == 1:
    print("The data point is normal.")
else:
    print("The data point is an anomaly.")
```

This will return 1 for normal data points and -1 for anomalies.

### Applying PCA

After preprocessing the new data, the PCA object can be used to apply PCA to the data:

```python
principal_components = pca.transform(scaled_new_data)
```

This will return the principal components of the data, which are a linear combination of the original features.

## Notebooks

There are two Jupyter notebooks that provide step-by-step instructions on how the models were created and how they can be used:

1. `anomaly_detection.ipynb`: This notebook contains the steps performed for data preprocessing, anomaly detection using the Isolation Forest model, and feature engineering using PCA. It also includes the steps for saving and loading the models.

2. `model_testing.ipynb`: This notebook contains the steps for loading the saved models and using them to predict anomalies in new sensor data. 

The notebooks can be run in environments such as Jupyter Notebook, JupyterLab, or Google Colab.

## Summary

This project provides a framework for anomaly detection in sensor data. The trained models can be used to detect anomalous sensor readings and apply dimensionality reduction to new data. The provided Jupyter notebooks provide detailed instructions on how to use the models.
