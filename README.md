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
df=pd.read_csv("Encoding Data.csv")
print(df)

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
pm=['Hot','Warm','Cold']
e1=OrdinalEncoder(categories=[pm])
e1.fit_transform(df[["ord_2"]])
df['bo2']=e1.fit_transform(df[["ord_2"]])
print(df)
```
<img width="474" height="750" alt="Screenshot 2026-08-18 105229" src="https://github.com/user-attachments/assets/85f30f96-4e8e-497f-b7c7-b69fe4966dd8" />


```


le=LabelEncoder()
dfc=df.copy()
dfc['ord_2']=le.fit_transform(dfc['ord_2'])
print(dfc)

from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder(sparse_output=False)
df2=df.copy()
enc=pd.DataFrame(ohe.fit_transform(df2[["nom_0"]])) # Orders in Alphabetical O
df2=pd.concat([df2,enc],axis=1)
print(df2)


```
<img width="543" height="535" alt="Screenshot 2026-08-18 105254" src="https://github.com/user-attachments/assets/0fea753c-884a-431a-9b17-5a2c56f2bbf6" />

```
!pip install category_encoders
from category_encoders import BinaryEncoder
df=pd.read_csv("data.csv")
df
i

be=BinaryEncoder()
nd=be.fit_transform(df['Ord_2'])
dfb=pd.concat([df,nd],axis=1)
dfb

```

<img width="847" height="728" alt="Screenshot 2026-08-18 105523" src="https://github.com/user-attachments/assets/1c760a33-9936-4764-a0c5-b5255d42b61c" />

```
from category_encoders import TargetEncoder
te=TargetEncoder()
CC=df.copy()
new=te.fit_transform(X=CC["City"],y=CC["Target"])
CC=pd.concat([CC,new],axis=1)
CC

```

<img width="634" height="433" alt="Screenshot 2026-08-18 105636" src="https://github.com/user-attachments/assets/60ed9e96-358a-4b48-a621-6cb07b6ad6a3" />


# RESULT:
       # INCLUDE YOUR RESULT HERE

       
