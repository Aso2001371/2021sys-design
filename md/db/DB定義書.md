# DB定義書
## ER図
[ER図](https://github.com/Aso2001371/2021sys-design/blob/main/EC%E3%82%B5%E3%82%A4%E3%83%88%E3%82%A8%E3%83%B3%E3%83%86%E3%82%A3%E3%83%86%E3%82%A3.md "ER図はこちら")

# DBテーブルカラム詳細一覧

## データベース詳細

d_purchase
| 属性名 | 型 | PK | NN | FK |
|-------|-----|---|----|----|
| order_id | bigint(20) | 〇| 〇| |
| customer_code | varchar(20) | | 〇| |
| purchase_date | date | | 〇| |
| total_price | int(11) | | 〇| |

d_purchase_detail
| 属性名 | 型 | PK | NN | FK |
|-------|-----|---|----|----|
| detail_id | bigint(20) | 〇| 〇| |
| order_id | bigint(20) | 〇| 〇| 〇|
| item_code | int(11) | | 〇| |
| price | int(11) | | 〇| |
| num | int(11) | | 〇| |

m_customers
| 属性名 | 型 | PK | NN | FK |
|-------|-----|---|----|----|
| customer_code | varchar(50) | 〇| 〇| |
| pass | varchar(50) | 〇| 〇| 〇|
| name | varchar(20) | | 〇| |
| address | varchar(100) | | 〇| |
| tel| varchar(20) | | 〇| |
| mail | varchar(100) | | 〇| |
| del_flag | int(11) | | | |
| reg_date | date | | 〇| |

m_category
| 属性名 | 型 | PK | NN | FK |
|-------|-----|---|----|----|
| category_id | int(11) | 〇| 〇| |
| name | varchar(20) | | 〇| |
| reg_date | date | | 〇| |

m_items
| 属性名 | 型 | PK | NN | FK |
|-------|-----|---|----|----|
| item_code | int(11) | 〇| 〇| |
| item_name| varchar(50) | | 〇| |
| price | int(11) | | 〇| |
| category_id | int(11) | | 〇| 〇|
| image | varchar(200) | | 〇| |
| detail | varchar(500) | | | |
| del_flag | int(11) | | | |
| reg_date | date | | 〇| |
