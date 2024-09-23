# ResNet18-Based Image Classification with PyTorch

## Objective
This project demonstrates how to use a pre-trained ResNet18 model for binary image classification using PyTorch. The task involves classifying images into two categories: **positive** and **negative**, based on the presence of specific features in the dataset (e.g., cracks in concrete).

## Dataset
The dataset used in this project contains two folders:
1. **Positive**: Images that contain cracks.
2. **Negative**: Images that do not contain cracks.

### Dataset Location
The dataset can be downloaded from the following link:
[Concrete Crack Image Dataset](https://s3-api.us-geo.objectstorage.softlayer.net/cf-courses-data/CognitiveClass/DL0321EN/data/images/concrete_crack_images_for_classification.zip)

Once downloaded, unzip the dataset and place it in the appropriate data directory for processing. The images are organized into two classes to facilitate binary classification.

## Model Architecture
The project uses a pre-trained **ResNet18** model for feature extraction. Key steps in building the model include:
1. **Loading ResNet18**: A pre-trained version of ResNet18 is loaded with weights from ImageNet.
2. **Output Layer Modification**: The final fully connected layer (`model.fc`) is replaced with a custom `nn.Linear` layer for binary classification (positive/negative).
   - Input features: 512 neurons (from ResNet18's last layer).
   - Output features: 2 (for binary classification).

### Model Summary
The modified ResNet18 model is printed to verify the architecture, with a linear output layer configured for 2-class classification.

## Training Process
The model is trained using a batch size of 100, with data loaders created for both training and validation datasets. Key components include:
1. **Loss Function**: Cross-Entropy Loss, as it's suitable for multi-class classification.
2. **Optimizer**: Adam optimizer, which adjusts learning rates dynamically during training.
3. **Validation**: Model accuracy is measured on the validation dataset to monitor overfitting and adjust hyperparameters as needed.

## Results
The model is trained and evaluated, with the objective of identifying several misclassified samples for further analysis. Screenshots and logs from the training and validation processes are included in the final report to illustrate performance.

## Conclusion
This project shows how to effectively fine-tune a pre-trained ResNet18 model for binary image classification tasks, specifically detecting cracks in images using PyTorch.
