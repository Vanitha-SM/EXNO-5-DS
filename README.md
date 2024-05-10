# EXNO-5-DS-DATA VISUALIZATION USING MATPLOT LIBRARY

# Aim:
  To Perform Data Visualization using matplot python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
### TO CAPTURE A TREND
1.Line Chart
```
import matplotlib.pyplot as plt
import numpy as np
x=[0,1,2,3,4,5]
y=[0,1,4,9,16,25]
plt.plot(x,y)
plt.show()
```
![image](https://github.com/Vanitha-SM/EXNO-5-DS/assets/119557985/80353c30-651b-4c6c-9a93-c437027e6f27)

2.Multi-Line Chart

```
x1=[1,2,3]
y1=[2,4,1]
plt.plot(x1,y1,label="line 1")
x2=[1,2,3]
y2=[4,1,3]
plt.plot(x2,y2,label="line 2")
plt.xlabel('x-axis')
plt.ylabel('y-axis')
plt.title('Multi-Line Chart')
plt.legend()
plt.show()
```
![image](https://github.com/Vanitha-SM/EXNO-5-DS/assets/119557985/bc614619-8fc3-40db-bd83-4c58e4ea0921)

3.Area Chart

```
x=[1,2,3,4,5]
y1=[10,12,14,16,18]
y2=[5,7,9,11,13]
y3=[2,4,6,8,10]
plt.fill_between(x,y1,color='blue')
plt.fill_between(x,y2,color='pink')
plt.plot(x,y1,color='red')
plt.plot(x,y2,color='black')
plt.legend(['y1','y2'])
plt.show()
```
![image](https://github.com/Vanitha-SM/EXNO-5-DS/assets/119557985/69aafe4c-0830-42da-94ab-90e1c5638892)

4.Stacked Area Chart

```
plt.stackplot(x,y1,y2,y3,labels=['Line 1','Line 2','Line 3'])
plt.legend(loc='upper left')
plt.title('Stacked Line Chart')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.show()
```
![image](https://github.com/Vanitha-SM/EXNO-5-DS/assets/119557985/7b05fb6c-da90-4b62-b6c7-71da1362b679)

5.Spline Chart

```
from scipy.interpolate import make_interp_spline
x=np.array([1,2,3,4,5,6,7,8,9,10])
y=np.array([2,4,5,7,8,8,9,10,11,12])
spl=make_interp_spline(x,y)
x1=np.linspace(x.min(),x.max(),100)
y1=spl(x1)
plt.plot(x,y,'*',label='data')
plt.plot(x1,y1,'-',label="spline")
plt.legend()
plt.show()
```
![image](https://github.com/Vanitha-SM/EXNO-5-DS/assets/119557985/b562ab9b-a335-461f-b34f-ef13f9c40862)

### TO VISUALIZE RELATIONSHIPS
1.Bar Chart
```
val=[5,6,3,7,2]
names=["A","B","C","D","E"]
plt.bar(names,val,color="blue")
plt.show()
```
![image](https://github.com/Vanitha-SM/EXNO-5-DS/assets/119557985/b6b76524-f4b7-464f-af5b-100d315d12fb)

2.Scatter Plot

```
x=[0,1,2,3,4,5]
y=[0,1,4,9,16,25]
plt.scatter(x,y,s=30,color="red")
plt.show()
```
![image](https://github.com/Vanitha-SM/EXNO-5-DS/assets/119557985/cedb4aee-824c-45de-9c54-8147afda4c87)

3.Bubble Chart
```
x = [1, 2, 3, 4, 5]
y = [10, 15, 20, 25, 30]
sizes = [100, 200, 300, 400, 500]
plt.scatter(x, y, s=sizes, alpha=0.5)
plt.xlabel('x_values')
plt.ylabel('y_values')
plt.title('Bubble Chart')
plt.show()
```
![image](https://github.com/Vanitha-SM/EXNO-5-DS/assets/119557985/5ad3f5a6-ac80-417d-9cc1-a466b417ead6)

### TO CAPTURE DISTRIBUTIONS
1.Histogram
```
ages=[2,5,70,40,30,45,50,45,43,40,44,60,7,13,57,18,90,77,32,21,20,40]
range=(0,100)
bins=10
plt.hist(ages,bins,range,color='purple',histtype='bar',rwidth=0.8)
plt.xlabel('age')
plt.ylabel('No. Of People')
plt.title('Histogram')
plt.show()
```
![image](https://github.com/Vanitha-SM/EXNO-5-DS/assets/119557985/e46be758-f204-4c02-9900-e92a284d45d1)

2.Box Plot
```
np.random.seed(0)
data=np.random.normal(loc=0,scale=1,size=100)
data
fig,ax=plt.subplots()
ax.boxplot(data)
ax.set_xlabel('Data')
ax.set_ylabel('Values')
ax.set_title('Box Plot')
```
![image](https://github.com/Vanitha-SM/EXNO-5-DS/assets/119557985/4413e459-7eec-4ce8-9b2b-40209ea155f0)

3.Violin Plot

```
data = [np.random.normal(loc=0, scale=1, size=100),
        np.random.normal(loc=2, scale=1, size=100),
        np.random.normal(loc=1, scale=2, size=100)]
plt.violinplot(data)
plt.xlabel('Groups')
plt.ylabel('Values')
plt.title('Violin Plot')
plt.xticks([1, 2, 3], ['Group 1', 'Group 2', 'Group 3'])
plt.show()
```
![image](https://github.com/Vanitha-SM/EXNO-5-DS/assets/119557985/20eb8b96-beb2-4a57-a1bb-fd8da31f7cdc)

4.Density Chart
```
data = np.random.normal(0, 1, 1000)
plt.hist(data, bins=30, density=True, alpha=0.5)
plt.title('Density Plot Example')
plt.xlabel('Values')
plt.ylabel('Density')
from scipy.stats import gaussian_kde
kde = gaussian_kde(data)
x_vals = np.linspace(min(data), max(data), 1000)
plt.plot(x_vals, kde(x_vals), 'r')
plt.show()
```
![image](https://github.com/Vanitha-SM/EXNO-5-DS/assets/119557985/82ab8bce-5f8c-4122-864c-5e7c8fb66da3)

5.Pie Chart
```
act=['eat','sleep','work','play']
slices=[3,7,8,6]
color=['r','y','g','b']
plt.pie(slices,labels=act,colors=color,startangle=90,shadow=True,explode=(0.1,0.1,0.1,0.1),radius=1.2,
autopct='%1.1f%%')
plt.legend()
plt.show()
```
![image](https://github.com/Vanitha-SM/EXNO-5-DS/assets/119557985/62b5566d-9c27-4025-8e6c-b71023122801)


# Result:
The Data Visualization using matplot python library is implemented successfully.

