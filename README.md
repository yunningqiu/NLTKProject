# NLTKProject
Suicide Prediction in Workplaces

**Business Problem:**
When employees attempt suicide, they cost companies money in the following ways:
1. Medical Costs (Hospitalization) and/or Compensation(Death)
2. Post-traumatic Stress Syndrome Training for other employees
3. Hurt Brand Images (Potential loss of existing employees, talents who could be onboard or customers)

**Business Solution:**
We want to save companies costs and improve employees' productivity, leading to increased profits.
We build a suicide prediction tool that predicts employees‘ intentions to suicide pre-emptively based on text data. 
Text classification identifies whether or not a person would commit suicide. 
Topic modeling identifies workers' flag behaviors or emotions related to mental health concerns, and companies can implement interventions to ensure corporate efficiency.

**Data Source:** https://www.kaggle.com/datasets/nikhileswarkomati/suicide-watch?resource=download
The dataset is a collection of posts from "SuicideWatch" and "depression" subreddits of the Reddit platform. 
The posts are collected using Pushshift API. 
All posts that were made to "SuicideWatch" from Dec 16, 2008(creation) till Jan 2, 2021, were collected while "depression" posts were collected from Jan 1, 2009, to Jan 2, 2021.
The dataset displays a text column and a class column (suicide, non-suicide)
There are 232,074 observations.

**Data Preprocessing**
- Translate emoji to english description: For better interpretation, we replaced emojis with their English names (ex. 😭 → “loudly crying face”)
- Remove stopwords: We removed NLTK (Natural Language Toolkit)'s default list of English stopwords and some unmeaningful punctuations like “.” “,”
- Regex cleaning: ‘_WORK_’: jobs?|career|intern(ship) ?|position
                  ‘_INTERPERSONAL_’: co(\- )?worker|interpersonal|m anagers?|boss|superviso r|colleague|employees?| staffs?|network
- Lemmatization: We used lemmatization over stemming because it converts words to their meaningful base forms. (ex. ‘Caring’ -> ‘Care’ rather than ‘Car’)

**Model Exploration & Architecture**
1. Bert Tokenizer
2. Train/Test Sets 50-50 Split
3. Model Exploration
  a. Logistic (baseline)
  b. Random Forest
  c. LightGBM
  d. XGBoost
  e. CatBoost
  f. Bert
  
**Model Performance**
Bert - 97.4% highest accuracy
