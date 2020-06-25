# hortilinea
A repository to host my first data science project.

About the Dataset
I encountered this dataset in a statistic class I took. The dataset was presented as 'dirty' and therefore 
needing thorough cleaning before anything meaningful could be undertaken with the data. The dataset itself 
"hortilinea.csv" is a survey conducted on a sample of Kenyan farmers to find out what type of produce their 
(small) farms generated, the produced quantity. The variables of the survey present some peculiarities such as
local measurement units (i.e. gorogoro, debe, pakaacha, handful, heap) whose equivalency with international 
measurements are not easily and unequivocally established. Where I found reliable information in the Internet, 
I used it. Otherwise, I had to do without the missing values. As such, the most important takeaway from this 
dataset is the cleaning, handling of missing values, and finding interesting questions that the available dataset
can answer.


Objectives
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


References :

https://books.google.de/books?id=Yw_WDwAAQBAJ&pg=PT78&lpg=PT78&dq=gorogoro+in+kg&source=bl&ots=-K7b9EDD-q&sig=ACfU3U13VvifcyeAqkc2nnXW6oi4E9QP2Q&hl=de&sa=X&ved=2ahUKEwiJ9-3QoYPqAhViUBUIHQijCIMQ6AEwAHoE
CAgQAQ#v=onepage&q=gorogoro%20in%20kg&f=false
