# Naive Bayes README
 **Project**: Naive Bayes<br>
 **Class**: Northwestern CS 349 Fall 2024<br>
 **Contributers**: Raymond Gu, Mimi Zhang, Alvin Xu, Rhema Phiri, Eshan Haq

## Sentences Dataset
The `sentences` dataset was taken from the Emotions dataset on Kaggle (provided by Nidula Elgiriyewithana).
- **Sentences**: Each of the sentences are from a collection of English Twitter messages. The sentences
                 have been formatted for easy handling. All letters in each sentence are lowercase
                 and all punctuation has been removed.
- **Emotion**: Each sentence has a corresponding emotion associated with it. There are 6 distinct emotions
               in this dataset: anger, fear, joy, love, sadness, and surprise.

## Naive Bayes File
The `Naive_Bayes.ipynb` file contains all the code needed for the Naive Bayes sentence classifier.<br>

**Description For Get_Datasets Function**<br>
The `get_datasets` function creates and downloads the training, validation, and test datasets as CSV files.
It downloads the files: `train.csv`, `valid.csv`, and `test.csv`. To create our model, we need an even
distribution of emotions across all of our datasets. Details about each dataset are provided below:
- **Training**: This dataset contains 30,000 examples (5,000 examples of each sentiment).<br>
- **Validation**: This dataset contains 3,750 examples (625 examples of each sentiment).<br>
- **Test**: This dataset contains 3,750 examples (625 examples of each sentiment).<br><br>

**Description For Naive Bayes Class**<br>
The design choices for the `Naive_Bayes` class are explained below.<br>
- **Sentence Representation**: We used a TF-IDF representation of words since it allowed us to assign
                               different values to words depending on how important they are to the class.<br>
- **Smoothing**: When calculating the probabilities of words being in a class, we decided to implement
                 smoothing incase a word from the validation or test datasets did not appear in the
                 training dataset. This helps prevent any issues with zero probabilities. The smoothing
                 parameter (alpha) is determined by testing various values on the validation set.<br>
- **Performance Metric**: For our performance metric, we decided to use F1-score because our task is
                          classification and it is a good balance between precision and recall.<br>