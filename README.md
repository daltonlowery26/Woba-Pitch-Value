# Predicting Pitch Value in MLB using XGBoost

## -- Project Status: Active

## Project Intro/Objective
Using data from the 2024 season, this project seeks to quantify the value of pitches in the context of woba. The result from this is then used in combination with other data to predict the WAR of a pitcher for that season.

### Methods Used
* Pandas: Used for data cleaning, transformation, and feature engineering.
* NumPy: For numerical computations and array manipulation.
* XGBoost: Implemented a gradient boosting regression model to predict pitch wOBA.
* Scikit-learn (sklearn): Utilized for model evaluation metrics, data splitting, and grid search hyperparameter tuning.
* Matplotlib and Seaborn: Employed for data visualization and exploratory data analysis (EDA).
* Bayesian Optimization : Used to efficiently explore the hyperparameter space of the XGBoost model.

## Project Description
The initial dataset containing 114 features, was reduced through cleaning methods to a more refined set of approximately 20 relevant variables to maximize XGBoost model performance. Feature extraction techniques were also implemented to generate additional informative features, further contributing to model accuracy. Extensive exploratory data analysis (EDA) was performed to quantify the impact of ball and strike counts on expected weighted On-Base Average (wOBA). This analysis, documented in count_clean.ipynb and strike_ball_value.ipynb, revealed a strike value of approximately -0.103 and a ball value of 0.17225 in terms of expected wOBA. The data_exploration folder contains additional EDA, which focused on understanding the nuanced relationships between pitch velocity, location, pitch type, and expected wOBA. Figures created from this can be viewed in the figures folder.

An XGBoost regression model was chosen due to its robust performance and gradient boosting algorithm, which offers significant advantages over simpler regression methods. To efficiently tune the model's hyperparameters, the project was migrated to Google Colab, leveraging its enhanced computational capabilities. A hybrid optimization strategy was employed. Bayesian optimization was initially used to efficiently explore the hyperparameter space, providing a more targeted search compared to random search. Subsequently, grid search was utilized to converge on the precise optimal parameter combination, ensuring maximum model performance with minimal computational overhead.

## Folder Structure
* cleaning: Cleaning of statcast dataset as well as creation of count dataset to help quantify ball and strike value.
* data: Orginal dataset (statcast_pitch_2024) and various cleaned datasets including the main cleaned_pitch_2024 dataset
* data/count: Leauge stats in diffrent counts, sourced from baseballsavant.
* data/old datasets: Datasets no longer used, from previous cleaning approaches.
* data/results: Datasets holding the results from basic statistical tests done in the data_exploration folder.
* data_exploration: Exploration of the preformance of various attribues in the context of wOBA as well as correlations between features and wOBA.
* models: Xgboost models for individual pitch preformance as well as, eventually, player preformance.

## Basic Implications of Data 
#### All Files in Data Exploration Folder 
* wOBA value does not vary signficantaly based on pitchtype alone (pitchtype.ipynb)
* Location is the most important factor for pitching results (location.ipynb)
* Velocity is very important for some pitch types (fastball, some curveballs) but not for others (velo.ipynb)
* Only swinging strike rate and called strikes are highly correlated with wOBA (stats.ipynb)


## Model Preformance
#### Preformance on Predicting Player War
###### (player_pitch_model.ipynb)
* Mean Squared Error of 0.22
* R^2 of 0.83

## Contact
* Please contact with any questions
* Email: dalton.lowery@emory.edu
