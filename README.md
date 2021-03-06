# NLP-with-Scikit-Learn
NLP Projects inspired by research papers implemented using the Python Scikit Learn library

## [Text Classification of News Articles using FCD and Naive-Baiyes](https://github.com/rahmadiridwan/NLP-with-Scikit-Learn/blob/main/MNB_FCD.ipynb)
https://github.com/rahmadiridwan/NLP-with-Scikit-Learn/blob/main/MNB_FCD.ipynb

This text mining project was inspired by a paper by Meng et al published in 2011 titled "A two-stage feature selection method for text categorization" (https://www.sciencedirect.com/science/article/pii/S089812211100616X) where a two stage feature selection method is implemented before applying support vector machine to classify text data. This project is my attempt to replicate the implementation of the first stage of the feature selection technique called FCD (Feature Contribution Degree) which is first proposed in this paper and to see how effective it is as a feature selection in its own. Hence, the second part of the feature selection stage (namely LSI) is not implemented and instead of the use of the SVM classifier, I will try to see how effective this feature selection technique is when applied together with the Multinomial Naive-Bayes classifier. (Note that this is also one of my very first projects in text mining using Python, when I tried to simply replicate and  maybe modify multiple feature selection techniques from text mining and NLP research papers as inspiration for my capstone project for my bachelor's degree in computing) 
* The text dataset provided for this project is an Indonesian news dataset consisting of 200 samples and 5 categories (with each category each consisting of 40 samples)
* At the text pre-processing stage, stopwords (in Indonesian) and punctuation marks are removed (using the nltk stopwords and the re libraries respectively) from the dataset and the text data is then stemmed and tokenized accordingly
* The dataset is then transormed by means of the binary countvectorizer into a matrix where the rows represent each sample, the columns represent each preprocessed word (term) in the entire corpus and the element of the matrix represents the binarized values of the feature terms in each document/row sample (0 if the term in not present in the document sample and 1 if it is present)
* A new matrix is then created consisting of the fcd values for each feature term in each news category
* The terms where a fcd value under 0 is present in any of the category are removed from the feature set and the tf-idf matrix of the new feature set with respect to each document (row sample) is then fed into the Multinomial Naive-Bayes algorithm with a training to testing data split of 70% and 30% respectively
* The classification accuracy for the model is 79.66%


## [Text Classification of News Articles using FS-CHICLUST and Naive-Baiyes](https://github.com/rahmadiridwan/NLP-with-Scikit-Learn/blob/main/MNB_FCD.ipynb)
https://github.com/rahmadiridwan/NLP-with-Scikit-Learn/blob/main/MNB_FCD.ipynb

This text mining project was inspired by a paper by Sarkar et al published in 2014 titled "A Novel Feature Selection Technique for Text Classification Using Naive Bayes" 

(https://www.researchgate.net/publication/285463155_A_Novel_Feature_Selection_Technique_for_Text_Classification_Using_Naive_Bayes) 

A two stage feature selection method called FS-CHICLUST is implemented before applying Multinomial Naive-Bayes to classify text data. This project is my attempt to emulate the implementation of FS-CHICLUST along with the Naive-Bayes classifier using the same Indonesian news articles dataset I used previously (when I attempted to implement FCD as the feature selection technique using the Naive-Bayes classifier). I did this project as my capstone project for my undergraduate dissertation

* The text dataset provided for this project is an Indonesian news dataset consisting of 200 samples and 5 categories (with each category each consisting of 40 samples)
* At the text pre-processing stage, stopwords (in Indonesian) and punctuation marks are removed (using the nltk stopwords and the re libraries respectively) from the dataset and the text data is then stemmed and tokenized accordingly
* The dataset is then transormed by means of the countvectorizer into a matrix where the rows represent each sample, the columns represent each preprocessed word (term) in the entire corpus and the element of the matrix represents the frequency of the feature terms present in each document/row sample 
* A new matrix is then created consisting of the modified chi-squared statistics values for each feature term in each news category
* The terms where the chi-square statistics value falls under the given threshold is present in any of the category are removed from the feature set and the tf-idf matrix of the new feature set with respect to each document (row sample) is then fed into the Multinomial Naive-Bayes algorithm with a training to testing data split of 70% and 30% respectively
* The classification accuracy for the model is 72.88% at the point of the iteration when the total number of clusters is equal to 960
