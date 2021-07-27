
```uml

@startuml


!define MASTER_MARK_COLOR Orange 
!define TRANSACTION_MARK_COLOR DeepSkyBlue

'グラデーションさせる場合 #xx-xx
!define MAIN_ENTITY #MintCream-MistyRose


skinparam class {
    '図の背景
    BackgroundColor Snow
    '図の枠
    BorderColor Black
    'リレーションの色
    ArrowColor Black
}

package "ECサイト" as target_system {
  

    entity "顧客マスタ" as customer <m_customers> <<M,MASTER_MARK_COLOR>> {
        + customer_code [PK]
        --
        pass
        name
        address
        tel
        mail
        del_flag
        reg_date
    }

    entity "購入テーブル" as order <d_purchase> <<T,TRANSACTION_MARK_COLOR>> MAIN_ENTITY {
        + order_id [PK]
        --
        # customer_code [FK]
        purchase_date
        total_price
    }


    entity "購入詳細テーブル" as order_detail <d_purchase_detail> <<T,TRANSACTION_MARK_COLOR>> MAIN_ENTITY {
        + order_id   [PK]
        + detail_id  [PK]
        --
        # item_code [FK]
        price
        num
    }


    entity "商品マスタ" as items <m_items> <<M,MASTER_MARK_COLOR>> {
        + item_code [PK]
        --
        item_name
        price
        # category_id [FK]
        image
        detail
        del_flag
        reg_date
    }





}


customer       |o-ri-o{     order
order          ||-ri-|{     order_detail
order_detail    }-do-||     items
items          }o-le-||     category


@enduml

```
