
# Anomaly Detection in Sensor Data

This repository contains the files for a project on anomaly detection in sensor data.

## Files in this repository

- `dataFolder.zip`: This zip file contains the sensor data used in this project.

- `anomaly_detection.ipynb`: This Jupyter notebook contains the steps performed for data preprocessing, anomaly detection using the Isolation Forest model, and feature engineering using PCA. It also includes the steps for saving and loading the models.

- `model_testing.ipynb`: This Jupyter notebook contains the steps for loading the saved models and using them to predict anomalies in new sensor data.

- `isolation_forest_model.pkl`: This file is the trained Isolation Forest model.

- `standard_scaler.pkl`: This file is the Standard Scaler used to standardize the features.

- `pca.pkl`: This file is the PCA object used for dimensionality reduction.

## Usage

First, unzip `dataFolder.zip` to get the sensor data.

The `anomaly_detection.ipynb` notebook includes the steps for loading and preprocessing the data, training the Isolation Forest model, and applying PCA.

The `model_testing.ipynb` notebook includes the steps for loading the saved models and using them to predict anomalies in new sensor data. You can replace the example new data in this notebook with your own data.

You can load the saved models in Python using the joblib library:

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

The `model` object is the trained Isolation Forest model, which can be used to predict anomalies in new data. The `scaler` object is used to standardize the features, and the `pca` object is used to apply PCA to the data.

