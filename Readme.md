#  
##  
```mermaid 
flowchart TD 
A[ final_datav3] --> B[<br>(cont_cols)<br>(cat_cols)] 
B --> C[ColumnTransformer<br> StandardScaler ()<br> OneHotEncoder (, sparse=True)] 
C --> D[LassoCV (cv=5)<br>] 
D --> E[] 
E --> F[RidgeCV (cv=5, alphas=logspace(-3,3,100))<br>] 
F --> G[<br>]

