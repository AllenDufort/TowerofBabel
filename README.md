# TowerofBabel
Devpost link for updates: https://devpost.com/software/tower-of-babel

Basic Summary
    We wanted to be able to take long text posts and sort them into categories. 
    We created the model from a database of news articles with subject tags.

    We made a jupyter notebook file, text_class.ipynb, and a dataset of news articles, 
    BBC News Train.csv, to achieve this.

The Dataset
    BBC News Train.csv has 1490 different articles. 
    Each article has: an article Id, the text, and the category.
    The 5 possible categories for the news artices are: 
    business, tech, politics, sports, and entertainment.

The Jupyter Notebook: text_class.ipynb
    First, we download the dataset and preprocess it.
    The preprocessing involves factorizing the dataset by the category,
    which associates the category names with a numerical index (a value 0 to 4), 
    and saves it in a new column called CategoryId.
    Next in the preprocessing, we remove all special characters, and stop words 
    from the dataset, we convert all the words to lowercase, and then we lemmatize the words
        
        Lemmatization groups words with similar meanings to one word 
        (e.g. 'rocks' and 'rock' would be grouped as one word).
        
        Stop words are a set of commonly used words in any language.
        Since we remove these commonly used stop words, 
        we can focus on the more important words instead.

    Next we shuffle the data and made 30% of the dataset the test set.
    
    Afterwords, we begin to run the model in a function called run_model().
    The function compares 9 different classifiers for natural language processing models:
    Logistic Regression, Random Forest, Multinomial Naive Bayes, 
    Support Vector Classifer, Decision Tree Classifier, Gaussian Naive Bayes,
    2 K Nearest Neighbor classifiers, and Multilayered Perceptron CLassifier.

Results

    We record the test accuracy, precision, recall, and F1 score.
    For each model, these 4 values are usually the same.
    The most accurate model is Random Forest.

        Model	                            Test Accuracy	Precision	Recall	F1
    0	Logistic Regression	                97.09%	        0.97	    0.97	0.97
    1	Random Forest	                    97.99%	        0.98	    0.98	0.98
    2	Multinomial Naive Bayes	            97.09%	        0.97	    0.97	0.97
    3	Support Vector Classifier           96.64%	        0.97	    0.97	0.97
    4	Decision Tree Classifier            82.10%	        0.82	    0.82	0.82
    5	Gaussian Naive Bayes	            76.06%	        0.76	    0.76	0.76
    6	K Nearest Neighbor	k=10            73.60%	        0.74	    0.74	0.74
    7   K Nearest Neighbor	k=7             77.63%	        0.78	    0.78	0.78
    8   Multilayer Perceptron Classifier	97.76%	        0.98	    0.98	0.98

        TP = true positive, TN = true negative, FP = false positive, TN = false negative

        Accuracy - the ratio of correctly predicted observation to the total observations.
        Accuracy = (TP+TN)/(TP+FP+FN+TN)

        Precision - the ratio of correctly predicted positive observations to the total predicted positive observations.
        Precision = TP/(TP+FP)

        Recall - the ratio of correctly predicted positive observations to all of the actual positive observations.
        Recall = TP/(TP+FN)

        F1 score - the weighted average of Precision and Recall.
        F1 Score = 2*(Recall * Precision) / (Recall + Precision)

Visualizations
    There is a histogram that shows how news articles are in each category.
    There is a pie chart that shows the percentage of news articles in each category.
    There is a wordcloud for each news category that shows the most common words in each category:
    the more used the word is, the bigger it is in the word cloud.

Limitations
    It can only categorize text into the 5 aforementioned categories, which does
    not encompass every major topic. Some categories that do not fit neatly into our categories, 
    such as poetry, might fit in weirdly




