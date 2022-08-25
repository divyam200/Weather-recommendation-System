import pandas as pd
from sklearn.preprocessing import LabelEncoder
from sklearn.naive_bayes import GaussianNB

#Reading CSV files
df = pd.read_csv("play_tennis.csv")
df

#Encoding the strings numercis
numerics = LabelEncoder()

#Dropping the target variable and make it newframe
inputs = df.drop('play',axis='columns')
target = df['play']
target

#Creating new dataframe
inputs['outlook_in'] = numerics.fit_transform(inputs['outlook'])
inputs['temprature_in'] = numerics.fit_transform(inputs['temp'])
inputs['humidity_in'] = numerics.fit_transform(inputs['humidity'])
inputs['wind_in'] = numerics.fit_transform(inputs['wind'])

#dropping string values
inputs_n = inputs.drop(['day','outlook','temp','humidity','wind'],axis='columns')
inputs_n

clf = GaussianNB()
clf.fit(inputs_n,target)

clf.score(inputs_n,target)

sample_data = list(map(int,input().split(',')))

prediction = clf.predict([sample_data])

if  prediction == ['Yes']:
    print("Wohoo ! Weather is suitable for play.")
else:
    print("Ohh ! Weather is not suitable for play.")
    
    
    
#Enter in format Outlook,temprature,humidity,wind
#outlook --> 0 - Overcast , 1 - Rain , 2 - Sunny
#temprature --> 0 - Cool ,  1 - Hot , 2 - Mild
#Humidity --> 0 - High , 1 - Normal
#wind --> 0 - Strong , 1 - Weak
