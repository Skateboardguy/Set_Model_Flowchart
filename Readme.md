#  
##  
```mermaid 
flowchart TD 
A["final_datav3] --> B[<br/>(cont_cols)<br/>(cat_cols)"] 
B --> C["ColumnTransformer<br/> StandardScaler (連續變數)<br/> OneHotEncoder (類別變數, sparse=True)"] 
C --> D["LassoCV (cv=5)<br/>"] 
D --> E[篩選保留後的重要特徵] 
E --> F[RidgeCV (cv=5, alphas=logspace(-3,3,100))<br/>] 
F --> G[<br/>]

