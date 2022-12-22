### 查看数据

```python
data.index
data.columns
data.describe()
data.head()
data.tail()
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
