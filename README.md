# Syntatic-Processing - Identifying Entities in Healthcare Data

There are eight major tasks that you need to perform to complete the assignment. They are as follows:

1. Data preprocessing
2. Concept identification
3. Defining the features for CRF
4. Getting the features words and sentences
5. Defining input and target variables
6. Building the model
7. Evaluating the model
8. Identifying the diseases and predicted treatment using a custom NER
9. Let's break down the steps into subtasks to understand this better.

 

# Data preprocessing: 
    As you are already aware that the dataset is in the token format instead of sentences, you need to construct the sentences from the words. There are blank lines     after the completion of each sentence or a set of labels in label files ('train_label' and 'test_label') and you need to build a logic to arrange them into         sentences or a sequence of labels in the case of label files. You can refer to the following two images to understand this better.
    
    ![image](https://user-images.githubusercontent.com/104059964/189470662-1a546dd3-8525-4e3f-aa70-a223e7dce6b7.png)

A similar step is to be performed for the 'train_label' and 'test_label' datasets.

![image](https://user-images.githubusercontent.com/104059964/189471547-32b8806e-2c80-4d14-a461-ca74019cd32a.png)

 
You need to do the following three tasks after processing and modifying the datasets:

 1. Construct proper sentences from individual words and print five sentences along with their labels.
 2. Print the correct count of the number of sentences in the processed train and test dataset.
 3. Correctly count the number of lines of labels in the processed train and test dataset.
 

# Concept identification: 
       
       After preprocessing, we will first explore what are the various concepts present in the dataset. For this task, we will use PoS tagging. It is good to              identify all the words from the corpus that have a tag of NOUN or PROPN (nouns) and prepare a dictionary of their counts. We will then output the top 25 most        frequently discussed concepts in the entire corpus.
       
       An important point to note here is that we are using both test and train sentences for concept identification. This is an exploratory analysis on the                complete data. In this step, you need to perform the following two tasks by considering the train and the test dataset as a single unit of data:

          1. Use a toolkit like spaCy to extract those tokens that have NOUN or PROPN as their PoS tag and find their frequency from the entire dataset that                      comprises both the train and the test datasets.
          2. Print the top 25 most common tokens with NOUN or PROPN PoS tags for the entire dataset that comprises both the train and the test datasets.

# Defining the features for CRF: 
   Here, you need to perform the following three steps:
    1.  Define the features with the PoS tag as one of the features.
    2.  While defining the features in which you have used the PoS tags, you also need to consider the preceding word of the current word. The use of the                   information of the preceding word makes the CRF model more accurate and exhaustive.
    3.  Mark the beginning and the end words of a sentence correctly in the form of features.
 

#  Getting the features and the labels of sentences: 
     In this step, you need to perform the following two tasks:
              1. Write the code to get the features' value of a sentence after defining the features in the previous step.
              2. Write the code to get a list of labels of a given preprocessed label line that you have created earlier.
 

# Defining input and target variables: 
In this step, you need to perform the following two tasks:
     1. Extract the features' values for each sentence as an input variable for the CRF model in the test and the train dataset.
     2. Extract the labels as the target variable for the test and the train dataset.
 

# Building the model: 
 You need to build the CRF model for a custom NER application using the features and the target variables.

 

# Evaluation:
 Evaluate the model using the following two steps:
   1. Predict the labels of each of the tokens in each sentence of the test dataset that has been preprocessed earlier.
   2. Calculate the f1 score using the actual and the predicted labels of the test dataset.
 

# Identifying the diseases and treatment using a custom NER: 

     1. Create the code or logic to get all the predicted treatments (T) labels corresponding to each disease (D) label in the test dataset. You can refer to the            following image to get an idea on how to create a dictionary where diseases are working as keys and treatments are working as values.
     
 ![image](https://user-images.githubusercontent.com/104059964/189471684-62ed73b2-2176-438e-9cf5-a8631a09caa4.png)

     2. Predict the treatment for the disease named 'hereditary retinoblastoma'.
     


# Assumption 

Please note that here, we are assuming that if there is a disease in the sentences, then the treatment mentioned in that sentence can be assumed to be the treatment for that disease. Also, there is an assumption that the same treatment can work for different diseases.
