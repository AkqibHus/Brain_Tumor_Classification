# Brain_Tumor_Classification
This code uses a deep learning model based on VGG19 for brain tumor classification in MRI images. The workflow begins with data loading and preprocessing using OpenCV and TensorFlow, where MRI images are resized, normalized, and augmented to increase the dataset's diversity.

The core model is VGG19, a pre-trained convolutional neural network that leverages transfer learning. Transfer learning allows the model to use patterns from large-scale image datasets, significantly improving training efficiency and accuracy on smaller medical image datasets. The top layers of the VGG19 model are fine-tuned specifically for this classification task, with additional layers added to optimize tumor classification.

Key steps include:

1) Data Loading and Preprocessing: Images are read, resized to fit the VGG19 input layer, normalized, and augmented through random rotations, shifts, and flips. This data is then split into training, validation, and test sets.

2) Model Definition and Transfer Learning: The VGG19 model is loaded with pre-trained weights. Top layers are customized for binary classification (tumor vs. no tumor), with additional fully connected layers added for fine-tuning. The final activation layer is configured with softmax for multi-class or sigmoid for binary output.

3) Model Training: The model is compiled with cross-entropy loss and optimized using Adam. It then undergoes training, using the augmented images. The model checkpoints and validation metrics track the best-performing weights to avoid overfitting.

4) Evaluation and Prediction: After training, the model is evaluated on test data to assess accuracy, precision, recall, and F1-score. Predictions are visualized on sample MRI images, where the model outputs "tumor" or "no tumor."

The final model achieves over 81% accuracy in classification, with clear application potential in aiding medical diagnosis of brain tumors from MRI scans.
