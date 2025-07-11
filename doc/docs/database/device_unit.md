# デバイスユニットテーブル

## 概要

SPLATSの物品管理デバイスのユニット情報を管理するテーブルです。1デバイスあたり複数ユニットの箱があり、それぞれのユニットにバッジやカードが入っているかを管理します。

## 基本構造

| 属性名 | データ型 |
| -- | -- |
| PK | device_id (String) |
| SK | unit_type#unit_no (String) |
| GSIPK1 | unit_type (String) |
| TTL | expires_at (Number) |

## 属性

=== "`device_id`"

    デバイスID

    ```ts
    device_id: string
    ```


=== "`unit_type#unit_no`"

    ユニット種別#ユニット番号

    ```ts
    type: string
    ```

=== "`unit_type`"

    ユニット種別

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

    先頭を0埋めした2桁の整数文字列で、デバイス内のユニット位置を表します。

=== "`status`"

    ユニットステータス

    ```ts
    status: "empty" | "occupied" | "maintenance" | "error"
    ```

    | ステータス | 説明 |
    | -- | -- |
    | `empty` | 空き |
    | `occupied` | 使用中 |
    | `maintenance` | メンテナンス中 |
    | `error` | エラー（故障中により使用禁止） |

    ※ リアルタイムの状態ではありません。リアルタイムの状態は本サービス内では管理せずSPLATSに任せます。

=== "`item_id`"

    アイテムID

    ```ts
    item_id: string
    ```

    ユニットに入っているアイテムのIDです。`status` が `occupied` のときに設定されます。

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
