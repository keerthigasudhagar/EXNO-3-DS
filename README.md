## EXNO-3-DS

# AIM:
To read the given data and perform Feature Encoding and Transformation process and save the data to a file.

# ALGORITHM:
STEP 1:Read the given Data.
STEP 2:Clean the Data Set using Data Cleaning Process.
STEP 3:Apply Feature Encoding for the feature in the data set.
STEP 4:Apply Feature Transformation for the feature in the data set.
STEP 5:Save the data to the file.

# FEATURE ENCODING:
1. Ordinal Encoding
An ordinal encoding involves mapping each unique label to an integer value. This type of encoding is really only appropriate if there is a known relationship between the categories. This relationship does exist for some of the variables in our dataset, and ideally, this should be harnessed when preparing the data.
2. Label Encoding
Label encoding is a simple and straight forward approach. This converts each value in a categorical column into a numerical value. Each value in a categorical column is called Label.
3. Binary Encoding
Binary encoding converts a category into binary digits. Each binary digit creates one feature column. If there are n unique categories, then binary encoding results in the only log(base 2)ⁿ features.
4. One Hot Encoding
We use this categorical data encoding technique when the features are nominal(do not have any order). In one hot encoding, for each level of a categorical feature, we create a new variable. Each category is mapped with a binary variable containing either 0 or 1. Here, 0 represents the absence, and 1 represents the presence of that category.

# Methods Used for Data Transformation:
  # 1. FUNCTION TRANSFORMATION
• Log Transformation
• Reciprocal Transformation
• Square Root Transformation
• Square Transformation
  # 2. POWER TRANSFORMATION
• Boxcox method
• Yeojohnson method

# CODING AND OUTPUT:
```
import pandas as pd
df=pd.read_csv("/content/Encoding Data.csv")
df
```
![370571673-3e735a88-0507-4bca-b382-9bd9322b5677](https://github.com/user-attachments/assets/ae45c339-e959-4e5a-8ef6-20a13228aa30)
```
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
```
```
from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
```
```
pm=['Hot','Warm','Cold']
```
```
el= OrdinalEncoder(categories = [pm])
```
```
el.fit_transform(df[["ord_2"]])
```
![370572081-8e10dc44-682d-4cf2-916b-13b412bf70f4](https://github.com/user-attachments/assets/3b3b43be-773e-4248-8ea2-50ca88fae3ef)

# RESULT:
       # INCLUDE YOUR RESULT HERE

       
