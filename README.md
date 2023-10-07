# Chess Piece Classifier
A neural network-based classifier designed to discern the presence or absence of a brain tumor in MRI scans.

## Programming Languages/Libraries/Frameworks

TensorFlow, Python, Keras

## Data

Three datasets from Kaggle, labeled to distinguish between those exhibiting tumors and those devoid of them.



**Br35H :: Brain Tumor Detection 2020**

Link : [https://www.kaggle.com/datasets/s4lman/chess-pieces-dataset-85x85](https://www.kaggle.com/datasets/ahmedhamada0/brain-tumor-detection)

**Brain MRI Images for Brain Tumor Detection**

Link : https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection

****

Link:

## Project Description

This project in essence, uses a Convolutional Neural Network in order to classify images of chess pieces to their respective labelS. The classifier is enabled to detect whether a particular piece is a pawn, knight, bishop, queen or a king.

#### Data Splitting

Used the Zipfile Module to unzip the three image folders.

After unzipping the files, I organized them into two separate directories named training and validation. Through this, I merged all the folders together. Following that, I divided these combined images between the training and validation directories, such that 80% of the images were placed in the training directory, while the remaining 20% were allocated to the validation directory.

#### Image Processing

I used **ImageDataGenerator** from *tensorflow.keras.preprocessing.image* to augment the images to virtually increase the size of the dataset. I added parameters in order to horizontally flip the image, change the brightness, zoom in or zoom out, shift width and height, and other augmentations.

Once the images were augmented, I created generators in order to flow the images from the given directories.

#### Model Architecture

The model at hand uses 4 Convolutional Layers (coupled with L2 Regularizers), followed by Max Pooling layers. There are Batch Normalization layers that are also used to avoid overfitting and to accelerate convergence.
 
Once the preprocessing is done, the pixels are flattened and passed into the Neural Network. It is then followed by three layers of Neurons with 'relu' activation, followed by a final dense layer of a single neuron with a sigmoid activation corresponding to the output.

The network is finally compiled using the loss function **binary_crossentropy** and the optimizer **adam** 

Here is a diagrammatic representation of the Neural Network Model:

<div align="center">
  <img src = "https://github.com/golgiwaffles/Brain-Tumor-Identifier/blob/main/brain_model.h5.png" width = "137px" height = "1396px" />
</div>

#### Output

The model is fitted with the training set for a 100 epochs.
Once the model is trained, there is a section where you can upload a MRI scan of the brain, and the model identifies whether the scan comprises of a tumor or not.

## Contact
**Name**: Skanda Vyas Venkatraman Srinivasan

**Email**: skandavyas20@gmail.com





