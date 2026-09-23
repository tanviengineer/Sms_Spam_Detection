SMS Spam Detection using Machine Learning and NLP


-------Project Overview---------

SMS Spam Detection is a Machine Learning and Natural Language Processing (NLP) project that classifies SMS messages into two categories:

Spam - unwanted or promotional/fraud-like messages

Ham (Not Spam) - normal messages

The project includes data cleaning, exploratory data analysis (EDA), text preprocessing, word-frequency analysis, TF-IDF feature extraction, machine learning model comparison, model evaluation, and a saved prediction model.



--------Objectives--------

Clean and prepare the SMS dataset.

Convert text messages into useful numerical features.

Apply NLP preprocessing such as tokenization, stop-word removal and stemming.

Perform exploratory data analysis and visualization.

Train and compare multiple machine learning classifiers.

Evaluate models using accuracy and precision.

Save the trained text vectorizer and prediction model.

Provide a simple Streamlit interface for SMS classification.



-------Dataset---------

The project uses spam.csv.

The notebook loads the dataset with CP1252 encoding. The original dataset contains 5,572 rows and 5 columns. Three extra unnamed columns are removed, after which the useful data contains the message label and message text.

The executed notebook shows 4,825 ham messages and 747 spam messages.

The columns are renamed to:

target - message class

text - SMS message

The target is label-encoded so that:

0 = ham

1 = spam

The notebook reports 403 duplicate rows before duplicate handling.



--------Technologies Used------------

Python

Pandas

NumPy

Matplotlib

Seaborn

NLTK

WordCloud

Scikit-learn

XGBoost

Streamlit

Jupyter Notebook



-------------Project Workflow------------

SMS Dataset
     |
     v
Data Cleaning
     |
     v
Label Encoding
     |
     v
EDA and Visualization
     |
     v
Text Preprocessing
     |
     v
TF-IDF Feature Extraction
     |
     v
Train/Test Split
     |
     v
Machine Learning Models
     |
     v
Evaluation
     |
     v
Saved Model + Vectorizer
     |
     v
Streamlit Prediction App



---------Text Preprocessing---------

The notebook creates a transformed text representation using NLP preprocessing. The workflow includes:

Convert text to lowercase.

Tokenize the message.

Keep alphanumeric tokens.

Remove English stop words and punctuation.

Apply Porter stemming.

Join the processed tokens into transformed text.



--------Feature Extraction--------

The project uses:

TfidfVectorizer(max_features=3000)

The transformed SMS messages are converted into numerical TF-IDF features before model training.



--------Train/Test Split-------

The notebook uses:

train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=2
)



-------Machine Learning Models--------

The notebook experiments with several classifiers, including:

Gaussian Naive Bayes

Multinomial Naive Bayes

Bernoulli Naive Bayes

Support Vector Classifier

K-Nearest Neighbors

Decision Tree

Logistic Regression

Random Forest

AdaBoost

Bagging Classifier

Extra Trees Classifier

Gradient Boosting

XGBoost

It also experiments with a soft Voting Classifier.



---------Evaluation Results---------

The following values are taken from the executed notebook:

Algorithm

Accuracy

Precision

KNN

0.904933

1.000000

Extra Trees

0.969507

1.000000

Multinomial Naive Bayes

0.965022

0.991736

SVC

0.973094

0.984848

Random Forest

0.967713

0.984127

XGBoost

0.961435

0.967480

Logistic Regression

0.951570

0.964286

Gradient Boosting

0.939910

0.941748

Bagging

0.960538

0.925373

AdaBoost

0.912108

0.894737

Decision Tree

0.923767

0.861386



The notebook also reports:

GaussianNB: Accuracy 0.862780, Precision 0.510204

MultinomialNB: Accuracy 0.965022, Precision 0.991736

BernoulliNB: Accuracy 0.973991, Precision 0.977778

Soft Voting Classifier: Accuracy 0.977578, Precision 1.000000

For the deployable files in this repository, the notebook saves the Multinomial Naive Bayes (mnb) model as model.pkl and the TF-IDF vectorizer as vectorizer.pkl.



-------Saved Files---------

model.pkl - trained prediction model

vectorizer.pkl - fitted TF-IDF vectorizer



---------Streamlit Application--------

The optional app.py provides a simple interface where a user can enter an SMS message and receive a prediction:

Spam

Not Spam



-------Run the application--------

Open PowerShell in the project folder:

cd D:\Tanvi_SmsSpamDetection
python -m pip install -r requirements.txt
python -m streamlit run app.py

Then open the local Streamlit URL shown in the terminal, normally:

http://localhost:8501



--------Project Structure---------

Sms_Spam_Detection/
│
├── Tanvi_SmsSpamDetection.ipynb
├── spam.csv
├── model.pkl
├── vectorizer.pkl
├── app.py
├── requirements.txt
└── README.md



-------GitHub Repository---------

https://github.com/tanviengineer/Sms_Spam_Detection



--------Future Scope----------

Add more recent and diverse SMS datasets.

Handle multilingual SMS messages.

Add probability/confidence information to the user interface.

Improve deployment for public web access.

Add automated model retraining when new labeled messages become available.

Add additional evaluation metrics such as recall and F1-score.



---------Conclusion---------

This project demonstrates an end-to-end NLP and Machine Learning workflow for SMS spam classification, from raw data cleaning and text preprocessing to feature extraction, model evaluation, model serialization, and application development.