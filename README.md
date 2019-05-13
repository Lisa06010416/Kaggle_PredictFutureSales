# Kaggle_PredictFutureSales
## DSAI HW3  p76074517 林怡瑄



#### data exploration and data preprocessing
參考 [Feature engineering, xgboost](https://www.kaggle.com/dhimananubhav/feature-engineering-xgboost)  
對資料中的兩個欄位(item_cnt_day與item_price)去除Outliers  
以及一些資料問題 像是 item price < 0 以及 商店重複  
還有用商店以及商品名子 找出商店所在城市以及商品的類別與子類別  

target lags =>  把資料的時間序列增加後加入原本的matric裡面  
把以前時刻的資料增加時間序列後 對到後面時間序列同一商店下同一商品的銷售紀錄  
ex lag 2 => 兩個時間序列前的銷售紀錄  

Mean encoded features => 用各種平均值增加資料  
Trend features => 知道過去六個月中的價格變動趨勢  
Last month shop revenue trend => 上一個月商店的銷售趨勢  
Special features => 上品銷售月與當月天數  
item_shop_last_sale => 同一個商品在同一個商店 距離上次被買隔多久  
item_last_sale => 同一個商品 距離上次被買隔多久  
item_shop_first_sale => 同一個商品在同一個商店 第一次被買的時間  
item_first_sale =>  第一次被買的時間  

#### feature selection
Score:0.90646  
https://github.com/Lisa06010416/Kaggle_PredictFutureSales/blob/master/raw/feature.PNG  
Score:0.91671  
https://github.com/Lisa06010416/Kaggle_PredictFutureSales/blob/master/raw/remove%20some%20feature.PNG  

#### model selection
xgboost:  
Score  
0.90646  

LinearRegression:  
Score  
1.01056  
會有負值  

LinearRegression:  
Score  
1.00994  
處理掉負值之後  