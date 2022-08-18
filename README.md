# Music Genre Prediction - Project overview
Data science project based on predicting music genre based on inputs such as popularity, velocity and tempo of the song.

# Code and resources used
* Kaggle dataset titled 'Prediction of music genre' : https://www.kaggle.com/datasets/vicsuperman/prediction-of-music-genre 

# Exploratory Data Analysis (EDA)
Features:

Categorical:

1. Instance ID
2. Artist name
3. Track name
4. Key
5. Mode
6. Obtained date

Thus a total of 6 columns are categorical variables.

Numeric:

1. Popularity
2. Acousticness
3. Danceability
4. Duration (in milliseconds)
5. Energy
6. Instrumentalness
7. Liveness
8. Loudness
9. Speechiness
10. Tempo
11. Valence

A total of 11 columns are numeric.

Target:

Music Genre

Using seaborn library, we can do some visual analysis on the given data:

* Histogram
![alt_text](https://github.com/ipieren/Music-genre-prediction/blob/main/img/histogram.PNG)

* Box plot
![alt_text](https://github.com/ipieren/Music-genre-prediction/blob/main/img/boxplot.PNG)

* Violin plot
![alt_text](https://github.com/ipieren/Music-genre-prediction/blob/main/img/violinplot.PNG)

The dataset is cleaned by removing NA values and dropping columns that were not useful so that model building could be carried out.

# Model Building

* One hot encoding is performed to ensure that we have numeric values for 'mode' and 'key' columns.
* The data is divided into training, testing and validation sets with 80-10-10 split.
* The following classifiers would be included for model building:
*   1. Random Forest Classifier
*   2. XGBoost Classifier (Default)
*   3. XGBoost Classifier (Altered)

# Model Performance
* We would be using f1-score instead of accuracy since it is better with a larger class distribution.
* Hyperparameter tuning is performed for obtaining the best Random Forest Classifier parameters.
* XGBoost Classifier is used with both default and altered parameters to check for model f1-score.

The ROC Curve for each of the classifier is given below:
* Random Forest Classifier

![alt_text](https://github.com/ipieren/Music-genre-prediction/blob/main/img/m1_randomforest.PNG)

* XGBoost Classifier (Default)


![alt_text](https://github.com/ipieren/Music-genre-prediction/blob/main/img/m2_defaultXGBoost.PNG)

* XGBoost Classifier (Altered)


![alt_text](https://github.com/ipieren/Music-genre-prediction/blob/main/img/m3_alteredXGBoost.PNG)

# Conclusion and further improvements
* Default XGBoost proved to be a better model with 0.931 AUC Score indicating that for the dataset at hand, this is a bit better choice than random forest classifier.
* Further hyperparameter tuning could be used for XGBoost. Since tuning using GridSearch consumes a lot of computational time, randomSearch method could be employed and the results may be improved accordingly.
