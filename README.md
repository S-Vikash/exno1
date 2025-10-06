# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
import pandas as pd
d=pd.read_csv("Data_set.csv")
df = pd.DataFrame(d)
print(df)
<img width="611" height="689" alt="image" src="https://github.com/user-attachments/assets/76b0ebdf-721e-41f0-962c-9371e0738295" />


import pandas as pd
d=pd.read_csv("Data_set.csv")
df = pd.DataFrame(d)
df.info()
<img width="404" height="281" alt="image" src="https://github.com/user-attachments/assets/ebcbc51d-7230-4f3a-9e97-b9e5fdbc28d9" />


import pandas as pd
d=pd.read_csv("Data_set.csv")
df = pd.DataFrame(d)
df.describe()
<img width="625" height="276" alt="image" src="https://github.com/user-attachments/assets/1cffe69d-c4b6-41fe-b8cc-4a03519201a5" />


import pandas as pd
d=pd.read_csv("Data_set.csv")
df = pd.DataFrame(d)
print(df.isnull())
<img width="533" height="457" alt="image" src="https://github.com/user-attachments/assets/a0005a6d-a740-40f6-9811-c88690504f71" />


import pandas as pd
d=pd.read_csv("Data_set.csv")
df = pd.DataFrame(d)
print(df.notnull())
<img width="552" height="465" alt="image" src="https://github.com/user-attachments/assets/1cadb6a4-8a1c-48a6-aa32-1093aa0f84b4" />


import pandas as pd
d=pd.read_csv("Data_set.csv")
df = pd.DataFrame(d)
print(df.isnull().sum())
<img width="215" height="175" alt="image" src="https://github.com/user-attachments/assets/687f1720-8fa6-4ec8-a690-349bbfb3f982" />


import pandas as pd
d=pd.read_csv("Data_set.csv")
df = pd.DataFrame(d)
print(df.dropna())
<img width="537" height="687" alt="image" src="https://github.com/user-attachments/assets/f172e3a9-93fb-45cf-aa6f-35fbc8ab8b11" />



import pandas as pd
d=pd.read_csv("Data_set.csv")
df = pd.DataFrame(d)
print(df.dropna(axis=1))
<img width="421" height="249" alt="image" src="https://github.com/user-attachments/assets/04ebcb35-589f-4c15-bd81-13c2398d695c" />


import pandas as pd
data = pd.read_csv('Data_set.csv')
df = pd.DataFrame(data)
dff = df.fillna(0)
print(dff)
<img width="580" height="683" alt="image" src="https://github.com/user-attachments/assets/ef0e3ddf-4157-4615-9509-54f18a2802a3" />


import pandas as pd
d=pd.read_csv("Data_set.csv")
df = pd.DataFrame(d)
print(df.ffill())
<img width="590" height="688" alt="image" src="https://github.com/user-attachments/assets/ffa981e4-cd67-434a-ac9e-a1ef647dd905" />


import pandas as pd
d=pd.read_csv("Data_set.csv")
df = pd.DataFrame(d)
print(df.bfill())
<img width="579" height="687" alt="image" src="https://github.com/user-attachments/assets/7ade9457-2d26-4a25-89a1-b40632fa9c56" />


import pandas as pd
data = pd.read_csv('Data_set.csv')
df = pd.DataFrame(data)
df['watchers']=df['watchers'].fillna(df['watchers'].mean())
df
<img width="1097" height="404" alt="image" src="https://github.com/user-attachments/assets/5adfd417-bf3b-4a83-bdb8-980a5186f6fe" />


import pandas as pd
data=pd.read_csv('Data_set.csv')
df = pd.DataFrame(data)
df.interpolate(method='linear')
<img width="1049" height="398" alt="image" src="https://github.com/user-attachments/assets/647548e3-3ee1-46d1-bba9-7b144468ed08" />


import pandas as pd
data = pd.read_csv('Data_set.csv')
df = pd.DataFrame(data)
df.drop_duplicates()
df
<img width="1054" height="396" alt="image" src="https://github.com/user-attachments/assets/7bc56cac-eb78-4bf0-bcf4-2cf7efa3c242" />


from scipy import stats 
import pandas as pd
import numpy as np
data_set = pd.read_csv('iris.csv')
df = pd.DataFrame(data_set)

z_scores = np.abs(stats.zscore(df.select_dtypes(include=[np.number])))
df_cleaned = df[(z_scores < 3).all(axis=1)]
df_cleaned
<img width="453" height="400" alt="image" src="https://github.com/user-attachments/assets/4f0cd695-90ba-46f4-9236-4a4bc9479306" />


import pandas as pd

import numpy as np

data_set = pd.read_csv("iris.csv")

df = pd.DataFrame(data_set)

Q1 = df["sepal_width"].quantile(0.25) 
Q3 = df["sepal_width"].quantile(0.75)

IQR = Q3 - Q1

lower_bound = Q1 - 1.5 * IQR 
upper_bound = Q3 + 1.5 * IQR

print("The Orginal DataSet") 
print(df)

outliers = df[(df['sepal_width'] < lower_bound) | (df['sepal_width'] > upper_bound)]

print("The Outliers") 
print(outliers)

df_clean = df[(df['sepal_width'] >= lower_bound) & (df['sepal_width'] <= upper_bound)]

print("The Dataset after removing the outliers")
print(df_clean)
<img width="508" height="622" alt="image" src="https://github.com/user-attachments/assets/16691cfb-43fc-445e-aadb-c0e26816ac58" />


# Result
          <<include your Result here>>
