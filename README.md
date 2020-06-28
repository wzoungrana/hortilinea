# hortilinea
A repository to host my first data science project.

## About the Dataset

The dataset is 'dirty' and therefore needed thorough cleaning before anything meaningful could be undertaken with the data. The dataset itself "hortilinea.csv" is a survey conducted on a sample of Kenyan farmers to find out what type of produce their (small) farms generated, the produced quantity. The variables of the survey present some peculiarities such as local measurement units (i.e. gorogoro, debe, pakaacha, handful, heap) whose equivalency with international measurements are not easily and unequivocally established. Where I found reliable information in the Internet, I used it. Otherwise, I had to do without the missing values. As such, the most important takeaway from this dataset is the cleaning, handling of missing values, and finding interesting questions that the available dataset can answer.


## Objectives
The first objective in dealing with this dataset is to perform data cleaning, engineer some features (i.e an imputed 
column on the total yield in quantity), analyze and visualize the data. To this end, I renamed the original 
columns, dropped irrelevant ones, generated nullity matrix, computed the percentage of missing values, wrote 
functions to convert Kenyan Shilling to Euro or acres to hectares, functions to generate plots or machine 
learning models, or to filter data, remove or fill incorrect and missing values. In addition to that, summary 
statistics such correlation matrix, plots on data distribution were generated when needed. I made use of the
Seaborn library for violin plots or regression plots, and tried my hand at Altair for interactive visualization, 
a tree map in Python with Squarify. The last important objective was to apply regression (linear and logistic),
and clustering to the cleaned data. For the logistic regression and classification tasks, I used metrics such as
accuracy, confusion matrix, classification report to assess the performance of the models. When models relied on
the null accuracy, I made use of an oversampling techniques to improve the accuracy.

## Machine Learning Models

### Linear Regression 

    1. Statsmodels OLS Regression:
    
X= HarvestQuantSold + PostHarvestPrice + TotalExpenditure + C(ProductDesignation) + SeedPlantedPrice'

y= HarvestIncomeinEur


LinearModel = smf.ols(formula='HarvestIncomeinEur ~  HarvestQuantSold + PostHarvestPrice + TotalExpenditure + C(ProductDesignation) + SeedPlantedPrice',data=renamed_df)

**R-Squared Adjusted = 0.65**

    2. Linear Regression with the Scikit -Package and CV
 
X= renamed_df[['HarvestQuantSold', 'PostHarvestPrice', 'TotalExpenditure', 'SeedPlantedPrice']]

y= renamed_df[['HarvestIncomeinEur']]

**Test Scores: [ 0.81753283,  0.12179442,   0.59255656,  0.60907234 , -4.00299248]**

**Test Score Agrregrated: -0.37240726575254834**


    3. Linear Regression with Random Forest and CV and Polynomial Features through Pipeline
    
**Test Score Agrregrated: 1.0**

### Clustering 

4. Clustering with KMeans

Data grouped grouped in **three clusters** according to harvest quantity and income (See notebook for more details).

X_cluster = renamed_df[['HarvestQuantSold','HarvestIncomeinEur']]
  
  
 ### Classification
 
 
5. Logistic Regression in Scikit
 
X_log = log[['YieldedQtyinKg', 'HarvestIncome']]

y_log = log['feat_cat']

Accuraracy Train Score: 0.62

**Accuracy Test Score: 0.64**

------> Actually null accuracy. Data needed Resampling. I tried another algorithm instead.


 6. Random Forest Classifier
  
  **Test Score : 0. 68**
 
 For confusion matrix and classification reports, see notebook. 

