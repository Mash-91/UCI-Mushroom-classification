# UCI-Mushroom-classification

This repository contains a notebook created with JupyterLab for a machine learning project based on the [Mushroom data set from the UCI Machine learning repository](https://archive.ics.uci.edu/ml/datasets/mushroom). The aim of this project is to classify mushrooms into the two mutually exclusive classes of "edible" and "poisonous" mushrooms.

The notebook is divided in four main sections:

* Data import and visualisation
* Feature selection and engineering 
* Classification algorithms 
* Conclusions

The **Data import and visualisation** section contains the main code to import the dataset through `pandas`, display some qualitative information on the dataframe and visualise general properties of the dataset using the `seaborn` library. 

The **Feature selection and engineering** section provides methods to quantitatively measure the weight of each feature on the target classification task. No machine learning methods are applied yet, it is rather a purely statistical analysis of the features. These methods are univariate selection methods included in the `sklearn.feature_selection` library such as `SeletKBest` using different metrics like the p-value of a statistical test (as the \chi^2 test) or information-theoretic metrics as for example the mutual information. 

The p-value allows to test whether the observed frequencies are originated or from the same general population (that is the so-called null hypothesis). In this case a \chi^2 statistical test can reveal which features reject or not the null hypothesis, and therefore which features witness or not the presence of two classes "edible" and "poisonous" mushrooms. If a feature manifests high p-value, could be discarded for classification purposes.  

The mutual information can quantify causal dependences between random variables (in this case a feature and the class). This tool from information theory can reveal correlations beyond the linear one and in a sense is a more fundamental measure. It is null if and only if the two random variables are independent, and higher values mean higher dependency. Therefore, features with low or close to zero mutual information might be discarded.

The **Classification algorithms** section as the name suggests, contains the core machine learning classification algorithms employed for this project. These are applied on the dataset obtained after pre-processing in the previous section, and are: Logistic regression, K-NN, Naive Bayes, SVM and random forest. All algorithm are imported from the the `sklearn` package. 

Finally, in the **Conclusions** section, the results from the different algorithm are compared and scored by means of different metrics.

