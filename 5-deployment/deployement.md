
# Anomaly Detection using Autoencoder

This repository contains code for detecting anomalies in sensor data using an autoencoder model. An autoencoder is a type of neural network used to encode data into a compressed representation, and then decode it back to the original form. By comparing the original data with its reconstructed version, we can detect anomalies.

## How it works

1. **Data Preparation:** A dummy example dataset with 25 features is created.
2. **Model Prediction:** The previously trained autoencoder model is loaded, and a prediction (or reconstruction) is made on the dummy data.
3. **Anomaly Detection:** The Mean Squared Error (MSE) between the original and reconstructed data is computed. If this error surpasses a certain threshold, the data is considered anomalous.

## Usage

# Create dummy data
example_data = np.random.rand(1, 25)

# Load the trained model (ensure the path is correct)
model_path = "anomaly_detection_model_dir"
loaded_model = tf.keras.models.load_model(model_path)

# Predict using the loaded model
reconstructed_data = loaded_model.predict(example_data)

# Calculate the Mean Squared Error (MSE) for anomaly detection
mse = np.mean(np.square(example_data - reconstructed_data))

# Define a threshold for anomaly detection (adjust based on your data)
threshold = 0.05

# Determine anomaly status
anomaly_status = "anomalous" if mse > threshold else "normal"

## Notes

- The threshold value provided (`0.05`) is hypothetical. Adjust it based on your specific dataset and requirements.
- For real-world applications, replace the dummy dataset with actual sensor data.
- Ensure the model path is correctly set to the location of your trained autoencoder model.
