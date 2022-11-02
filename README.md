Recyclable Trash Classification Report

**Intro**:
This recyclable trash classification project aims at applying convolutional neural network(CNN) with datasets available in Kaggle. CNN is one of the most basic, yet well-known and effective, algorithms used in the deep learning field. Many of the advanced and more recent algorithms used in vision evolved from CNN, improving concepts and architectures of kernels, filters, layers, and feature maps.  The objective of this project is to detect images that are given as inputs and identify the type of trash that is displayed in the image. When the image is detected, the output prints what type of material the model believes it is detecting along with the percentage confidence. With this model, I am able to isolate and categorize different images based on the chemical compositions with approximately 80% accuracy. 

**Setup**:
The project is mostly done in the Google Colab environment with tensorflow as the main library used to preprocess data and train and test the model. Some other packages used are matplotlib, which is used to visualize performance of the model, PIL, to show the images in train/test datasets, and pathlib, which is used to set directories and path to data. 

**Dataset**:
Total of about 5030 images were used, split between train and test datasets with the proportion of 8:2, resulting in 4024 train images and 1006 validation images. There are 4 classes to classify: glass, metal, paper, and plastic. I made sure that there are enough samples in each class so that each material is represented evenly in the input train data. All images are preprocessed so that all image sizes are set to 224 x 224. The batch size is set to 32.

**Description**:
When creating the model, a basic Keras sequential model consisting of several convolution blocks with Conv2D layer and max pooling layer included in each block was used. 
Initially, only normalization was applied in the input layer to normalize pixel values of input images, followed by three convolution blocks with increasing number of kernel sizes, then set an output dense layer with dimensions matching the number of classes I wanted to classify. Relu was used as the activation function. After training this initial model, the performance was subpar, with the model accuracy around 75%. 
To improve the performance, additional methods were utilized, such as adding drop out layers as well as applying data augmentation. Data augmentation adds more image data based on the existing datasets. It applies modifications such as zoom in/out and rotations to train images in effort to increase train data size. Dropout layer, on the other hand, randomly removes nodes in the algorithm, performing a technique that is similar to random sampling in traditional machine learning process. After making these adjustments and retraining the model, the probability of guessing the right material went up drastically, to a percentage over 80%, which is also visible with the attached graph below. 

**Limitations**:
The biggest area of improvement was the restrictive number and type of data. Having a bigger and more diverse dataset would allow the model to be better optimized, thus resulting in better accuracy in output. Also, there is more room for optimization that can be done in the model architecture. I only used the basic CNN model for this project, but when compared to the performance of models such as MobilenetV2 from model Zoo, the performance of the CNN model is shown to be lacking, as the MobilenetV2 performance reached over 90% at an even faster rate in early epochs in training. It was surprrising to observe how different the accuracies can be, considering the exact same data were used to train both models. After studying more about deep learning and its various models, I will come back to this recyclable trash classification project to improve my model.

