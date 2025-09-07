# Brain-tumor
Brain Tumor Detection using VGG16 (Transfer Learning)

This project focuses on detecting brain tumors from MRI images using deep learning. By leveraging the power of VGG16, a pre-trained convolutional neural network, the model can effectively classify MRI scans as either showing a tumor or not.

1. Dataset

The dataset was downloaded from Kaggle (navoneel/brain-mri-images-for-brain-tumor-detection). It contains MRI brain images categorized into two classes:

Yes → Tumor present

No → No tumor

The images were extracted and prepared for training inside Google Colab.

2. Data Preprocessing

Each image was read using OpenCV and resized to 224×224 pixels, matching VGG16’s input requirements.

The images were stored as input features (X) and assigned labels (y → Tumor or No Tumor).

Labels were encoded into numerical values (0 = No tumor, 1 = Tumor) and then converted into categorical vectors.

Finally, the dataset was split into 67% training and 33% testing to evaluate performance.

3. Transfer Learning with VGG16

The VGG16 model, pre-trained on the ImageNet dataset, was used as the base.

The original classification layers were removed (include_top=False), keeping only the feature extraction layers.

All base layers were frozen to preserve pre-trained weights, while new custom layers were added for tumor classification.

4. Custom Layers

On top of VGG16, additional layers were added:

Global Average Pooling to reduce feature maps.

Dense layers with ReLU activation to learn deeper patterns.

A final softmax layer for binary classification (Tumor vs No Tumor).

5. Model Training

The model was compiled with the Adam optimizer, categorical crossentropy loss, and accuracy as the evaluation metric.

Training was performed for 5 epochs, with validation data used to track performance during training.

6. Evaluation & Results

The training process recorded both accuracy and loss for training and validation sets.

Graphs were plotted to visualize:

Training vs. Validation Accuracy

Training vs. Validation Loss

These plots helped assess whether the model was learning effectively or overfitting.
