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
```
df['bo2']=el.fit_transform(df[["ord_2"]])

df
```
![370572192-2d868f26-5e4b-4807-81a1-8aa85c9af317](https://github.com/user-attachments/assets/8b92ec18-365a-4e48-a605-c43f1faf59fa)
```
le=LabelEncoder()
dfc=df.copy()
dfc['ord_2']=le.fit_transform(dfc['ord_2'])
dfc
```
![370572310-eed9d998-4a2c-4571-ae3d-621f183fd26c](https://github.com/user-attachments/assets/a0ec2dd6-7253-4bb6-879d-16caf2b4d87e)
```
dfc=df.copy()
dfc['con_2']=le.fit_transform(dfc['ord_2'])
dfc
```
![370572445-035f680e-dbf0-4a4d-ad50-cba1bb95ef6c](https://github.com/user-attachments/assets/615fdb6c-4a8f-4fc6-a415-e4ed90eb1c4c)
```
from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder(sparse_output=False)
df=df.copy()
```
```
enc=pd.DataFrame(ohe.fit_transform(df[['nom_0']]))
enc
```
![370572629-0de7ee6f-9baa-4e0b-a024-002c6c6f7351](https://github.com/user-attachments/assets/eb2691b2-f627-45cb-9c76-f88eb73512dd)
```
df2=pd.concat([df,enc],axis=1)
df2
```
![370572799-3ac75523-8147-4da0-9dc4-f07d0e5c03dc](https://github.com/user-attachments/assets/389074f8-04aa-4ba6-95ac-adc4b67abbe9)
```
pip install --upgrade category_encoders
```
```
from category_encoders import BinaryEncoder
```
```
import pandas as pd
df=pd.read_csv('/content/data (1).csv')

df
```
![370573113-fbf9b8fd-1f31-4a34-a015-2bf592ef6cb3](https://github.com/user-attachments/assets/7f74ca39-1d17-4fba-bef6-cf99c583d0f6)
```
be=BinaryEncoder()
nd=be.fit_transform(df['Ord_2'])
dfb=pd.concat([df,nd],axis=1)
dfb1=df.copy()
dfb
```
![370573328-ea9b50e2-2daf-4ad6-86d2-226e06da6ecf](https://github.com/user-attachments/assets/e1335420-a1fd-464c-8c11-bc45347bfcb2)
```
from category_encoders import TargetEncoder
te=TargetEncoder()
cc=df.copy()
new=te.fit_transform(X=cc["City"],y=cc["Target"])
cc=pd.concat([cc,new],axis=1)
cc
```
![370573531-ca40d19a-5493-4707-9fb0-0879990c9cfd](https://github.com/user-attachments/assets/a4354783-6278-4607-b44f-d2eb423b04bf)
```
import numpy as np
import pandas as pd
from scipy import stats
```
```
df=pd.read_csv('/content/Data_to_Transform.csv')
df
```
```
df.skew()
```
![370573991-df04efde-3ad9-4da2-9d0e-7e35d8ca7ac9](https://github.com/user-attachments/assets/771c7dfc-de95-4707-973a-126fea0e7642)
```
np.log(df['Highly Negative Skew'])
```
![370573992-43cc4e8d-5012-4b83-8d08-753c5d02951b](https://github.com/user-attachments/assets/a0b9c827-1205-4580-b6a6-543eebfb74fc)
```
np.sqrt(df['Highly Negative Skew'])
```
```
np.reciprocal(df['Highly Negative Skew'])
```
![370574388-46f6e6ce-cf83-4e87-b38a-ae16b31e8060](https://github.com/user-attachments/assets/ffe20e0a-7628-48f8-93f4-4d8abd4d6d83)
```
np.square(df['Highly Negative Skew'])
```
![370574387-44d1271b-931a-4407-8ac4-e28c8248e6cb](https://github.com/user-attachments/assets/ccb59214-b3f8-484b-aed4-408381efd152)
```
df['Highly Positive Skew_boxcox'],parameters=stats.boxcox(df['Highly Positive Skew'])

df
```
![370574675-92ac1792-885c-4d0d-97f5-5676b0495fc9](https://github.com/user-attachments/assets/839f7a5c-72a7-41b3-9288-126989c7a84a)
```
import seaborn as sns
import matplotlib.pyplot as plt
import statsmodels.api as sm
```
```
sm.qqplot(df["Moderate Negative Skew"],line='45')
plt.show()
```
![370574796-3db7be83-450e-46d4-bcba-389cb85f6c5e](https://github.com/user-attachments/assets/08affaaf-0514-43a1-952b-3ebaaa67b311)
```
sm.qqplot(np.reciprocal(df["Moderate Negative Skew"]),line='45')
plt.show()
```
![370575042-d35ee720-cd38-4bc1-84b3-c07e29297d7e](https://github.com/user-attachments/assets/14b20984-c332-4950-bbbd-845b0a9a5cbb)

# RESULT:
 Thus, performing Feature Encoding and Transformation process for the given data set is completed.

       
