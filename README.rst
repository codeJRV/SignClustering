
This Repository basically clusters images of traffic signs in order to visualize and prove that their in class variances are very low. This is a step towards my thesis that we can build more efficient algorithms for sign detection and tracking of traffic signs as we exactly know what we are looking for.


Using pyhog  : 
----------

The Pascal VOC Toolkit comes with a Matlab/C implementation of HOG features by
Pedro Felzenszwalb, Deva Ramanan and presumably others. Since I'm not very fond
of Matlab I replaced the Matlab-specific parts for their Numpy equivalents. It
works, but it's not very efficient because it copies the array into a
Fortran-ordered version. That should be easy to fix.

Using tensorflow: 
----------


# Libraries:
    keras-1.2.1
    Tensorflow -1.0.1
    python-3.5

# Runing the embedding visualization using the logs given in this repository
To run the embeddings launch tensor board 

     tensorboard --logdir=/path/to/your_log/embedding-logs --port=6006
     
     ## Please make sure there is no gap between the name of your directory-
        for e.g- folder name will not work it has to be folder_name
     
       Then open localhost:6006 in a browser
       
       Then go to the embedding options in Tensorboard
       

# To regenerate the embedding logs for feature vectors given in this repositoty

To regenerate the same embedding logs you can use the feature_vectors_400_samples.txt in the feature_vectors.zip file.

If you want to generate embedding visulaization for the given feature vector data, you can directly look into 
[Visualizer.ipynb](https://github.com/codeJRV/Tensorboard-own-image-data-image-features-embedding-visualization/blob/master/own-data-embedding-visualization.py) script to visualize your feature vectors in embedding visualizer.

The code is described block wise in the next section of # Generating the embedding logs for your own feature vectors
Running this script will generate the embedding logs specified to your system path .
Then you can run the tensorboard using

     tensorboard --logdir=/path/to/your log/embedding-logs --port=6006
     
       Then open localhost:6006 in a browser
       
       Then go to the embedding options in Tensorboard

# Data used in this Example
I have used 6 categories with around 300 images in total. The data is stored in the ./data folder. The fearure vectors are generated using the FHOGExtractor.ipynb

# Generating the embedding logs for your own feature vectors

If you want to generate embedding visulaization for your own feature vector data that you have- you can directly look into 
[visualizer.ipynb] script to visualize your feature vectors in embedding visualizer.

Import the modules
      
      import os,cv2
      import numpy as np
      import matplotlib.pyplot as plt
      import pickle # if your feature vector is stored in pickle file
      import tensorflow as tf
      from tensorflow.contrib.tensorboard.plugins import projector

Define your log directory to store the logs

