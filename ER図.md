```uml
@startuml

!define MASTER_MARK_COLOR Orange
!define TEBUE_MARK_COLOR RED
!define TRANSACTION_MARK_COLOR DeepSkyBlue

'グラデーションさせる場合 #xx-xx
!define MAIN_ENTITY #MintCream-MistyRose

/'
  デフォルト色を"skinparam class"で設定します。
'/
skinparam class {
    '図の背景
    BackgroundColor Snow
    '図の枠
    BorderColor Black
    'リレーションの色
    ArrowColor Black
}


 entity "購入テーブル" as purchase <d_purchase> <<T,TEBUE_MARK_COLOR>>{
+ order_id[PK]
--
customer_code
purchase_date
total_price

}


entity "購入詳細テーブル" as d_purchase_detail <d_purchase_detail> <<T,TEBUE_MARK_COLOR>>{
+ order_id [PK][NN][FK]
+ detail_id [PK]
--
item_code
price
num

}



entity "顧客マスタ" as m_customers <m_customers> <<M,MASTER_MARK_COLOR>>{
+ customaer_code [PK][NN]
--
pass
name
address
tel
mail
del_flag
reg_date

}


entity "カテゴリマスタ" as m_category <m_category> <<M,MASTER_MARK_COLOR>>{
+ category_id[PK][NN]
--
name
reg_date

}

entity "お気に入りマスタ" as m_favorite <m_category> <<M,MASTER_MARK_COLOR>>{
+ customaer_id[PK][NN]
+ item_code[PK][NN]
--
category_id
del_flag

}




entity "商品マスタ" as m_items <m_items><<M,MASTER_MARK_COLOR>>{
+ item_code[PK]
--
item_name
price
category_id
image
detail
del_flag
reg_date

}

purchase }o--o| m_customers 
 d_purchase_detail }|--|| purchase
 m_items }o--|| m_category
 m_favorite }o-ri- m_customers
 m_favorite }o-le- m_category
 m_favorite }o-do- m_items




@enduml
```





