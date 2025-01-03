# COMP432 Project

# Project Description

This project uses deep learning in computer vision to solve two image classification tasks using Convolutional Neural Networks (CNNs). The primary focus is on applying a CNN backbone architecture to classify images from two real-world datasets.

### Task 1: Training a CNN for Colorectal Cancer Classification
We trained a CNN model (ResNet50) on the Colorectal Cancer dataset to classify tissue types into three categories:
- Smooth muscle (MUS)
- Normal colon mucosa (NORM)
- Cancer-associated stroma (STR)

We experimented by training and tuning the model's hyperparameters, evaluating the model performance using common evaluation metrics, then visualized feature extraction using t-SNE plots to analyze class separability.

### Task 2: Transfer Learning on Prostate Cancer and Animal Faces Datasets
The trained CNN encoder from Task 1 and a pre-trained ImageNet encoder were applied to:
- Prostate Cancer Classification: Classifying tissue types into Prostate Cancer Tumor Tissue, Benign Glandular Prostate Tissue, and Benign Non-Glandular Prostate Tissue.
- Animal Faces Classification: Classifying images into Cats, Dogs, and Wildlife Animals.

We used transfer learning to analyze feature representations, visualized feature extraction with t-SNE, then used logistic regression to classify the extracted features for each dataset.

## Results

### Colorectal Cancer Training Results

Using ResNet50 with the RMSProp optimizer showed the best performance:
- **Validation Accuracy:** Reached 93.75% after 10 epochs.
- **t-SNE Visualization:** Displayed strong class separability for all three classes.

### Prostate Cancer Transfer Learning Results

- **ImageNet Model:** Achieved near-perfect classification with clear class separability in t-SNE plots.
- **Colorectal Cancer Model:** Effectively separated the tumor class, but struggled with the non-gland and gland tissue types.

### Animal Faces Transfer Learning Results

- **ImageNet Model:** Produced high-quality features with clear class separation in t-SNE plots.
- **Colorectal Cancer Model:** Struggled with feature extraction, leading to mixed class embeddings in t-SNE and poor logistic regression performance (50% accuracy).
---
### Authors
- Tristan Lafleur (40245238)
- Nicholas Cook (40175800)
- Ion Turcan (40154098)
- Kenny Luo-Li (40237402)
- Youssef Morcos (40124441)
---
---
### Required Libraries
- ### **[`torch`](https://pytorch.org/docs/stable/index.html)**
- ### **[`torchvision`](https://pytorch.org/vision/stable/)**
- ### **[`numpy`](https://numpy.org/install/)**
- ### **[`sklearn`](https://scikit-learn.org/stable/install.html)**
- ### **[`matplotlib`](https://matplotlib.org/stable/#install)**
- ### **[`pandas`](https://pandas.pydata.org/getting_started.html)**
---
---
### Configuring for Local Machines
- In order to utilize the neural networks with GPUs, the [CUDA toolkit](https://developer.nvidia.com/cuda-downloads) must be compatible with the local machine and installed.
- Follow the instructions at [PyTorch's Start Locally](https://pytorch.org/get-started/locally/) page to configure your machine.
    - Select the appropriate OS and Package Manager for your system and Python environment
    - Select the Python language and choose a CUDA platform
---
---
### Notebooks
- **`[COMP432]_Corolectal_Cancer_Neural_Network.ipynb`**: Colorectal Cancer Pre-trained model
- **`[COMP432]_Prostate_Cancer.ipynb`**: Transfer learning analysis on the Prostate Cancer dataset
- **`[COMP432]_Animal_Faces_Transfer_Learning.ipynb`**: Transfer learning analysis on the Animal Faces dataset
---
---
### Training and Validating the Model

The notebooks demonstrate how to train and validate a ResNet50 model for different datasets classification using various optimizers. Each optimizer section is organized with hidden cells.

#### Available Optimizers

- **SGD + Momentum**  

- **RMSProp**  

- **SGD**  

- **Adam**
  
#### Instructions for Training

1. Adjust the hyperparameters to suit your specific computational resources according to the optimizer you will be using 

2. Navigate to the desired optimizer section in the notebook:
   - SGD + Momentum
   - RMSProp
   - SGD
   - Adam

3. Expand the section

4. Execute the training cells to start the training process. Validation results are displayed after each epoch.

---
---
### How to Test the Pre-trained Model
The notebooks provide functionality to test the pre-trained ResNet50 model on the test dataset. Follow the instructions below to perform inference,evaluate the model:

#### Instructions for Testing

1. **Locate the Testing Section**  
   Navigate to the section in the notebook corresponding to the optimizer used during training (e.g. `Adam`, `SGD`, `RMSProp`, etc.)

2. **Run the Test Inference Cell**  
   Execute the cells that have a test heading for testing the model. These cells use the pre-trained weights saved during training to perform inference on the test dataset.

3. **Output Metrics**  
   The following metrics will be displayed after testing:
   - **Loss and Accuracy**: The overall performance of the model on the test set.
   - **Confusion Matrix**: A visualization of the true versus predicted labels.
   - **Classification Report**: Detailed metrics such as precision, recall, F1-score, and support for each class.

4. **Generate t-SNE Visualizations**  
   - Use the feature extractor provided in the notebook to extract intermediate layer features from the model.
   - Generate t-SNE embeddings of the feature space.
   - Visualize the results using the provided scatter plot function, where each class is represented as a distinct cluster in 2D space.

5. **Evaluate the Results**  
   - Review the confusion matrix and classification report to identify any patterns or misclassifications.
   - Analyze the t-SNE plot to understand how well the model clusters features for different classes.

#### Notes

- Ensure the test dataset is correctly preprocessed using the same transformations applied during training.
- If running inference with a different optimizer or hyperparameter setting, confirm that the correct pre-trained weights are loaded.

---
---
### Obtaining the Datasets
- ### **[Colorectal Cancer Dataset](https://1drv.ms/u/s!AilzKc-njjP7mN0NOZvxl0TPAUxmig?e=K0TpeX)**
- ### **[Prostate Cancer Dataset](https://1drv.ms/u/s!AilzKc-njjP7mN0M_LjB5xeAydDsrA?e=0obzsx)**
- ### **[Animal Faces Dataset](https://1drv.ms/u/s!AilzKc-njjP7mN0LqoRZvUYONY9sbQ?e=wxWbip)**
---
---
