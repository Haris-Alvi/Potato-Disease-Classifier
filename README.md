# Potato Disease Classifier

A deep learning-based image classification system for detecting diseases in potato leaves. The project uses a **Convolutional Neural Network (CNN)** to classify potato leaf images into three categories: **Early Blight, Late Blight, and Healthy**.

An interactive web-based interface was developed using **Gradio**, allowing users to upload a potato leaf image and receive a predicted disease class along with its confidence score.

## Project Overview

Early and accurate identification of plant diseases can help support agricultural decision-making. This project demonstrates how a trained CNN model can be integrated into an accessible web application so that users without machine learning expertise can interact with the model.

The trained model was developed using **1,722 potato leaf images** across three classes:

* Potato Early Blight — 800 images
* Potato Late Blight — 800 images
* Healthy Potato Leaves — 122 images

The CNN architecture consists of convolutional blocks with batch normalization and max-pooling layers, followed by dense layers and dropout for regularization. The model achieved **over 96% validation accuracy** according to the project report.

## Classes

| Class        | Description                            |
| ------------ | -------------------------------------- |
| Early Blight | Potato leaves affected by Early Blight |
| Late Blight  | Potato leaves affected by Late Blight  |
| Healthy      | Healthy potato leaves                  |

## Application Workflow

```text
User uploads potato leaf image
            ↓
Image resized to 128 × 128
            ↓
Pixel values normalized to 0–1
            ↓
Batch dimension added
            ↓
CNN model performs prediction
            ↓
Highest-probability class selected
            ↓
Class + confidence displayed
```

## Gradio Interface

The project uses **Gradio** to provide a simple web-based interface.

Users can:

1. Upload a potato leaf image
2. Submit the image for prediction
3. View the predicted disease
4. View confidence scores for the available classes

## Image Preprocessing

Before being passed to the CNN, uploaded images undergo the following preprocessing:

* Resize to **128 × 128 pixels**
* Convert the image into a NumPy array
* Normalize pixel values from `0–255` to `0–1`
* Add a batch dimension

This ensures that the input matches the format used during model training.

## Technologies Used

* Python
* TensorFlow / Keras
* NumPy
* Gradio
* PIL
* Convolutional Neural Networks (CNN)

## Running the Application

Install the required dependencies:

```bash
pip install tensorflow numpy gradio pillow
```

Run the application:

```bash
python app.py
```

> Replace `app.py` with the actual Python filename in the repository if it is different.

The Gradio interface will launch locally in a web browser.

## Model Performance

According to the project report, the CNN achieved:

**Validation Accuracy: >96%**

The model was evaluated across the three potato leaf categories.

## Limitations

The model's predictions depend on the quality and characteristics of the training data. Performance may be affected by:

* Unusual lighting conditions
* Different camera angles
* Unusual leaf stages
* Images that do not contain potato leaves

The current application also does not include explicit handling for non-potato images.

## Future Improvements

Potential improvements include:

* Input validation for non-potato images
* Confidence threshold warnings
* Batch image prediction
* Model explainability
* Prediction history
* Improved dataset diversity
* Deployment as a publicly accessible application

## Disclaimer

This project was developed as an academic machine learning project. Predictions are intended for demonstration and educational purposes and should not be considered a substitute for professional agricultural diagnosis.
