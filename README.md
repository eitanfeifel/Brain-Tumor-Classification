# Brain-Tumor-Classification
Brain Tumor Classification using Xception Model and a custom CNN Model

# Brain Tumor Classification with Xception and Custom CNN Models

This project provides a comprehensive solution for brain tumor classification based on MRI scans. It uses deep learning models—`Xception` and a custom `CNN` model—with options for Transfer Learning (TL) and Transfer Learning with Cross-Validation (TL + CV). Users can upload an MRI image, select model configurations, and get predictions and saliency maps that visually indicate the regions of the brain the models focused on during classification.

## Project Overview

The application offers a `Streamlit` UI to simplify the process of model inference and visualization. The UI displays side-by-side comparisons of the `Xception` and `Custom CNN` model predictions, along with saliency maps that highlight critical regions in the MRI scans. This approach assists medical practitioners in identifying brain tumor classes, including:
- **Glioma**
- **Meningioma**
- **No tumor**
- **Pituitary**

## Models and Training

### 1. Xception Model
The `Xception` model is a pre-trained deep learning model that has shown high performance on various image classification tasks. This model is loaded with `ImageNet` weights and fine-tuned for brain tumor classification using Transfer Learning.

### 2. Custom CNN Model
A custom `CNN` model based on the `VGG16` architecture is developed specifically for this task. The custom model has two configurations:
   - **Transfer Learning (TL)**: Only selected layers of the `VGG16` model are fine-tuned, while others remain frozen.
   - **Transfer Learning with Cross-Validation (TL + CV)**: This version applies cross-validation to increase robustness, training with different subsets of the data to improve generalization.

Both models are trained to classify MRI images into one of the four classes.

## User Interface Features
The application has a user-friendly interface built with Streamlit. Below are the main features:

### 1. Image Upload
Users can upload an MRI image file in `.jpg`, `.jpeg`, or `.png` format. Once uploaded, the image is displayed in the UI for confirmation before processing.

### 2. Model Selection and Cross-Validation Toggle
- **Xception Model**: This model provides predictions based on a pre-trained Xception architecture. The output includes the predicted class, confidence score, and a saliency map highlighting regions of interest in the MRI scan.
- **Custom CNN Model**: Configurable to operate in two modes—Transfer Learning (TL) or Transfer Learning with Cross-Validation (TL + CV). Users can toggle between these modes by checking the "Cross Validation" checkbox, which dynamically updates the model type.

### 3. Side-by-Side Model Comparisons
Both the Xception and Custom CNN models display their predictions in a side-by-side format. This layout allows for direct comparison between the models, helping users assess differences in model confidence and predictions.

Each model section includes:
- **Predicted class and confidence score**
- **Bar chart** displaying confidence percentages for each class
- **Saliency map** indicating significant brain regions that contributed to the model's prediction

### 4. Explanation Generation
The application provides an AI-driven explanation based on the predictions and saliency maps from both models. This explanation interprets the models' areas of focus and gives a possible diagnosis.

### 5. Similar Historical Cases
Based on the uploaded image's embedding, the app retrieves the top three similar historical cases from the dataset.

Each similar case is displayed with:
- The **class label** of the similar case
- The **similarity score**
- The **MRI image** of the historical case for visual comparison

## Usage Example
1. **Upload an MRI Image**: Upload an MRI image of the brain to classify.
2. **Select Model Configuration**: Optionally toggle the "Cross Validation" option under the Custom CNN model to enable or disable Cross-Validation.
3. **View Predictions and Saliency Maps**: The app displays predictions from both models, with saliency maps highlighting the regions each model focused on.
4. **Read the Explanation**: A generated explanation provides insights into the models’ predictions, focus areas, and diagnosis recommendations based on similar cases.
5. **Analyze Similar Historical Cases**: Review historical cases that are similar to the uploaded MRI, along with similarity scores and class labels.

## Dependencies
- **tensorflow** and **keras** for deep learning models
- **streamlit** for building the user interface
- **google.generativeai** for generating explanations (requires API key)
- **sklearn** for similarity calculations
- **opencv-python** for image processing
- **pandas** and **numpy** for data handling and manipulation

