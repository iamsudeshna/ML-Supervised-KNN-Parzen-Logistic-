# ML-Supervised-KNN-Parzen-Logistic
TMNIST Dataset
Data set link :  tmnst DATA SET.csv
This dataset contains 26 characters in different fonts. 
•	We will work with all the 26 capital letters A to Z. 
•	Normalize each pixel value from [0,1] range instead of [0,255] now. 
•	Please split each class into 70% train and 30% test split 

 PROBLEM Statement 1: Visualizing PCA vs. Fisher Scatter Plots
•	Write a Function that takes any four classes from this dataset
•	NOTE: Number of Fisher projections = Number of classes – 1
•	So taking 4 classes gives us a maximum of 3 Fisher projections
•	Function interface should look like this

def pca_vs_fisher_3d(train, [‘A’, ‘C’, ‘O’, ‘X’]):

Part 1: PCA PROJECTION
•	Compute the first 3 principal components of the data (across all four classes you have chosen) 
•	Figure 1: Draw the 3-D Scatter plot of the points in the PCA space.
•	Make sure to colour code each data point by class (red, green, blue, cyan)

Part 2: FISHER PROJECTION
•	Compute the first 3 Fisher components using class label into account
•	Figure 2: Draw the 3-D scatter plot of the points in the Fisher space
•	Make sure to colour code each data point by class (red, green, blue, cyan)

Submit Figure 1 and 2 pair together for the same four classes. 

Repeat this for 3 such combinations of 4 classes of your choice by calling the above function 3 times and generating the 6 images. 

 
PROBLEM Statement 2: Visualizing all Classes via their Fisher Distance

•	Part 1: FISHER DISTANCE COMPUTATION
•	Focus on the 26 capital letter classes
•	We want to compute the Pair-wise distance between all pairs. 
•	Compute the Fisher Discriminant between that pair of classes
•	Create the matrix e.g. Fisher(‘A’, ‘B’),… Fisher(‘Y’, ‘Z’)
Create a three column file with headings: Class 1  ,  class 2 ,  fischer values
•	Example : class 1    class 2        fisher scores
o	         ‘A’,          ‘B’,           Fisher(‘A’, ‘B’) value
o	…..                   ……….        ………….
o	         ‘Y’,          ‘Z’,             Fisher(‘Y’, ‘Z’) value
  Part 2: CLASS VISUALIZATION USING t-SNE/MDS
•	Using and Multi-Dimensional-Scaling tool for visualization
•	Show the 26 classes on a 2-D plan such that
•	Two classes with small Fisher distance are close to each other
•	Two classes with larger Fisher distance are far from each other
•	Comment on whether this makes sense? 

PROBLEM Statement 3: kNN and Parzen Window classifiers hyper parameter sweeps
•	First project the 26 class, 784 dimensional data into 25 Fisher-dimensions
o	Note: Since data has 26 classes, it will have max 25 Fisher projections
•	Using this 25-D data we will do both parameter sweeps on knn and parzen

def knn_sweep(train, test, K = [1, 3, 5, 7, 9, 11, 13, 15, 17]):

def parzen_sweep(train, test, sigma = [0.1, 0.5, 1, 1.5, 2, 3, 4, 6, 8, 10]):


•	In each case (knn and parzen) we will SAVE the train data
•	Fit the test data given the training data using the two methods
•	Run a for loop over the parameters passed
•	Compute the train set and test set accuracy on the same
•	Plot both against the parameters and show the two curves
•	You need to be able to generate the following tables first: 
o	Knn.csv = k-value, train-accuracy, test-accuracy
o	Parzen.csv = sigma-value, train-accuracy, test-accuracy

 PROBLEM Statement 4: Perceptron vs. Logistic Regression
•	Using the projected 25-dimensional data itself (from problem 3)
•	Pick two classes and train multiple (100) perceptron/logistic models
•	Draw train and test accuracy histograms with these 100 random initializations

def perceptron_model(train, test, classes = [‘A’, ‘C’]):

def logistic_model(train, test, classes = [‘A’, ‘C’]):

You need to first generate the following files: 
•	perceptron_A_C.csv = [run, train-accuracy, test-accuracy]
•	logistic_A_C.csv = [run, train-accuracy, test-accuracy]

        Compute the average test/train accuracy of perceptron and logistic regression.

