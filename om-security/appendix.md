
# 環境構築後の事後作業について

外形監視(可用性モニタリング)の仕組みを実装してみよう
- 環境構築後の事後作業はなし

SQLのパフォーマンス・チューニングをしてみよう！
- チューニング対象のSQLの実行

**ADBのログイン情報**
 - ユーザ名：ADMIN
 - パスワード：Welcome12345##

【実行するSQL】
``` 
/*+ MONITOR */
WITH filtered_sales AS (
    SELECT CHANNEL_ID, PROD_ID, TIME_ID, AMOUNT_SOLD
    FROM SHADMIN.SALES
    WHERE TIME_ID BETWEEN TO_DATE('2010-01-01', 'YYYY-MM-DD') 
                      AND TO_DATE('2020-12-31', 'YYYY-MM-DD')
),
total_sales_by_prod AS (
    SELECT 
        f.PROD_ID, 
        SUM(f.AMOUNT_SOLD) AS total_sales
    FROM 
        filtered_sales f
    JOIN SHADMIN.SALES s ON f.PROD_ID = s.PROD_ID
    WHERE s.TIME_ID BETWEEN TO_DATE('2010-01-01', 'YYYY-MM-DD') 
                        AND TO_DATE('2020-12-31', 'YYYY-MM-DD')
    GROUP BY 
        f.PROD_ID
)
SELECT 
    fs.CHANNEL_ID,
    fs.PROD_ID,
    tsp.total_sales
FROM 
    filtered_sales fs
LEFT JOIN 
    total_sales_by_prod tsp ON fs.PROD_ID = tsp.PROD_ID
GROUP BY 
    fs.CHANNEL_ID, fs.PROD_ID, tsp.total_sales;
```





