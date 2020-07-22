# traffic
 Designed a neural network model to identify which traffic sign appears in a photograph given dataset of traffic sign images.
In this project, I used TensorFlow to build a neural network to classify road signs based on an image of those signs.
To do so, you’ll need a labeled dataset: a collection of images that have already been categorized by the road sign represented in them.
Several such data sets exist, but for this project, 
I used the German Traffic Sign Recognition Benchmark (GTSRB) dataset, which contains thousands of images of 43 different kinds of road signs.

First, take a look at the data set by opening the gtsrb directory. You’ll notice 43 subdirectories in this dataset, numbered 0 through 42.
Each numbered subdirectory represents a different category (a different type of road sign).
Within each traffic sign’s directory is a collection of images of that type of traffic sign.

Next, take a look at traffic.py. In the main function, we accept as command-line arguments a directory containing the data and (optionally) a filename to which to save the trained model.
The data and corresponding labels are then loaded from the data directory (via the load_data function) and split into training and testing sets.
After that, the get_model function is called to obtain a compiled neural network that is then fitted on the training data.
The model is then evaluated on the testing data. Finally, if a model filename was provided, the trained model is saved to disk.

Implementation of load_data :
      * The load_data function accepts data_dir as an argument, representing the path to a directory where the data is stored,
        and return image arrays and labels for each image in the data set.
      * Used the OpenCV-Python module (cv2) to read each image as a numpy.ndarray (a numpy multidimensional array).
        To pass these images into a neural network, the images will need to be the same size, so I resized each image to have width IMG_WIDTH and height IMG_HEIGHT.
      * The function returns a tuple (images, labels). images is a list of all of the images in the data set, where each image is represented as a numpy.ndarray of the appropriate size.
        labels is a list of integers, representing the category number for each of the corresponding images in the images list.
        
        
Implementation of get_model :
      * The get_model function returns a compiled neural network model.
      * The input to the neural network will be of the shape (IMG_WIDTH, IMG_HEIGHT, 3) (that is, an array representing an image of width IMG_WIDTH, height IMG_HEIGHT, and 3 values for each pixel for red, green, and blue).
      * The output layer of the neural network should have NUM_CATEGORIES units, one for each of the traffic sign categories.
      * Adjust numbers of convolutional and pooling layers, numbers and sizes of filters for convolutional layers,pool sizes for pooling layers,numbers and sizes of hidden layers, dropout
        to get good accuracy.
      
      
