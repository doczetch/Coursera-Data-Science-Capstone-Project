## General Overview

The purpose of this project is to create a prediction algorithm built thru a Shiny application that will predict a word using a natural language processing model. In this case, US English (en_US) was used.

The application will try to predict the next word if a word or phrase is entered to the text box in the app. It works in a similar fashion, to the way most smart phone keyboards are implemented today using the technology of Swiftkey.

The predictive model will be trained using a corpus, a collection of written texts, called the HC Corpora which has been filtered by language.


### Prediction Model

The prediction model uses the principles of Tidy Data applied to text mining in R. The following steps are involved in the prediction model.

1. Raw text files for model training are used as input.
2. Data is cleaned and separated into 2, 3, 4, 5, and 6 word n-grams and saved as tibbles.
3. N-gram tibbles are sorted by frequency and saved as .rds files.
4. Ngram function uses a **back-off** type prediction model where a user supplies an input phrase, a model uses the last 5, 4, 3, 2 or 1 words to predict the best 6th, 5th, 4th, 3rd, or 2nd match in the data.
5. A predictive next word is given as output.

### Word Predictor App

Overview: The Word Predictor app provides a simple user interface to the word prediction model. The app takes as input a word or phrase in a text box and outputs a prediction of the next word.
