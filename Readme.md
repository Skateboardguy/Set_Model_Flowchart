# 正則化建模流程

## 資料處理與特徵工程


```mermaid 
flowchart TD 
A[RawData] --> B["特徵拆分<br/>連續變數(cont_cols)<br/>類別變數(cat_cols)"] 
B --> C["ColumnTransformer<br/> 標準化(StandardScaler)<br/> 讀熱編碼 (OneHotEncoder)"] 
C --> D["LassoCV (cv=5)<br/>"] 
D --> E[篩選保留後的重要特徵] 
E --> F["RidgeCV (cv=5, alphas=logspace(-3,3,100))<br/>建立最終模型"] 
F --> G[解釋係數<br/>重要因子排名]



