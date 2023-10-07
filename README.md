# Chess Piece Classifier
A neural network-based classifier designed to discern the presence or absence of a brain tumor in MRI scans.

## Programming Languages/Libraries/Frameworks

TensorFlow, Python, Keras

## Data

Three datasets from Kaggle, labeled to distinguish between those exhibiting tumors and those devoid of such abnormalities. 

**Br35H :: Brain Tumor Detection 2020**

Link : [https://www.kaggle.com/datasets/s4lman/chess-pieces-dataset-85x85](https://www.kaggle.com/datasets/ahmedhamada0/brain-tumor-detection)

## Project Description

This project in essence, uses a Convolutional Neural Network in order to classify images of chess pieces to their respective labelS. The classifier is enabled to detect whether a particular piece is a pawn, knight, bishop, queen or a king.

#### Data Splitting

Used the Zipfile Module to unzip the image file.

Once the file was unzipped, I created two directories called training and validation, with subdirectories labelling each chess piece. I then shuffled the images in the original data files and transferred them such that 20% of the data went to the validation set, and 80% went to the training set.

#### Image Processing

I used **ImageDataGenerator** from *tensorflow.keras.preprocessing.image* to augment the images to virtually increase the size of the dataset. I added parameters in order to horizontally flip the image, change the brightness, zoom in or zoom out, shift width and height, and other augmentations.

Once the images were augmented, I created generators in order to flow the images from the given directories.

#### Model Architecture

The model at hand uses 3 convolutional layers in order to extract features of the data, followed by Pooling. Batch Normalization is done after each convolution in order to accelerate convergence. Once the preprocessing is done, the pixels are flattened and passed into the Neural Network. It is then followed by three layers of Neurons with 'relu' activation, followed by a final dense layer with a softmax activation corresponding to the output.

The network is finally compiled using the loss function **categorical_crossentropy** and the optimizer **adam** 

Here is a diagrammatic representation of the Neural Network Model:

<div align="center">
  <img src = "https://github.com/golgiwaffles/Chess-Piece-Classifier/blob/main/Chessmodel.h5.png" width = "137px" height = "1396px" />
</div>

#### Output

The model is fitted with the training set for a 100 epochs.
Once the model is trained, there is a section where you can upload an image of a chess piece, and the model guesses which chess piece it is.

## Contact
**Name**: Skanda Vyas Venkatraman Srinivasan

**Email**: skandavyas20@gmail.com





