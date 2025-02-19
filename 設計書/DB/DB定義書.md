# DB定義書
## ER図
[ER図はこちら](https://github.com/Aso2001219/team/blob/main/%E8%A8%AD%E8%A8%88%E6%9B%B8/DB/ER%E5%9B%B3.md)

# DBテーブルカラム詳細一覧

# データベース詳細

## 購入テーブルd_purchase
|和名|属性(カラム名)|型|PK|NN|FK|
|---|---|--|--|--|---|
|オーダーID|order_id|bigint(20)|〇|〇||
|顧客コード|customer_code|varchar(50)||〇||
|購入日|purchase_date|date||〇||
|総額|total_price|int(11)||〇||


## 購入詳細テーブル d_purchase_datail
|和名|属性名|型|PK|NN|FK|
|---|-----|--|--|--|--|
|オーダー詳細ID|detail_id|bigint(20)|〇|〇||
|オーダーID|order_id|bigint(20)|〇|〇|〇|
|商品コード|item_code|int(11)||〇||
|価格|price|int(11)||〇||
|数量|num|int(11)||〇||

## 顧客マスタm_customers
|和名|属性名|型|PK|NN|FK|
|----|-----|--|--|--|--|
|顧客コード|customer_id|varchar(50)|〇|〇||
|パスワード|pass|varchar(8~16)|〇|〇|〇|
|氏名|name|varchar(50)||〇||
|住所|adress|varchar(50)||〇||
|電話番号|tel|varchar(50)||〇||
|メールアドレス|mail|varchar(50)||〇||
|削除フラグ|del_fiag|int(11)||||
|登録日|reg_date|date||〇||

## カテゴリマスタm_category
|和名|属性名|型|PK|NN|FK|
|----|-----|--|--|--|--|
|カテゴリID|category_id|int(11)|〇|〇||
|氏名|name|varchar(20)||〇||
|登録日|reg_date|date||〇||

## お気に入りマスタm_favorite
|和名|属性名|型|PK|NN|FK|
|----|-----|--|--|--|--|
|顧客コード|customer_id|varchar(50)|〇|〇|〇|
|カテゴリID|category_id|int(11)||〇|〇|
|商品コード|item_code|int(11)|〇|〇|〇|
|削除フラグ|del_date|int(11)||||


## 商品マスタm_items
|和名|属性名|型|PK|NN|FK|
|---|-----|--|--|--|--|
|商品コード|item_code|int(11)|〇|〇||
|商品名|item_name|varchar(50)||〇||
|価格|price|int(11)||〇||
|カテゴリID|category_id|int(11)||〇|〇|
|画像ファイル名|image|varchar(200)||〇||
|商品詳細説明|detail|varchar(500)||||
|削除フラグ|del_flag|int(11)||||
|登録日|reg_date|date||〇||

