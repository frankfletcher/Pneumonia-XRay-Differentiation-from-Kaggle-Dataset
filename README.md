# Pneumonia-XRay-Differentiation-from-Kaggle-Dataset

<br>

### DATASET
The dataset for this notebook is available here: https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia

The data contains chest x-ray images with 3 different labels
1. NORMAL
2. BACTERIAL (pneumonia)
3. VIRAL (pneumonia)

<br>

### TASK
The original task was to differentiate between Normal and Pneumonia.  This turned out to be quite simple to accomplish.  
*I chose the harder task of categorizing between Bacterial pneumonia and Viral pneumonia.* 

<br>

### CHALLENGES
Several challenges presented themselves.  The first challenge is the lack of data.  The training set I used contained the following number of images per categegory:

len(bac_fnames)     :  2772
len(viral_fnames)   :  1493

The delta was 1279 images, or slightly more than half the larger set. I used oversampling to balance the dataset.  
(See <a href="https://arxiv.org/abs/1710.05381">A systematic study of the class imbalance problem in convolutional neural networks by Buda, et al (arXiv:1710.05381v2)</a> for why oversampling is often the best method for correcting imbalance issues.)

The second challenge was overfitting.  I used a Resnet-50 architecture which tended to favor the training set over the validation set.  
To overcome this, we applied a standard set of augmentation transforms provided by FastAI, with the exception of flipping (due to the need to differentiate the left and right lungs)

The baseline model had less than 80% Accuracy.

<br>

### OUTCOME
100% Accuracy on the test set.

<br>


### FUTURE PROJECTS
Recombine in the NORMAL category.
