# Ex:05 Feature Generation
## AIM
To read the given data and perform Feature Generation process and save the data to a file.

## Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

## ALGORITHM
### STEP 1
Read the given Data.

### STEP 2
Clean the Data Set using Data Cleaning Process.

### STEP 3
Apply Feature Generation techniques to all the feature of the data set.

### STEP 4
Save the data to the file.

## CODE :
Developed by : Naveenaa A.K
Reg No : 212222230094
## Data.csv:
```
import pandas as pd
df=pd.read_csv("data.csv")
print(df)

import category_encoders as ce
be=ce.BinaryEncoder()
df1=be.fit_transform(df["bin_1"])
df["bin_1"] = be.fit_transform(df["bin_1"])
df1

be=ce.BinaryEncoder()
df2=be.fit_transform(df["bin_2"])
df["bin_2"] = be.fit_transform(df["bin_2"])
df2

df1=df.copy()

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder,OneHotEncoder
import category_encoders as ce
be=ce.BinaryEncoder()
ohe=OneHotEncoder(sparse=False)
le=LabelEncoder()
oe=OrdinalEncoder()

df1["City"] = ohe.fit_transform(df1[["City"]])
temp=['Cold','Warm','Hot','Very Hot']
oe1=OrdinalEncoder(categories=[temp])
df1['Ord_1'] = oe1.fit_transform(df1[["Ord_1"]])
edu=['High School','Diploma','Bachelors','Masters','PhD']
oe2=OrdinalEncoder(categories=[edu])
df1['Ord_2']= oe2.fit_transform(df1[["Ord_2"]])
df1
```
## SCALING:
```
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df2=pd.DataFrame(sc.fit_transform(df1),columns=(['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target']))
df2

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df3=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df3

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df4=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df4

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df5=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df5
```
## Encoding data:
```
import pandas as pd
df=pd.read_csv("Encoding Data.csv")
df
```
## GENERATION:
```
import category_encoders as ce
be=ce.BinaryEncoder()
ndf=be.fit_transform(df["bin_1"])
df["bin_1"] = be.fit_transform(df["bin_1"])
ndf

be=ce.BinaryEncoder()
ndf2=be.fit_transform(df["bin_2"])
df["bin_2"] = be.fit_transform(df["bin_2"])
ndf2

df1=df.copy()

from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
le=LabelEncoder()
oe=OrdinalEncoder()

df1["nom_0"] = oe.fit_transform(df1[["nom_0"]])
temp=['Cold','Warm','Hot']
oe2=OrdinalEncoder(categories=[temp])
df1['ord_2'] = oe2.fit_transform(df1[['ord_2']])
df1
```
## SCALING:
```
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df0=pd.DataFrame(sc.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df0

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df2=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df2

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df3=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df3

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df4=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df4
```
## OUTPUT :
## (i) Data.csv
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-05/assets/113497406/387df8d7-ed25-443b-8be1-0d1bfdadaed5)
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-05/assets/113497406/735bf477-174c-4ba7-91f4-9f33f817cb94)
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-05/assets/113497406/ab54e0b8-7434-49a5-96cc-4902b801df42)
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-05/assets/113497406/e3c82327-1601-4155-8cda-a0efdb142f2d)

## Minmax scaling:
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-05/assets/113497406/2c6efcda-1cd1-4790-9365-59844c6998a1)
## Standard scaling:
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-05/assets/113497406/a8d5c162-3e69-446b-90a6-c7bfaf6e8009)

## Maxabs scaling:
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-05/assets/113497406/ec643798-a4c5-4714-96ce-1dcb6e88ddbd)
## Robust scaling:
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-05/assets/113497406/7e617f51-ec9f-4860-aefd-d5ae9a67612c)
## (ii) Encoding data.csv
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-05/assets/113497406/81f07773-a53c-43ca-bdc8-5b020bbb4df6)
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-05/assets/113497406/462a98d7-12dc-4292-910a-1e3cbec00d39)
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-05/assets/113497406/bb34642d-b8b0-4266-84b9-d1df47cb08bb)
## Minmax scaler:
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-05/assets/113497406/c418d508-2c0b-4131-b491-2ef8cb2a96e3)
## Standard scaler:
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-05/assets/113497406/d1d62e7d-e4dc-4230-9662-6afa7e2c5988)
## Maxabs scaler:
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-05/assets/113497406/64000c89-263c-4962-abfe-820a2833caf8)
## Robust scaler:
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-05/assets/113497406/311a688a-aab1-4744-9e60-f215e16396e1)
## Result:
Thus the Feature Generation and Feature Scaling process is applied to the given data set.
