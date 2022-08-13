![](https://github.com/SmailDK/Melanoma-Detection/blob/master/Melanoma_Detection_.png)

The objective of this project is to propose a methodology for the automatic classification of skin lesions, based on image analysis and machine learning.

# 1 - Database

The database is composed of 200 original images of pigmented skin lesions acquired by
dermoscopy. 100 of them have been histopathologically confirmed as melanomas. Thus two
classes are considered in this project: on the one hand confirmed melanomas and on the
other hand the remaining benign lesions.
In addition to the original images, binary images representing the region of interest of
each lesion are included in the database. The segmentation of the images using superpixels
are also added.

![](https://github.com/SmailDK/Melanoma-Detection/blob/master/skinlesions_readme.png)

# 2 - Feature Extraction 

**Morphological features** are extracted from the segmented images thanks to the `regionprops` function from `skimage.measure` such as :

- area
- eccentricity
- perimeter
- equivalent diameter
- extent
- filled area
- minor axis length
- major axis length
- major axis length/minor axis length
- solidity

The most relevant features are then kept using ANOVA criterion

**Texture features** are extracted from the images thanks to the **Local Binary Patterns** algorithm 
The most relevant features are then kept using Pearson's correlation formula

# 3- Training and testing of the model

The final dataframe is divided into a training set with 70% of the size of the original set and a test set with 30% of the size of the original set.


Multiple Machine Learning models are tested (Naive Bayes, SVM, Logistic Regression, Random Forest, Decision Trees, ...) and the performance of each model is assessed with measures such as :

- Accuracy
- F1 Score
- ROC Curve
- AUC

The max accuracy reached is 74% with Random Forests, which can be largely improved with state of the art models that are used today.
