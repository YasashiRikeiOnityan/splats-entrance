# アイテムテーブル

## 概要

ユニットに保管するアイテムを管理するテーブルです。バッジやカードの情報を管理し、どのデバイスのどのユニットに保管されているかを追跡します。

## 基本構造

| 属性名 | データ型 |
| -- | -- |
| PK | item_id (String) |
| SK | device_id (String) |
| GSIPK1 | device_id (String) |
| TTL | expires_at (Number) |

## 属性

=== "`item_id`"

    アイテムID

    ```ts
    item_id: string
    ```

=== "`device_id`"

    デバイスID

    ```ts
    device_id: string
    ```

    アイテムが保管されているデバイスのIDです。

=== "`unit_type`"

    アイテム種別

    ```ts
    unit_type: "badge" | "visitor_card" | "employee_card"
    ```

    | 種別 | 説明 |
    | -- | -- |
    | `badge` | バッジ |
    | `visitor_card` | 来客用カード（業者など） |
    | `employee_card` | 社員用カード |

=== "`unit_no`"

    ユニット番号

    ```ts
    unit_no: string
    ```

    アイテムが保管されているユニット番号です。先頭を0埋めした2桁の整数文字列です。

=== "`badge_number`"

    バッジ番号

    ```ts
    badge_number: string
    ```

    先頭を0埋めした2桁の整数文字列です。

=== "`card_data`"

    カードデータ

    ```ts
    card_data: string
    ```

    Felicaカードの仕様に従ったカード番号です。

=== "`created_at`"

    作成日時

    ```ts
    created_at: string
    ```

=== "`updated_at`"

    更新日時

    ```ts
    updated_at: string
    ```
