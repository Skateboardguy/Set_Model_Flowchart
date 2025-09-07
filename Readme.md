# 機器學習建模流程

## 資料處理與特徵工程流程

```mermaid 
flowchart TD 
A["final_datav3] --> B[<br/>(cont_cols)<br/>(cat_cols)"] 
B --> C["ColumnTransformer<br/> StandardScaler (連續變數)<br/> OneHotEncoder (類別變數, sparse=True)"] 
C --> D["LassoCV (cv=5)<br/>"] 
D --> E[篩選保留後的重要特徵] 
E --> F["RidgeCV (cv=5, alphas=logspace(-3,3,100))<br/>建立最終模型"] 
F --> G[解釋係數<br/>重要因子排名]

