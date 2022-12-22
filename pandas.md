https://pandas.pydata.org/docs/user_guide/missing_data.html
### 查看数据

```python
data.index
data.columns
data.describe()
data.head()
data.tail()
data.AGE.unique()#查看有哪些值，不重复
data.AGE.value_counts()
#对所有值修改
review_points_mean = reviews.points.mean()
reviews.points.map(lambda p: p - review_points_mean)#集体减去平均数
#更简洁的方法
reviews.points - reviews_points_mean
#apply()可以执行一个函数
def remean_points(row):
    row.points = row.points - review_points_mean
    return row

reviews.apply(remean_points, axis='columns')
```
### 选择特定行和列
```python
import pandas as pd
data = pd.read_csv("Covid Data.csv")
//列
data.ICU 
data["ICU"]
//行
data[10:20]
data.loc[:,["OBESITY","ICU"]]
data.iloc[1:3 , 2:4]
data.iloc[[1, 2, 5] , [4, 6]]

```
###删除行或列
用法：DataFrame.drop(labels=None,axis=0, index=None, columns=None, inplace=False)

参数说明：
labels 就是要删除的行列的名字，用列表给定
axis 默认为0，指删除行，因此删除columns时要指定axis=1；
index 直接指定要删除的行
columns 直接指定要删除的列
inplace=False，默认该删除操作不改变原数据，而是返回一个执行删除操作后的新dataframe；
inplace=True，则会直接在原数据上进行删除操作，删除后无法返回。

因此，删除行列有两种方式：
1）labels=None,axis=0 的组合
2）index或columns直接指定要删除的行或列

### 条件选择

```python
data[ data.ICU > 2]
data[(data.AGE<30) & (data.AGE >20)]
data[ data.MEDICAL_UNIT.isin( [1,2,3] )]
```

### 画图

```python
import matplotlib.pyplot as plt
plt.figure()
data.plot().bar()//柱状图
data.plot().bar(stacked = True)//柱状图叠加
data.plot().barh()//水平柱状图
