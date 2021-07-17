# PD_prediction
A loan enters default when the borrower fails to pay the lender per the terms in the initial loan agreement. Different organizations have different timeframes before which the provided loan is declared as a default. Another important factor that organizations use to the flag plausible defaultees is Delinquency. If a borrower fails to pay multiple payments they are labelled as delinquents but they can get their original status bu making the payments within a reasonable amount of time. Lenders collect extensive information about a plausible client to filter out the plausible defaultees and decide whether or not to provide their services. 
## Dataset
The dataset consists of multiple columns with different kinds of information about the borrowers. The data consists of the following columns. 

![image](https://user-images.githubusercontent.com/75209124/126041108-379b7946-d4c7-49bc-af3c-68b52805d5ae.png)
## EDA
Intial analyses begins by plotting histograms of all the int type columns to get a general idea of the distribution of the data and filtering out columns that may contain outliers. Similar plots are getnerated from value_counts of the variables in categorical columns. Multiple graphs for each specific variable are plotted to get insights on the data. A bar graph that segregates default and non-default for the variables is plotted for most of the columns to understand any self evident relationships. 

A copy of the dataset is then created and the object type variables are converted into labels. A rudimentory selection of variables is then done using a correlation heat map where only one is kept among two highly related columns are removed in the orignial dataset. This is followed by the removal of columns that are weakly correlated with the target variable Default and contain large number of missing values. 

# Data Preprocessing
- The NaN values in columns that contain a considerable units of missing data are replaced by suitable valid values. The other values are then filled by using ffill method in pandas. 
- An outlier check is run by generating basic statistics and plotting boxplots for columns that are suspected to have outliers from the EDA. The data is then modified by removing the outliers using IQR methodology. 
- A Min-Max transform is applied to relevant columns to standardize the data.
- The object type variables are then converted into integer type by using the get_dummies function of pandas. Another alternative to this method can be the utilization of LabelEncoder followed by OneHotEncoder/to_categorical method. 
- The training data is then split into train and validation sets with 80-20 split. 

# Models
1. Logistic Regression
2. KNN
3. SVM
4. Decision Tree
5. Random Forest
6. Neural Network

Hyper parameter tuning and Grid Search is run for the models to get the optimized parameters. The performance of each model is tested using the auc_roc curve.
