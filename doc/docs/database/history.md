# 履歴テーブル

## 概要

来客の受付履歴やバッジ・カードの取り出し履歴を管理するテーブルです。来客履歴、カード貸出履歴でのアクセスパターンをサポートします。

## 基本構造

| 属性名 | データ型 |
| -- | -- |
| PK | history_id (String) |
| SK | timestamp (String) |
| GSIPK1 | user_id (String) |
| GSIPK2 | device_id (String) |
| TTL | expires_at (Number) |

## 属性

=== "`history_id`"

    履歴ID

    ```ts
    history_id: string
    ```

=== "`timestamp`"

    タイムスタンプ

    ```ts
    timestamp: string
    ```

    履歴が発生した日時をISO 8601形式で記録します。

=== "`history_type`"

    履歴種別

    ```ts
    history_type: "visitor_reception" | "badge_rental" | "visitor_card_rental" | "employee_card_rental" | "badge_return" | "visitor_card_return" | "employee_card_return"
    ```

    | 種別 | 説明 |
    | -- | -- |
    | `visitor_reception` | 来客受付 |
    | `badge_rental` | バッジ貸出 |
    | `visitor_card_rental` | 来客用カード貸出 |
    | `employee_card_rental` | 社員用カード貸出 |
    | `badge_return` | バッジ返却 |
    | `visitor_card_return` | 来客用カード返却 |
    | `employee_card_return` | 社員用カード返却 |

=== "`user_id`"

    ユーザーID

    ```ts
    user_id: string
    ```

    履歴に関連するユーザーのIDです。

=== "`usergroup_id`"

    ユーザーグループID

    ```ts
    usergroup_id: string
    ```

    履歴に関連するユーザーグループのIDです。

=== "`device_id`"

    デバイスID

    ```ts
    device_id: string
    ```

    履歴が発生したデバイスのIDです。バッジ・カードの貸出・返却時に設定されます。

=== "`unit_type`"

    ユニット種別

    ```ts
    unit_type: "badge" | "visitor_card" | "employee_card"
    ```

=== "`unit_no`"

    ユニット番号

    ```ts
    unit_no: string
    ```

    バッジ・カードの貸出・返却時に使用されたユニット番号です。

=== "`item_id`"

    アイテムID

    ```ts
    item_id: string
    ```

    貸出・返却されたアイテムのIDです。

=== "`reservation_id`"

    予約ID

    ```ts
    reservation_id: string
    ```

    来客受付時に設定される予約IDです。

=== "`action_details`"

    アクション詳細

    ```ts
    action_details: {
        action: string,
        description: string,
        metadata?: Record<string, any>
    }
    ```

    履歴の詳細情報を記録します。

=== "`comment`"

    コメント

    ```ts
    comment: string
    ```

    管理者によるコメントが追加できます。

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

=== "`expires_at`"

    削除予定日時

    ```ts
    expires_at: number
    ```

    作成日から1年後の時間をUNIXエポック時間形式で登録します。 