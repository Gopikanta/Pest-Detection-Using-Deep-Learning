🐛 Pest Detection using Deep Learning
📖 Overview

This project aims to identify and classify agricultural pests using Deep Learning. It leverages a MobileNetV2 model trained on a publicly available pest dataset to assist farmers in early pest detection, reducing crop loss and improving productivity. A Gradio interface is integrated for real-time predictions.


📊 Dataset

Source: Kaggle - Pest Dataset - https://www.kaggle.com/datasets/simranvolunesia/pest-dataset

Type: Image dataset

Classes: aphids, armyworm, beetle, bollworm, grasshopper, mites, mosquito, sawfly, stem borer

Training images: 300 per class

Testing images: 50 per class

⚙️ Project Workflow

Upload & Extract Dataset

The dataset is uploaded and extracted in Google Colab.

Data Preprocessing

Images are resized to 224×224 pixels.

ImageDataGenerator is used for normalization and augmentation (rotation, zoom, flip, etc.).

Model Architecture

Base Model: MobileNetV2 (pretrained on ImageNet)

Added Layers:

GlobalAveragePooling2D

Dense (128 units, ReLU, L2 regularization)

Dropout (0.6)

Output layer (Softmax)

Training Strategy

Phase 1: Train only top layers (base model frozen).

Phase 2: Fine-tune last 20 layers with a lower learning rate.

Early stopping and learning rate reduction used to prevent overfitting.

Evaluation

Validation Accuracy: ~78% after fine-tuning

Test Accuracy: 92.89%

Deployment (Gradio App)

Interactive web interface for uploading pest images and getting instant predictions.

🧠 Technologies Used

Python

TensorFlow / Keras

MobileNetV2 (Transfer Learning)

Gradio (for deployment)

Google Colab

| Metric              | Value      |
| ------------------- | ---------- |
| Validation Accuracy | ~78%       |
| Test Accuracy       | **92.89%** |



💡 Future Enhancements

Add more pest species and image samples.

Implement real-time mobile app integration.

Use ensemble models for improved accuracy.


