# Semantic Segmentation
### Introduction
In this project, you'll label the pixels of a road in images using a Fully Convolutional Network (FCN).

### Architecture

A pre-trained VGG-16 network was converted to a fully convolutional network by converting the final fully connected layer to a 1x1 convolution and setting the depth equal to the number of desired classes (in this case, two: road and not-road). Performance is improved through the use of skip connections, performing 1x1 convolutions on previous VGG layers (in this case, layers 3 and 4) and adding them element-wise to upsampled (through transposed convolution) lower-level layers (i.e. the 1x1-convolved layer 7 is upsampled before being added to the 1x1-convolved layer 4). Each convolution and transpose convolution layer includes a kernel initializer and regularizer

### Optimizer

The loss function for the network is cross-entropy, and an Adam optimizer is used.

### Training

The hyperparameters used for training are:

  - keep_prob: 0.5
  - learning_rate: 0.0009
  - epochs: 50
  - batch_size: 5

## Results

Average loss per batch 2 epochs below 0.180
10 epochs below 0.80
20: 0.045
30: 0.040
40: 0.035
50: 0.030

### Samples

Below are a few sample images from the output of the FCN, with the segmentation class overlaid upon the original image in green.

![sample1](./runs/1511643716.7857401/um_000000.png)
![sample2](./runs/1511643716.7857401/um_000001.png)
![sample3](runs/1511643716.7857401/um_000002.png)
![sample4](runs/1511643716.7857401/um_000003.png)
![sample5](runs/1511643716.7857401/um_000004.png)
![sample6](runs/1511643716.7857401/um_000005.png)
![sample7](runs/1511643716.7857401/um_000006.png)
![sample8](runs/1511643716.7857401/um_000007.png)

### Setup
##### Frameworks and Packages
Make sure you have the following is installed:
 - [Python 3](https://www.python.org/)
 - [TensorFlow](https://www.tensorflow.org/)
 - [NumPy](http://www.numpy.org/)
 - [SciPy](https://www.scipy.org/)
##### Dataset
Download the [Kitti Road dataset](http://www.cvlibs.net/datasets/kitti/eval_road.php) from [here](http://www.cvlibs.net/download.php?file=data_road.zip).  Extract the dataset in the `data` folder.  This will create the folder `data_road` with all the training a test images.

### Start
##### Implement
Implement the code in the `main.py` module indicated by the "TODO" comments.
The comments indicated with "OPTIONAL" tag are not required to complete.
##### Run
Run the following command to run the project:
```
python main.py
```
**Note** If running this in Jupyter Notebook system messages, such as those regarding test status, may appear in the terminal rather than the notebook.

### Submission
1. Ensure you've passed all the unit tests.
2. Ensure you pass all points on [the rubric](https://review.udacity.com/#!/rubrics/989/view).
3. Submit the following in a zip file.
 - `helper.py`
 - `main.py`
 - `project_tests.py`
 - Newest inference images from `runs` folder  (**all images from the most recent run**)
 
 ## How to write a README
A well written README file can enhance your project and portfolio.  Develop your abilities to create professional README files by completing [this free course](https://www.udacity.com/course/writing-readmes--ud777).
