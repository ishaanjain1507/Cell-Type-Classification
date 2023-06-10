# Cell-Type-Classification
- The main task was to classify 6 different types of cells using a basic 3-4 layered CNN.

## Data
- Due to storage constraints, the whole dataset can't be uploaded here. Though it can be downloaded from https://www.dropbox.com/s/bqtzrmi5l5ojbhh/cells.zip?dl=0
- The data is basically a folder of many grayscale images.
- A `.csv` file is also give which labels the Cells.

## Data Preparation
- The data is imported using `CV2` image by image and converted to array of shape (64, 64, 1) 
- All the features of the images were appended to a list `dataset` which is later converted to an array.
- The data is split into training and testing dataset using `sklear.model_selection.train_test_split`.
- the features are then converted to a 2D array from 3D array
- the label '6' is converted to 0 temporarely.

## Model 

- The model is a Sequential CNN based on TensorFlow.
- The layers are:
  - Flatten
  - Dense, 64 neurons, activation function as relu,
  - Dense, 32 neurons, activation function as relu,
  - Dense, 6 neurons, activation function as softmax
- The model is compiled with 'adam' optimizer andloss funtion as 'categorical_crossentropy'.
- The model is trained for 15 epochs.

## Evaluation and Metrics

- The true and predicted labels are plotted as bar graph.
- The wrong predictions in each label is also plotted.
- The confusion matrix is plotted as a heatmap
- TensorBoard was used to keep the log of accuracy and loss. That is also plotted. 
