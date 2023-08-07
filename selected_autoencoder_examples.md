
# Intro to Autoencoders - Selected Examples

Source: [TensorFlow.org](https://www.tensorflow.org/tutorials/generative/autoencoder)

---

## Image denoising

An autoencoder can be trained to remove noise from images. In this section, a noisy version of the Fashion MNIST dataset is used, where random noise is applied to each image. The autoencoder uses the noisy image as input, and the original image as the target, to train itself to denoise the images.

---

## Anomaly detection

In this example, an autoencoder is trained to detect anomalies on the ECG5000 dataset, which contains Electrocardiograms. The dataset has rhythms labeled either as normal or abnormal. The autoencoder is trained on the normal rhythms only, and then used to reconstruct all the data. The hypothesis is that abnormal rhythms will have a higher reconstruction error. A rhythm is classified as an anomaly if the reconstruction error surpasses a fixed threshold.

---

### Citation

"Intro to Autoencoders." TensorFlow. [Online]. Available: [TensorFlow.org](https://www.tensorflow.org/tutorials/generative/autoencoder). Accessed on [Date of Access].
